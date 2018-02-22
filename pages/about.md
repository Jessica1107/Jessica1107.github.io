---
layout: page
title: About
description: 做一个知足的人
keywords: Ziyang Sun, 孙梓洋
comments: true
menu: 关于
permalink: /about/
---

我是孙梓洋。

这是我随意折腾的一个博客，有兴趣的可以看一看咯。我会记录一些我平时学习中遇到的一些问题，也会有一些杂七杂八的东西，可能会比较乱吧。有什么问题的话，欢迎联系我哦（大概不会有的）。

## 联系

* Email：[i@sunziyang.com](mailto:i@sunziyang.com)
{% for website in site.data.social %}
* {{ website.sitename }}：[@{{ website.name }}]({{ website.url }})
{% endfor %}