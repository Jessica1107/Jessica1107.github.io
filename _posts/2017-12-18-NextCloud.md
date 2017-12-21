---
layout: post
title: 从头开始搭建NextCloud私有云盘
categories: Blog
description: 搭建NextCloud
keywords: NextCloud
---

我想大家一定都知道国内网盘相继关闭，百度网盘的和谐、限速大法吧。我还有同步盘的需求，以前百度网盘是有的，现在要会员才能用吧，还要冒着可能被莫名和谐的风险，我还是手动再见。对我来说，网盘还是非常有用，国内的这些网盘用得我十分难受，网上又正好有现成的私有云盘可供我折腾，好吧，其实我就是想折腾。

<!--more-->

我最先听到的其实是owncloud和seafile的。相对于seafile，我更加喜欢owncloud的界面，我也装过owncloud试用来着，结果发现还有许多常用功能需要折腾额外的插件。在折腾的过程中，我发现了nextcloud这个和owncloud在很多方面都十分相像的私有云盘，原来是owncloud原班人马做的更新的版本啊。有新的不用怎么能行，你说是不是？于是我就开始试用nextcloud了。安装过程多有借鉴网上的教程，十分感谢网上的大佬。

## NextCloud安装

### VPS选择

在这方面我也没什么经验，就不便多说。就说几点，我认为比较重要的吧。

1. 你的VPS内存至少能有512MB吧，最好能有1GB，太大我觉得也没必要。
2. 你用来作私有云盘存储的，存储空间总不能太小，这个看你需要多大，因人而异。
3. 你得保证你的VPS的IP在你所在的地区有一定的访问速度，能跑满速自然是最好的，一般VPS商应该都有测试数据让你测试速度的。
4. 作为网盘，少不了上传下载，说不定还要离线下载、在线影院什么的，那么流量也不能少。不过这点一般不用担心，国外的VPS一般不怎么吝啬流量的。
5. 其他的嘛，额，你可能最好能有个域名，这不是必须的（偏题了，不管了就在这提了）。
6. 个人推荐Time4VPS，我现在自用就是这个，这家的存储VPS算是最实惠了吧。

### 宝塔Linux面板安装

对于安装这种东西，对于linux小白来说，自然是越简单越好。于是我选择使用可视化面板**宝塔Linux面板**，在这上面可以一键部署环境，配置网站等等。

安装宝塔面板，我以CentOS 7为例。用Xshell或者PuTTY等无论什么软件通过ssh远程连接你的VPS。输入命令：

```yum install -y wget && wget -O install.sh http://download.bt.cn/install/install.sh && sh install.sh```

其他的系统，可以查看官方提供的[安装命令页面](https://www.bt.cn/bbs/thread-1186-1-1.html)。

会让你确认安装，输入y回车即可。

等待安装完成，会告诉你宝塔面板的访问路径和用户名密码等，以后可以修改。就算密码忘记了只要你能登录你的VPS就能够通过官方的命令修改。

### 部署网站

#### 环境配置

首先登录宝塔面板，会让你一键安装套件，nextcloud官方推荐使用LAMP。LNMP也是能装的，据说会有诡异的问题，我也没试过。

![LAMP](/images/2017-12-18-NextCloud/LAMP.png)

建议按照我的选择，点击一键安装，宝塔面板会帮你将所需环境安装完成。

在安装完成后，还有几个内容需要添加，后期将会用到。点击左侧导航栏的软件管理，再点击PHP-7.1右侧的设置。

![Software](/images/2017-12-18-NextCloud/software.png)

这样将会弹出php的管理界面，点击左侧栏的安装扩展，安装如图所示的三个扩展。

![PHP](/images/2017-12-18-NextCloud/php.png)

#### 添加站点

点击左侧栏的网站，然后点击添加站点。在域名框中添加你需要的域名，你需要在你域名的DNS处将这个子域名解析到你的VPS的IP。

![Add Website](/images/2017-12-18-NextCloud/addwebsite.png)

创建完成后，点击你的网站目录，删除如图所示的自动生成的文件，并将nextcloud的网站文件上传到这个目录。

打开NextCloud的[官网](https://nextcloud.com/install/#instructions-server)下载最新的安装包。

在页面中选择Get Nextcloud Server栏目下的Download按钮点击它。出现如下图界面点击Download Nextcloud开始下载：

![Download](/images/2017-12-18-NextCloud/download.png)

下下来的文件是个压缩包，你只需要把文件夹中的文件都上传到刚刚的网站目录即可。**注意：只要文件夹中的文件，不要文件夹。**

#### 添加数据库

点击面板左侧栏的数据库，点击phpMyAdmin，出现数据库的管理界面，通过root用户登录，root密码可以通过刚刚页面的root密码按钮得到。

接下来新建一个供nextcloud使用的数据库。点击数据库，输入数据库名，再点击创建就完成了。

![SQL](/images/2017-12-18-NextCloud/sql.png)

#### 创建管理员账户

现在你已经可以访问你的域名来访问nextcloud了，你将会看到如下所示的界面，你需要在这里创建管理员账户。

![admin](/images/2017-12-18-NextCloud/admin.png)

管理员账户的用户名密码，自定。点开存储&数据库，在这里可以修改数据目录。配置数据库选择MySQL/MariaDB，然后填入刚刚你创建的数据库，最后点击安装完成。**注意：localhost后一定要写上端口3306，如图所示**

![admin config](/images/2017-12-18-NextCloud/adminconfig.png)

现在你已经可以登录你的nextcloud了，尽情享用吧。