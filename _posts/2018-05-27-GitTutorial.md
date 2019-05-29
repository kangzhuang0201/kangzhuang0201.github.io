---
layout: post
title: "Git教程"
date: 2018-05-27
tag: 测试
---

### 介绍

　　经过个人用了一段Git觉着它用好了真的是挺强大的, 而且Git上还有很多开源项目的源码(你懂得...)

　　Git被多数人称为版本管理工具。假如现在你有一个文件夹，里面可以是项目，也可以是你的个人笔记(如我这个博客)，或者是你的简历、毕业设计等等，都可以使用git来管理。

　　目前常用的版本控制器有Git和SVN，即使这两个你没有全用过，至少也会听过，我这里以Git为例，个人比较喜欢Git，你也可以看看这篇文章：[为什么Git比SVN好](http://www.worldhello.net/2012/04/12/why-git-is-better-than-svn.html)。

### 安装Git

**在Mac OS X上安装Git**      

提供两种方法参考：      

> 1、通过homebrew安装Git，具体方法请参考[homebrew的文档](http://brew.sh/)      
> 2、直接从AppStore安装Xcode，Xcode集成了Git，不过默认没有安装，你需要运行Xcode。     

**在Windows上安装Git**      

> 从[https://git-for-windows.github.io](https://git-for-windows.github.io) 下载，然后按默认选项安装即可，安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！

**在Ubuntu 上安装Git**
> sudo apt-get install git命令进行安装

### 配置Git      

安装完成后，还需要最后一步设置，在命令行输入：

>* $ git config --global user.name "Your Name"
>* $ git config --global user.email "email@example.com"

"Your Name"： 是每次提交时所显示的用户名，因为Git是分布式版本控制系统，当我们push到远端时，就需要区分每个提交记录具体是谁提交的，这个"Your Name"就是最好的区分。          

"email@example.com"： 是你远端仓库的email       

--global(global前面是两条-)：用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然我们也可以对某个仓库指定不同的用户名和Email地址。



### 开始使用-建立仓库：

一.登陆自己的github账号
>* https://github.com/

二.点击new repository进行创建一个新的仓库，用来存放自己的项目;然后会有一个url如：

>* https://github.com/你的用户名/你的项目名.git

三.也是最重要的部分，用命令将项目上传；

1.启动git-cmd.exe  cd 到上传项目的根目录下，然后初始化本地仓库，
>* cd /d D:\idea_project_workspace\springmvcDemo
>* git init

2.添加当前工作目录文件到index，添加管理，

>* git add .(记得有个点哦，并且和add之间有空格)

3.查看一下当前目录所有没有被git管理的文件以及被git管理并且被修改但是还没有提交的文件，

>* git status       （若出现了很多红色文件，那么就需要再次进行2的步骤，git add .直到没有问题。）

4.提交文件，把本地仓库暂存区的文件提交到本地仓库。

>* git commit -m "message"       其中message就是你提交文件时候的备注。以便知道本次提交是什么作用……

5.关联远程仓库，其中origin后跟的是，远程仓库的别名。
>* git remote add origin https://github.com/用户名/helloworld.git
>* 提示出错信息：fatal: remote origin already exists.
>* 解决办法如下：
>*   ①先输入$ git remote rm origin
>*   ②再输入$ git remote add origin https://github.com/用户名/helloworld.git 就不会报错了！

6.push文件。

>* git push -u origin master

注意

>* 如果使用git extension 拉取或者push代码，提示
>* "C:\Program Files\Git\bin\git.exe" pull --progress "origin" +refs/heads/zjw
>* fatal: unable to access 'https://github.com/**/': error setting certificate verify locations:
>* CAfile: C:/Program Files/Git/mingw64/libexec/ssl/certs/ca-bundle.crt
>* CApath: none
>* Done
>* Press Enter or Esc to close console...
>* 这是因为git 提交代码时需要安全认证，可以通过以下方法设置，取消验证
>* 解决：
>* 找到 git的config 配置文件，路径应该在
>* C:\ProgramData\Git\config ，添加下面两行
>* [http]
>*     sslVerify = false
>*     sslCAinfo = /bin/curl-ca-bundle.crt
>* 保存后，再提交代码就可以了。

### 下载代码

1.命令下载代码
 >*  git clone https://github.com/*****/****.git

2.通过ssh下载则需要配置ssh 秘钥, 生成SSH密钥过程：
 >*  1.查看是否已经有了ssh密钥：cd ~/.ssh
 >*  如果没有密钥则不会有此文件夹，有则备份删除
 >*  2.生成密钥(切记要加你公司的邮箱)：
 >*  ssh-keygen -t rsa -C "YourName@example.com" 按3个回车，密码为空。 最后得到了两个文件：id_rsa和id_rsa.pub
 >*  查看id_rsa.pub公钥 (linux下)cat ~/.ssh/id_rsa.pub, 打开id_rsa.pub文件，并且复制全部内容。
 >*  3.打开GitLab账户，打开SSH Keys:
 >*  将刚刚复制的内容添加到Key的文本域中，然后点击Add key, 这样就添加了一个SSH key

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

3.删除"footer-fix"分支
 >* git branch -d footer-fix

4.切换到新分支
 >* git checkout footer-fix

5.切换到主干master,合并分支
 >* git checkout master
 >* git merge branchName

6.查看配置的信息
 >* git config --list (list前面是两条-)
