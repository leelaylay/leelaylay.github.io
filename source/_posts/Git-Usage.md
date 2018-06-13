---
title: Git Usage
date: 2018-06-13 09:49:17
tags: Tool
---

Git 与 SVN 都是项目版本控制和团队协作的工具，Git 是分布式的版本控制，而SVN是集中式的版本控制，可以说 Git 具有更好的去中心化的能力，也是更符合团队合性质的一个工具，也符合社区和开源的思想。



Git 相比于 SVN 的优点有合并对提交过程的保留（方便追踪历史和 rollback ），快速的热操作（pull 、push） ， 修正提交（修改提交的记录），本地分支（Local Branch），合并能力（Merge），完整配套的开发过程设施（Github、Gitlab、Bitbucket）。（PS：Git 是一个免费、开源、分布式的对项目代码的提供版本管理功能的**软件**，GitHub、Bitbucket 则是一个基于 Git 提供代码托管服务的**网络平台**。）



本文讨论的是 Git 的安装和使用，并介绍了当前流行的 GUI 工具 SourceTree的相关操作。



## 软件安装

一般的图形化界面的工具有[SourceTree](https://www.sourcetreeapp.com/)、[Github Desktop](https://desktop.github.com/)、[Git Tower](https://www.git-tower.com/)等，当然Git也提供纯粹命令行的管理工具[Git](https://git-scm.com/)。个人目前使用体验[SourceTree](https://www.sourcetreeapp.com/)>[Github Desktop](https://desktop.github.com/)，因此本文主要介绍的工具是SourceTree。（最近 M$ 收购了Github，期待 Github 的使用也越来越好）

### 注册账号

如果没有账号的话，首先先去注册GitHub账号和Bitbucket账号。



注册 Github 账号流程如下，进入 https://github.com，选择“Sign up for Github”，输入新建的用户名（Username）和邮箱地址（Email）、密码（Password），点击创建即可，下一步。一般选择计划为“Free”（Github Education可以另外），不要勾选了“Help me set up an organization next”，最后点击“Finish Sign Up”，账号建立完毕。



注册 Bitbucket 账号流程如下，https://bitbucket.org/account/signup/，输入邮箱地址（Email），点击“Continue”，再次确认邮箱地址（Email）、密码（Password），点击“Continue”，最后在邮箱中点击“                  Verify my email address” ，再输入自己的用户（Username）即可完成 Bitbucket账号的注册。（ Bitbucket 似乎目前支持Google Account和 Github账号的关联，感觉也挺方便的）（一般需要翻墙）



### Github Desktop

去https://desktop.github.com/网站下载安装，

### SourceTree

去https://www.sourcetreeapp.com/网站下载安装。



## 界面操作

**Repository** (仓库): 一个项目的所有代码存放在同一个仓库 (Repo) 中。仓库有本地仓库 (Local) 与远程仓库 (Remote) 的区别。如果你使用 GitHub ，那么你的远程仓库便托管在 GitHub 上。



**Commit** (提交): 当你在本地库完成了一些修改后，将所有修改内容提交到缓存区。你可以为每个 Commit 加上一个标题并写明这次修改的主要内容。



**Push** (推送): 当本地仓库缓冲区有未同步的 Commit 时，即本地仓库代码版本新于远程仓库，Push可以将这些 Commit 推送到远程仓库。



**Pull/Fetch** (拉取): 当远程仓库代码版本新于本地仓库时，Pull/Fetch 操作可以使本地仓库更新到远程仓库的版本。



**Sync** (同步): 同步远程仓库版本与本地仓库版本。



**Fork/Clone/Publish** (复制/克隆/发布): Fork 操作将一个他人的远程仓库复制到自己的远程仓库中； Clone 操作将一个他人的远程仓库复制到自己的本地仓库中；Publish 操作将自己的本地仓库发布到 GitHub 等代码托管平台上，即在托管平台上建立起一个对应的远程仓库。



### 命令行工具使用



### 图形化界面工具使用



## 指南与参考

Pro Git book: https://book.git-scm.com/doc

GitHub Help: http://help.github.com/

SourceTree Document: https://confluence.atlassian.com/get-started-with-sourcetree

A Visual Git Reference: http://marklodato.github.io/visual-git-guide/index-en.html