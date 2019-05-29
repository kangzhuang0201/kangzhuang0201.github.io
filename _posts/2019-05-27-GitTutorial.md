---
layout: post
title: "Git教程"
date: 2019-05-27
tag: 工具 
---

### 介绍       

　　Git是做项目的版本管理，你也可以称它们为版本管理工具。假如现在你有一个文件夹，里面可以是项目，也可以是你的个人笔记(如我这个博客)，或者是你的简历、毕业设计等等，都可以使用git来管理。

　　目前常用的版本控制器有Git和SVN，即使这两个你没有全用过，至少也会听过，我这里以Git为例，个人比较喜欢Git，你也可以看看这篇文章：[为什么Git比SVN好](http://www.worldhello.net/2012/04/12/why-git-is-better-than-svn.html)。

### 安装Git

**在Mac OS X上安装Git**      

提供两种方法参考：      

> 1、通过homebrew安装Git，具体方法请参考[homebrew的文档](http://brew.sh/)      
> 2、直接从AppStore安装Xcode，Xcode集成了Git，不过默认没有安装，你需要运行Xcode。     

**在Windows上安装Git**      

> 从[https://git-for-windows.github.io](https://git-for-windows.github.io) 下载，然后按默认选项安装即可，安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！

**在Ubuntu 上安装Git**
　　sudo apt-get install git命令进行安装

### 配置Git      

安装完成后，还需要最后一步设置，在命令行输入：

>* $ git config --global user.name "Your Name"
>* $ git config --global user.email "email@example.com"

"Your Name"： 是每次提交时所显示的用户名，因为Git是分布式版本控制系统，当我们push到远端时，就需要区分每个提交记录具体是谁提交的，这个"Your Name"就是最好的区分。          

"email@example.com"： 是你远端仓库的email       

--global：用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然我们也可以对某个仓库指定不同的用户名和Email地址。         



### 开始使用-建立仓库：

你在目标文件夹下使命令：    

>* git init  （创建.git文件）      

就会创建一个 `.git` 隐藏文件，相当于已经建立了一个本地仓库。

**添加到暂存区：**      

>* git add .   （全部添加到暂存区）    
>* git commit -m ' first commit'  （提交暂存区的记录到本地仓库）     


### 下载代码

  1.命令代码
    >*git clone https://github.com/*****/****.git
  2.通过ssh下载则需要配置ssh 秘钥, 生成SSH密钥过程：
    >* 1.查看是否已经有了ssh密钥：cd ~/.ssh
    >* 如果没有密钥则不会有此文件夹，有则备份删除
    >* 2.生存密钥(切记要加你公司的邮箱)：
    >* ssh-keygen -t rsa -C "YourName@example.com" 按3个回车，密码为空。 最后得到了两个文件：id_rsa和id_rsa.pub
    >* 查看id_rsa.pub公钥 (linux下)cat ~/.ssh/id_rsa.pub, 打开id_rsa.pub文件，并且复制全部内容。
    >* 3.打开GitLab账户，打开SSH Keys:
    >* 将刚刚复制的内容添加到Key的文本域中，然后点击Add key, 这样就添加了一个SSH key
  3.IDEA下载代码
    >* VCS--> Checkout from Version Control -->Git
### 开发常用命令
1.列出所有分支
 git branch

 出现如下:
 >*  (HEAD detached at analytics_v2)
 >*  dev
 >*  master
2.创建新的"footer-fix"分支
 >* git branch footer-fix

删除"footer-fix"分支
 >* git branch -d footer-fix

3.切换到新分支
 >* git checkout footer-fix

4.切换到主干master,合并分支
 >* git checkout master
 >* git merge branchName

5.查看配置的信息
 >* git config --list
