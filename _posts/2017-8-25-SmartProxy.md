---
layout: post
title: SmartProxy-安卓智能代理
categories: app
description: 安卓番羽土啬软件
keywords: app，翻墙
---

##SmartProxy

**GitHub地址**

```
https://github.com/hedaode/SmartProxy
```

##下载地址

原始地址：[http://smartproxy.me:80/app/SmartProxy.apk](http://smartproxy.me:80/app/SmartProxy.apk)

备用链接：[http://ov827byht.bkt.clouddn.com/app/apk/smartproxy.apk](http://ov827byht.bkt.clouddn.com/app/apk/smartproxy.apk "备用链接")

##官方介绍

###安卓下的智能代理

SmartProxy是一款工作在Android 4.0及以上系统的TCP透明代理客户端软件，无需ROOT权限。它根据配置文件的规则来决定使用代理还是直连。最关键的是能防DNS污染，永不掉线，还很省电。

**智能分流**

软件不仅可以根据黑白名单进行分流，还可以根据国内或国外IP进行分流。

**永不掉线**

无会话和按需访问机制，无论是移动网络还是WIFI网络，都不会因为频繁的网络变化而掉线。

**防DNS污染**

软件使用本地DNS代理及HTTP/HTTPS协议分析智能识别目标域名，能有效避免DNS缓存污染。

**超级省电**

软件使用NIO异步读写数据，无复杂运算和逻辑，仅仅在需要联网时才会消耗资源，非常适合长期后台运行。

##配置说明

提示：配置文件请使用**UTF-8**编码。当然如果是纯英文，用**ASCII**编码也可以。

提示：SmartProxy1.4已支持**shadowsocks**，目前仅支持**table**方式加密。

------------------------------------

###最简配置：

```
#必须至少包含一行proxy信息，默认仅访问国外网站才会代理，国内直连。
#目前支持HTTP(CONNECT)和Shadowsocks(table加密)两种代理。
#可以设置多个代理，但是目前系统只会使用第一个。

#需要用户名密码验证的代理服务器地址
proxy http://username:password@hostname:port

#无需验证的代理服务器
proxy http://hostname:port 

#shadowsocks地址（目前method仅支持table）
proxy ss://method:password@hostname:port

#Base64加密的shadowsocks地址（目前method仅支持table）
proxy ss://YmYtY2ZiOnRlc3RAMTkyLjE2OC4xMDAuMTo4ODg4
```

###完整示例：

```
#smartproxy config file
#字符'#'用于注释
#参数每行一条，参数名称和值之间用空格分隔，使用"name value1 value2 ... valueN"格式。
#同一参数名称可以在多行出现，系统会将其值自动合并成一个数组。

#TAG:session_name
#设置VPN连接会话名称。默认值：无。非必须。
session_name smartproxy

#TAG:welcome_info
#设置VPN连接后的欢迎信息。默认值：无。非必须。
welcome_info Welcome to smartproxy!

#TAG:ip
#设置VPN的IP地址。默认值：10.8.0.2。非必须。
ip 10.8.0.2

#TAG:dns
#设置VPN的DNS地址，设置后系统将使用该DNS，若不设置系统将使用原来的DNS。默认值：无。非必须。
dns 114.114.114.114
dns 8.8.8.8

#TAG:dns
#DNS缓存时间，单位秒，用于防DNS污染。默认值：30。非必须。
dns_ttl 30

#TAG:route 非必须。
#设置VPN路由，符合该路由的网络都会通过VPN。默认值：0.0.0.0/0。非必须。
route 0.0.0.0/0

#TAG:proxy
#目前支持HTTP(CONNECT)和Shadowsocks(table加密)两种代理。必须。
#可以设置多个代理，但是目前系统只会使用第一个。

#需要用户名密码验证的代理服务器地址
proxy http://username:password@hostname:port

#无需验证的代理服务器
proxy http://hostname:port 

#shadowsocks地址（目前method仅支持table）
proxy ss://method:password@hostname:port

#Base64加密的shadowsocks地址（目前method仅支持table）
proxy ss://YmYtY2ZiOnRlc3RAMTkyLjE2OC4xMDAuMTo4ODg4

#TAG:outside_china_use_proxy
#设置国外网站是否走代理。默认值：on。非必须。
outside_china_use_proxy on

#TAG:direct_domain
#设置直连的域名。非必须。
direct_domain baidu.com qq.com taobao.com
direct_domain sina.com 163.com sohu.com

#TAG:proxy_domain
#设置需要代理的域名。非必须。
proxy_domain google.com twitter.com facebook.com youtube.com

#end of file
```
