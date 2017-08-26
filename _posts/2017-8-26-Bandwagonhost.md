---
layout: post
title: 初试自建shadowsocks服务器
categories: 科学上网
description: 自建shadowsocks服务器
keywords: shadowsocks，翻墙
---

## 原用服务

我原本购买的shadowsocks服务是[https://portal.shadowsocks.com.au](https://portal.shadowsocks.com.au)，服务还不错，大家可以试试。这两天快要到期了，正在考虑是否要续费的问题。

我犹豫的原因主要有这么几点：

1. 我买的这个shadowsocks服务提供了九个服务器地址，分别处于美国、日本、新加坡、香港。但是，可以正常访问，速度尚可的，没有几个，我印象里也就一个美国的和一个香港的服务器比较顺畅。
2. 由于一些众所周知的原因，服务商的地址一直在换。虽然会在主页提前通知，但如果没有经常关注，我怕哪天我就找不到了。
3. 服务器不限制带宽和流量，但是，我平均流量每个月也就10G多，并没有那么大的需求。
4. 还有就是没有对服务器的管理权，心里慌啊，不如自己搭一个。
5. 我购买的服务的价格是每年15.7$，限制同时使用的用户数，租一个VPS的花费也差不多了吧，还可以和朋友共享来分摊费用，岂不美哉。

----------------------------------------

## Bandwagon Host

今早看到一篇博文，叫做[ShadowSocks（影梭）不完全指南](http://www.auooo.com/2015/06/26/shadowsocks%EF%BC%88%E5%BD%B1%E6%A2%AD%EF%BC%89%E4%B8%8D%E5%AE%8C%E5%85%A8%E6%8C%87%E5%8D%97/#configuration)。文章中采用自己搭建shadowsocks服务器的方式，还推荐了不少各个价位不同服务商提供的VPS服务。

我选择了[搬瓦工](https://bandwagonhost.com)的一款每月2.99$的服务。配置规格如下：

- SSD: 10 GB RAID-10
- RAM: 1 GB
- CPU: 1x Intel Xeon
- Transfer: 1000 GB/mo
- Link speed: 1Gigabit
- Location: US, California

这个配置在我看来已经完全足够使用，性价比非常高，这么大的流量怕是10个人一起用也够哦。此外，[搬瓦工](https://bandwagonhost.com)支持**支付宝**支付，可谓是十分良心了。

注意：如果玩游戏，延迟要求比较高的话，不适合选择这一款VPS。亲测平均延迟200ms。

### 安装Shadowsocks服务

估计这个档次的 VPS 多用来进行番羽土啬，搬瓦工支持一键安装Shadowsocks，完全傻瓜式操作。

1. 创建 VPS 后，登录搬瓦工的 **Client Area**。在 **Services-My Services** 找到自己的VPS。

 ![My Service](/images/2017-8-26-Bandwagonhost/Myservice.png)

2. 下图就是我选购的 VPS 服务器，点击右侧的 **KiviVM Control Panel** 进入控制面板。

 ![VPS](/images/2017-8-26-Bandwagonhost/VPS.png)

3. 一键安装服务只支持 **CentOS 6**，如果不是的话，需要在控制面板中的 **Install new OS** 重新安装系统。

 ![Install OS](/images/2017-8-26-Bandwagonhost/Install OS.png)

4. 我的 SS 服务已经安装过了，我就展示一下没有安装过的 SSR 的安装界面，SS 的安装界面也类似。只要点击 **Install ShadowsocksR Server** ，系统就会自动进行傻瓜式安装。

 ![Install](/images/2017-8-26-Bandwagonhost/Install.png)

5. 安装完成以后，在这个界面将会显示服务的参数。下方提供了各个版本的客户端下载链接和详细的配置使用教程。

 ![Server](/images/2017-8-26-Bandwagonhost/Server.png)

### 使用体验

1. 首先配置简单，不用我操作服务器。
2. 网速令人满意，在 YouTube 上看 1080P 视频流畅无卡顿。
3. 有时会抽风，加载稍慢，过会便会自己恢复。
4. 延迟亲测稍高，不适合延迟要求较高的用户。