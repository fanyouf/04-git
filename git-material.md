# git讲义

## git的作用

## 版本管理

版本控制（Version control）:学习它，爱上它，享受它。顾名思义，**版本控制系统是任何能让你了解到一个文件的历史，以及它的发展过程的系统。**

设计稿

- 201906011初稿.doc
- 201906013初稿-带目录.doc
- 201906016修正稿-带目录和页码.doc
- 201906018修正稿（导师二次修改）-带目录和页码.doc
- 201906020最终版.doc
- 201906022最终版（导师提了几个要求）.doc
- 201906022最终版（打死不改版）.doc
- 201906023最终版（打印店）.doc
- 201906024最终版（加上参考文献及边距）.doc

## git中的基本概念

**Git 是一种专为处理文本文件而设计的版本控制系统。**

注意：只对文本文件。我们的代码恰好就是文本文件。换句话说，如果你希望记录视频文件的修改过程，git是不能帮助你的。

## 登记

- git config --global user.email "you@example.com"
- git config --global user.name "yourname"

## 使用步骤

### 初始化仓库(git init)



### 修改

包括新建文件，修改文件内容等操作均属性于修改的范畴。

`git add` 

### 提交修改

`git commit`

常用操作

git status：检查当前的状态

git log: 查看提交历史

git reflog：查看历史命令

## 月光宝盒

通过两个命令：

git log

git log --oneline

git reset  --hard commit id



背景：每次提交都修改了多个文件。每次提交都会有一个版本号。 

目标：回到某一个版本号，还原多个文件。

命令： `git reset --hard 'commitID'`



背景：每次提交都修改了多个文件。每次提交都会有一个版本号。 

目标：对某一个文件，希望回到某一个版本号，还原这个文件。

命令：要用到如下三条命令

	-  git reset 'commitID' yourfilename.txt
	-  git commit -m ""
	-  git checkout yourfilename.txt



## 工作区和暂存区



隐藏目录`.git`是Git的版本库。Git的版本库里存了很多东西，其中最重要的是：

- 暂存区： 称为stage（或者叫index）
- 分支区：在初始化时，git会为我们自动创建的第一个分支`master`，以及指向`master`的一个指针叫`HEAD`。

![git-repo](https://www.liaoxuefeng.com/files/attachments/919020037470528/0)

回顾我们把文件往Git版本库里添加的时候，是分两步执行的：

第一步：是用`git add`把文件添加进去，实际上就是把本地文件修改添加到暂存区；

第二步：是用`git commit`提交更改，实际上就是把暂存区的所有内容提交到当前分支。因为我们创建Git版本库时，Git自动为我们创建了唯一一个`master`分支，所以，现在，`git commit`就是往`master`分支上提交更改。



你可以简单理解为：第一步把需要提交的文件修改通通放到暂存区，第二步：一次性提交暂存区的所有修改。

## 撤销修改

1. 放弃工作区的修改

   背景：没有运行add

   命令: git checkout -- yourfilename.ext

2. 放弃暂存区的修改

   背景：运行了add,没有commit

   命令：git reset HEAD yourfilename.ext  gitcheckout -- yourfilename.ext

3. 通过版本管理，放弃某个版本的修改

4. 删除文件。你已经在硬盘上手动删除了文件。

   - 这个文件没有被跟踪过。
   - 文件在仓库中
     - 从分支中还原：git checkout -- yourfilename.ext
     - 你在分支中也删除: git rm yourfilename.ext git commit -m ""; 





Git 是一个可安装应用，它允许你对你自己所做的更改进行注释，用以创建易于导航的系统历史。

- **Version Control（版本控制）:** 任何一个能够让你了解文件的历史，以及该文件的发展进程的系统。
- **Git：**一个版本控制程序，通过对变更进行注释，以创建一个易于遍历的系统历史。
- **Commit（提交）：**在指定时间点对系统差异进行的注释 “快照”。
- **Local（本地）：**指任意时刻工作时正在使用的电脑。
- **Remote（远程）：** 指某个联网的位置。
- **Repository (仓库，简称 repo)：**配置了Git超级权限的特定文件夹，包含了你的项目或系统相关的所有文件。
- **Github：**获取本地提交历史记录，并进行远程存储，以便你可以从任何计算机访问这些记录。
- **Push（推送）：**取得本地Git提交（以及相关的所有工作），然后将其上传到在线Github。
- **Pull（拉取）：**从在线的Github上获取最新的提交记录，然后合并到本地电脑上。
- **Master (branch)：主分支，**提交历史 “树”的 “树干”，包含所有已审核的内容/代码。
- **Feature branch（功能分支/特性分支）：**一个基于主分支的独立的位置，在再次并入到主分支之前，你可以在这里安全地写工作中的新任务。
- **Pull Request（发布请求）：**一个 Github 工具，允许用户轻松地查看某功能分支的更改 （the difference或 “diff”），同时允许用户在该分支合并到主分支之前对其进行讨论和调整。
- **Merge（合并）：**该操作**指**获取功能分支的提交，加入到主分支提交历史的顶部。
- **Check out（切换）：**该操作指从一个分支切换到另一个分支。

