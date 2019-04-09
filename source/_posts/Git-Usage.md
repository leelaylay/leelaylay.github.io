---
title: Git Usage
tags:
  - Tool
  - Git
abbrlink: 39759
date: 2018-06-13 09:49:17
---

Git 与 SVN 都是项目版本控制和团队协作的工具，Git 是分布式的版本控制，而SVN是集中式的版本控制，可以说 Git 具有更好的去中心化的能力，也是更符合团队合性质的一个工具，也符合社区和开源的思想。



Git 相比于 SVN 的优点有合并对提交过程的保留（方便追踪历史和 rollback ），快速的热操作（pull 、push） ， 修正提交（修改提交的记录），本地分支（Local Branch），合并能力（Merge），完整配套的开发过程设施（Github、Gitlab、Bitbucket）。（PS：Git 是一个免费、开源、分布式的对项目代码的提供版本管理功能的**软件**，GitHub、Bitbucket 则是一个基于 Git 提供代码托管服务的**网络平台**。）



本文讨论的是 Git 的安装和使用，并介绍了当前流行的 GUI 工具 SourceTree的相关操作。



## 软件安装

一般的图形化界面的工具有 [SourceTree](https://www.sourcetreeapp.com/)、[Github Desktop](https://desktop.github.com/)、[Git Tower](https://www.git-tower.com/)等，当然 Git也提供纯粹命令行的管理工具 [Git](https://git-scm.com/)。个人目前使用体验 [SourceTree](https://www.sourcetreeapp.com/) > [Github Desktop](https://desktop.github.com/)，因此本文主要介绍的工具是SourceTree。（最近 M$ 收购了 Github，期待 Github 的使用也越来越好）

### 注册账号

如果没有账号的话，首先先去注册GitHub账号和Bitbucket账号。



注册 Github 账号流程如下，进入 <https://github.com>，选择“Sign up for Github”，输入新建的用户名（Username）和邮箱地址（Email）、密码（Password），点击创建即可，下一步。一般选择计划为“Free”（Github Education可以另外），不要勾选了“Help me set up an organization next”，最后点击“Finish Sign Up”，账号建立完毕。



注册 Bitbucket 账号流程如下，<https://bitbucket.org/account/signup/>，输入邮箱地址（Email），点击“Continue”，再次确认邮箱地址（Email）、密码（Password），点击“Continue”，最后在邮箱中点击“                  Verify my email address” ，再输入自己的用户（Username）即可完成 Bitbucket账号的注册。（ Bitbucket 似乎目前支持Google Account和 Github账号的关联，感觉也挺方便的）（一般需要翻墙）



### Github Desktop

去 <https://desktop.github.com/> 网站下载安装。连接账号的时候如果没有SSH KEY，请选择**HTTPS** 。

### SourceTree

去 <https://www.sourcetreeapp.com/> 网站下载安装。连接账号的时候如果没有SSH KEY，请选择**HTTPS** 。

## Git 相关概念

**Repository** (仓库): 一个项目的所有代码存放在同一个仓库 (Repo) 中。仓库有本地仓库 (Local) 与远程仓库 (Remote) 的区别。如果你使用 GitHub （Bitbucket），那么你的远程仓库便托管在 GitHub （Bitbucket）上。

**Commit** (提交): 当你在本地库完成了一些修改后，将所有修改内容提交到缓存区。你可以为每个 Commit 加上一个标题并写明这次修改的主要内容。

**Push** (推送): 当本地仓库缓冲区有未同步的 Commit 时，即本地仓库代码版本新于远程仓库，Push可以将这些 Commit 推送到远程仓库。

**Pull/Fetch** (拉取): 当远程仓库代码版本新于本地仓库时，Pull/Fetch 操作可以使本地仓库更新到远程仓库的版本。

**Sync** (同步): 同步远程仓库版本与本地仓库版本。

**Fork/Clone/Publish** (复制/克隆/发布): Fork 操作将一个他人的远程仓库复制到自己的远程仓库中； Clone 操作将一个他人的远程仓库复制到自己的本地仓库中；Publish 操作将自己的本地仓库发布到 GitHub 等代码托管平台上，即在托管平台上建立起一个对应的远程仓库。

## 界面操作

### 命令行使用

命令行的使用可以帮助我们更好地理解 Git 相关概念。

**Clone**

Clone 是指将一个他人的远程仓库复制到自己的本地仓库中。

```bash
# 使用 https，而 ssh 一般需要专门的 ssh key。
git clone https://github.com/leelaylay/leelaylay.github.io.git
```

**Init**

Init 独自创建本地的仓库。

```bash
# 将当前文件下下作为本地仓库位置，同时建立".git"文件夹差量保存项目日志。
git init
```

**Add**

add 就是将本地 change 添加到项目中。

```bash
# XXXX 代表某个文件或文件夹，另外".gitignore"文件能指定git项目忽略匹配的文件
git add XXXX
# rm 代表删除某个文件
git rm XXXX
```

**Commit**

commit 就是提交保存一次 change 到提交记录中，区别于 add 的在于 add 的时候没有 commit 到本地仓库提交记录，一般都是先 add 再 commit。

```bash
git commit
```

**Pull/Fetch**

Pull/Fetch 操作可以使本地仓库更新到远程仓库的版本，可以理解 Fetch 只是将远程的所有提交记录下载到本地，没有合并，而 Pull 则需要合并。

```bash
# fetch 使本地仓库更新到远程仓库的版本时，代码没有合并（merge）。<remote>代表远程仓库。
git fetch <remote>
# pull 使本地仓库更新到远程仓库的版本时，代码需要合并（merge）。<remote>代表远程仓库，<branch>代表远程分支，可以均不指定代表默认远程的某个分支。
git pull <remote> <branch>
```

**Push**

与 pull 相对的便是 push，指的是将本地仓库的更新推送到远程仓库的某个分支。

```bash
# push 使本地仓库的更新推送到远程仓库的某个分支时。<remote>代表远程仓库，<branch>代表远程分支，可以均不指定代表默认远程的某个分支。
git push <remote> <branch>
```





git 相关指令如下：

![](https://raw.githubusercontent.com/leelaylay/IMGUR/master/img/20180829223445.png)

### 图形化界面使用

图形化界面使用方便，实用友好，本文以 SourceTree 为例介绍。

1. 在这里，我们把远程仓库搭建在Github（Bitbucket类似）上面，现在我的远程仓库为： https://github.com/leelaylay/leelaylay.github.io

2. 打开SourceTree，点击New Repository-->Clone from URL,  然后复制仓库地址 https://github.com/leelaylay/leelaylay.github.io.git   到SourceTree中的Source URL中，本地仓库的位置和名称可以随意修改，点击clone即可把远程仓库中的项目clone到本地了。

3. clone项目完成后，SourceTree中看到如下：

  上面的任务栏分别有commit（提交）、Pull（更新代码）、Push（推送代码）、Fetch（抓取代码），Branch（新建分支）、Merge（合并代码）、Stash（暂存代码状态）。
  
  左侧中的WORKSPACE表示本地的工作区，file status中可以看到本地文件的改变状态，History中是commit历史。下面的BRANCHES显示的是本地的分支。REMOTES显示的是远程的分支。
  
  下方的状态栏显示本次提交的修改文件。以及修改文件中修改的代码。

  ![](https://raw.githubusercontent.com/leelaylay/IMGUR/master/img/20180829223431.png)

   

4. 可以在SourceTree中可以看到工作区中的改变，比如哪些文件被修改，以及修改的内容。

5. 本地做了修改后，可以看到文件都还是在Unstaged files中，勾选你要提交的文件，然后文件就会到Staged file中，这个操作对应的命令就是git add, 即把文件从工作区放到暂存区。

6. 此时就可以进行commit操作了。点击左上角的commit。在commit的时候强烈建议写上注释，作为commit的可读日志。

   ![](https://raw.githubusercontent.com/leelaylay/IMGUR/master/img/20180829223433.png)

   完成commit之后，提交历史就会变成如下所示。”1↑“表示本地提交比远程提交领先一次commit。

   ![](https://raw.githubusercontent.com/leelaylay/IMGUR/master/img/20180829223435.png)

7. 本地完成commit之后，就需要向远程仓库提交(Push)代码了。个人建议，在Push之前，先进行Pull。

   要注意，pull = fetch + merge，你拉取代码的时候选择的是pull还是fetch，还是使用rebase，这个要根据你的个人习惯，最主要的是要根据你团队的Git工作流来操作。

8. 完成更新代码后 ，就可以向远程提交代码了。点击上方的Push。

   ![](https://raw.githubusercontent.com/leelaylay/IMGUR/master/img/20180829223438.png)

   在提交的时候，选择要提交的分支即可。此时可能需要你输入Github或者其他的远程的用户名和密码，输入即可。（注意：此时输入的用户名和密码与.git配置里面的name和email不是同一个概念。此时要你输入的用户名和密码只和你的远程服务器有关，和git无关，因为你要向服务器推送代码，必然要有权限，这个用户名和密码相当于权限。但是.git里面的name和email只是作为你git这个工具标记而已，和远程服务器没有关系。）

   ![](https://raw.githubusercontent.com/leelaylay/IMGUR/master/img/20180829223440.png)

9. Push完代码后，可以在提交历史中看到自己和别人的提交。此时，本地和远程已经保持了同步，所以原来的"1 ↑"就消失了。来到Github中，发现代码已经成功提交了。此时，如果其他开发者向远程仓库提交了代码，在你本地的master分支下，可以看到"1↓"，表示你本地的分支已经落后于远程分支1 commit了。可以选择Pull来更新代码。

   （以上部分是主要流程，以下部分是关于 branch 的部分知识）

10. 如果远程仓库有其他的分支，那么我需要checkout（检出）远程分支到本地，如图，远程有dev分支，双击左侧远程的dev分支，即可检出。检出的时候还可以重命名本地该分支的名字。

11. 在SourceTree中经常会出现track这个词，表示“跟踪”，表示本地某个分支跟踪远程某个对应的分支。所以，判断是ahead还是behind commit的时候，都是去和track的那个分支进行比较的。双击本地的某个分支即可完成分支切换。

12. 当你在本地新建某个分支的时候，也可以推送到远程，然后远程就会有该分支了。你要确定是否有某个分支，你也可以去Github或者其他远程服务器查看。

13. 当然你也可以在SourceTree中删除本地或者远程的一个分支，删除分支是个很谨慎的操作，需要慎重。



## 指南与参考

Pro Git book: https://book.git-scm.com/doc

GitHub Help: http://help.github.com/

SourceTree Document: https://confluence.atlassian.com/get-started-with-sourcetree

A Visual Git Reference: http://marklodato.github.io/visual-git-guide/index-en.html