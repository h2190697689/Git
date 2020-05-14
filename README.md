# Git的基本使用

## git init 
- git 初始化仓库

## 删除.git 文件夹(删除本地git)
- find . -name ".git" | xargs rm -Rf

## git add 文件名  (或者 git add .)
- 将文件添加到仓库

## git commit -m "提交信息"
- 文件提交到仓库

## git status 
- 查看仓库状态

## git diff 
- 查看修改内容
- git diff HEAD -- 文件名   (查看工作区和版本库区别)

## git log   （可添加  --pretty=oneline）
- 查看 git 提交的历史记录日志 (不可以查看未来记录)
- git log --graph --pretty=oneline --abbrev-commit

## git reset
- 版本回退
- git reset --hard HEAD^  回退到上一个版本,HEAD表示当前版本
- git reset --hard HEAD^^   回退上上一个版本
- git reset --hard HEAD~100  回退上100个版本
- git reset --hard commitId  回退到某一个版本

## git reflog
- 查看历史命令

## git checkout -- 文件名 
- 让文件回到最近一次 git commit 或 git add时的状态

## git reset HEAD 文件名
- 把暂存区的修改回退到工作区

## git rm 文件名
- 从版本库删除文件
- 也可以直接使用 git add . 代替操作

## git remote add origin git@github.com:h2190697689/git-order.git
- 关联远程库

## git push -u origin master
- 把本地库内容推送到远程
- 第一次之后的提交只需要 git push origin master 即可;

## git clone
- 克隆项目

## git checkout -b dev 
- 创建分支，并且切换到分支

## git branch dev
- 创建分支

## git branch -d dev 
- 删除分支
- git branch -D dev 强行删除分支

## git checkout dev
- 切换分支

## git branch
- 查看当前分支

## git merge dev
- 先切换到master分支,合并分支
- git merge --no-ff -m "merge with no-ff" dev (禁用Fast forward模式,因为该模式删除分支后,会丢掉分支信息)

## git stash 
- 暂时储存工作区，再转换分支
- 可在git add . 后进行操作
- 可切换分支，在其他分支上进行git commit 操作

## git stash list
- 查看暂存列表

## git stash apply 
- 恢复暂存

## git stash drop
- 删除暂存列表内容

## git stash pop
- 恢复暂存同时把stash内容也删除

## git remote
- 查看远程库的信息
- git remote -v  查看详细信息

## git checkout -b dev origin/dev
- 创建远程origin的dev分支到本地
- 相当于创建并指定与远程库origin/dev的连接
- 在git-clone 后使用

## git pull
- 协作提交时存在冲突,git pull把最新提交从 origin/dev 抓下来

## git branch --set-upstream-to=origin/dev dev
- 指定本地dev分支与远程origin/dev分支的链接
- git pull 和 git push 使用时后面可以不带参数
- 当然也可以不指定连接，但git pull,git push 需指定origin dev

## git rebase
- 把分叉提交变为一条直线

