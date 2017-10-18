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

## 联系

* Email：[i@sunziyang.com](mailto:i@sunziyang.com)
{% for website in site.data.social %}
* {{ website.sitename }}：[@{{ website.name }}]({{ website.url }})
{% endfor %}