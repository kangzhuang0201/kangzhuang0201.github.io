---
layout: post
title: "Github绑定域名"
date: 2019-05-30
tag: 绑定域名
---

### 介绍

　　今天给大家简单的介绍一下如何将自己的Github网站绑定自己的域名, 因为我自己最近刚刚弄了一个,目前思路还是比较清晰的.

### 创建自己的Github网站

**Git官网上创建仓库**

没有账号的到官网注册一个, 很easy的, 创建仓库, 仓库名一般要以自己的github用户名开头,例如:用户名.github.io

 >*  ![](/images/posts/DomainDeal/CreateRepository.png)

**选择主题**

点击create repository 创建，然后到设置界面,找到Choose a theme选项点击

 >*  ![](/images/posts/DomainDeal/Setting.png)

 >*  ![](/images/posts/DomainDeal/ChooseTheme.png)

上面的都是github给我们提供的一些样例模板，随便选择一个, 然后点击Select theme

 >*  ![](/images/posts/DomainDeal/SelectTheme.png)

选择完毕之后我们提交更改，我们点击提交

 >*  ![](/images/posts/DomainDeal/Submit.png)

提交之后，你的网站可以访问了，访问地址:  用户名.github.io

### 域名申请并解析

域名可以直接到阿里云上购买即可[阿里云官网](https://www.aliyun.com/?utm_content=se_1000301881&source=5176.11533457&userCode=rqgd7c6l)
域名后缀不同价格不同, 根据个人经济情况而定, 一般的一年几块到几十块, 我买的是.top的, 吸引我的原因可能下面这段话:

 >*  ![](/images/posts/DomainDeal/top.png)

购买流程就不说了，购买之后。打开控制台，点击解析域名，如图：

 >*  ![](/images/posts/DomainDeal/JieXi.png)

点击解析,最后添加记录.记录类型选A, 你记录值要填写你的github的ip地址, ping 用户名.github.io ,记录类型为CNAME, 填写你的github的域名地址,如图:

 >*  ![](/images/posts/DomainDeal/AddRecords.jpg)

### 绑定域名
在你的仓库下面创建一个名字为 CNAME的文件,填写你购买的域名, 当然www.可加可不加, 我试过都可以,如图:

 >*  ![](/images/posts/DomainDeal/CNAME.png)

观察 settings 下地址变化,如图:

 >*  ![](/images/posts/DomainDeal/AddrChange.png)

这样就可以通过你自己的域名进行访问了! 即使你通过 用户名.github.io  访问, 地址也会自动跳转为你的域名. 快去试一试吧!



