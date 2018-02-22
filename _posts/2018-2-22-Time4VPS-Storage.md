---
layout: post
title: Time4VPS大容量存储VPS推荐
categories: 国外VPS测评
description: 大容量存储型VPS
keywords: Storage,大容量存储,VPS,Time4VPS
---

如果想要自己搭建私有云，一个大容量存储型VPS将是最合适的。

在这里我想要推荐一下我正在使用的这个Time4VPS的大容量存储VPS，还是十分有性价比的。

<!--more-->

<a href="https://billing.time4vps.eu/?affid=2759"><img src="https://www.time4vps.eu/banners/affiliate/1200x628.gif" width="1200" border="0" title="Time4VPS.EU" alt="Time4VPS.EU - VPS hosting in Europe" /></a>

## 概览

Time4VPS的大容量存储VPS机房位于欧洲，全都是OpenVZ架构，CPU为Intel® Xeon® E5-2603 v4，主频为1.70GHz，内存为DDR4-1866 ECC REG，硬盘是RAID，最高200 IOPS。我觉得作为搭建私有云的平台应该是足够了。搭建代理就算了吧，国内连接速度比较慢，而且如果被封了加IP的话，一次要19.99欧元。

控制面板功能比较完善，提供的OS较多，甚至有owncloud镜像提供，做私有云更加方便了。

这家IDC据说对国内不太友好，我当时买的时候说我的IP不能购买，我联系了在线客服说明了一下，倒也很快就解决了。

## 推广链接

这是我的推广链接，欢迎感兴趣的点我的推广链接购买，感谢！

推广链接:[https://billing.time4vps.eu/?affid=2759](https://billing.time4vps.eu/?affid=2759)

## 套餐

|         |1 TB Plan |2 TB Plan |4 TB Plan |
|---------|----------|----------|----------|
|CPU      |1×1.70 GHz|1×1.70 GHz|1×1.70 GHz|
|RAM      |1024 MB   |2048 MB   |4096 MB   |
|HDD      |1024 GB   |2048 GB   |4096 GB   |
|Bandwidth|10 TB     |20 TB     |40 TB     |
|端口速度  |100Mbps   |200Mbps   |400Mbps   |
|虚拟化    |OpenVZ    |OpenVZ    |OpenVZ    |
|季付价格  |5.99 欧元/月|9.99 欧元/月|17.99 欧元/月|
|年付价格  |5.24 欧元/月|8.74 欧元/月|15.74 欧元/月|
|两年付价格|4.49 欧元/月|7.49 欧元/月|13.49 欧元/月|

## 测试

测试机器为1 TB Plan的。其他没有买，没办法测试。我搭建nextcloud已经完全够了，各位看官自己斟酌。

### 网络（下行）和 IO 测试

![time4vps](/images/2018-2-22-Time4VPS-Storage/time4vps.png)

### Unix Bench 测试

![Unix Bench](/images/2018-2-22-Time4VPS-Storage/Bench.png)

### 国内Ping

国内连接速度较慢，我原来是作为同步盘的，所以无所谓。

![ping](/images/2018-2-22-Time4VPS-Storage/ping.png)

## 后话

我这台机子快要过期了，暂时不准备续费了。我还是想要访问速度更快一点，所以迁到了国内的阿里云，虽说国内域名要备案，但是我自己用，直接访问IP也问题不大。阿里云的ECS挂载OSS存储装Nextcloud也是一个性价比很高的私有云解决方案。