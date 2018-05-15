# git stash


假设这种场景，当前你正在某个分支上做修改，正改到一半，乱七八糟时，烦了，想先暂停修改，转到另一个分支上做别的工作，问题是：你不想提交进行了一半的工作，<br/>否则以后你可能无法回到这个工作节点，解决的办法就是 git stash 命令
     
假设我们修改了readme.txt,还未修改完毕，所以还未提交到暂存区，这时执行 git status 命令
	
```     
	$ git status
	# On branch master
	# Changes to be committed:
	#   (use "git reset HEAD <file>..." to unstage)
	#
	#      modified:   readme.txt
	#
```
这时，你想切换分支，但又不想提交，执行 git stash 命令
```	
	Saved working directory and index state WIP on master: 1b736cc add new file
	HEAD is now at 1b736cc add new file
```
这时，会将你修改过的文件和暂存的变更保存到一个未完结变更的堆栈中，再次执行 git status 
```
	# On branch master
	nothing to commit, working directory clean	
```
你现在可以方便的切换到其他分支工作。如果要查看现有的储存，可以执行 
```	
	$git stash list
```
git会列出当前的储存列表
```
	stash@{0}: WIP on master: 1b736cc add new file
```     
等到你其他分支工作完成后，再次切换到当前分支,想继续之前的工作，执行 git stash apply,会恢复到最近的一个储存，如果想应用更早的储存，可以通过名字指<br/>定:
```   
	git stash apply stash@{2}	
```
如果想移除一个储存，执行命令 
```     
     git stash drop <Name>
```

未完待续......


