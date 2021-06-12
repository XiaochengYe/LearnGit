## 廖雪峰—Git

####创建版本库
1.创建空目录	mkdir cd pwd
2.将目录变成Git可管理仓库	git init	ls -ah

####文件添加版本库
1.文件添加到仓库	git add xxx
2.文件提交到仓库	git commit -m "xxx"		git commit -a --allow-empty-message -m ""

#### 更改文件与提交
1.更改文件
2.查看更改	查看状态git status	对比git diff xxx
3.提交更改	①git add xxx	看状态(将要提交的修改)git status	②提交git commit -m "xxx"	(看状态)
看历史记录	git log		git log --pretty==oneline

#### 版本回退
Head 当前版本	Head^上一版	 Head^^上上一版本	HEAD~100
1.退回上一版本	git reset --hard HEAD^
	查看版本库状态(历史提交版本)	git log --pretty=oneline	[已无最新的版本]
	显示文档 cat xxx
2.返回上一版(重返未来)		git reset --hard xxx(commit_id)		
	若clear了看不到新id(查看命令历史)	git reflog

#### 工作区和暂存区
工作区——	文件夹(电脑可看目录)
版本库——	.git
git add 文件由**工作区**添加到**暂存区**，即stage(index)；git commit将**暂存区**内容提交到**分支**(仓库)
需要提交的文件修改通通放到暂存区，然后，一次性提交暂存区的所有修改。
对比：
git diff 	比较的是**工作区**文件与**暂存区**文件的区别
git diff --cached	**暂存区**和HEAD(**仓库**)的不同
git diff HEAD --xxx	查看**工作区**和**仓库**(版本库**最新版本**)的差异
git checkout	把**暂存区**最新版本转移到**工作区**(撤销工作区修改)		git add的反向命令
git reset HEAD	把**仓库**最新版本转移到**暂存区**	git commit反向命令

Git跟踪修改：每次修改，如果不用git add到暂存区，那就不会加入到commit中。

#### 撤销修改
1.丢弃**工作区**的修改	git checkout -- xxx
	1.修改后还没有被放到暂存区，撤销回到和版本库一模一样的状态
	2.已经添加到暂存区，撤销回到添加到**暂存区**后的状态
即，让这个文件回到最近一次 git commit 或 git add 时的状态。
2.丢弃**暂存区**的修改	
	1.git reset HEAD xxx	(把暂存区的修改撤销(unstage)，重新放回**工作区**)
	2.git checkout -- xxx 	丢弃工作区修改
3.丢弃**版本库**的修改	即版本回退













