---
layout: post
title: SQL Server数据库角色成员身份
categories: 笔记
description: SQL Server数据库学习
keywords: 笔记, ASP.NET, MVC
---

本文总结了SQL Server数据库的自带角色成员身份权限。

|数据库级别的角色名称|说明|
|:-----------------|:---|
|db_accessadmin|db_accessadmin固定数据库角色的成员可以为Windows登录名、Windows组和SQL Server登录名添加或删除数据库访问权限。|
|db_backupoperator|db_backupoperator固定数据库角色的成员可以备份数据库。|
|db_datareader|db_datareader固定数据库角色的成员可以从所有用户表中读取所有数据。|
|db_datawriter|db_datawriter固定数据库角色的成员可以在所有用户表中添加、删除或更改数据。|
|db_ddladmin|db_ddladmin固定数据库角色的成员可以在数据库中运行任何数据定义语言(DDL)命令。|
|db_denydatareader|db_denydatareader固定数据库角色的成员不能读取数据库内用户表中的任何数据。|
|db_denydatawriter|db_denydatawriter固定数据库角色的成员不能添加、修改或删除数据库内用户表中的任何数据。|
|db_owner|db_owner固定数据库角色的成员可以执行数据库的所有配置和维护活动，还可以删除数据库。|
|db_securityadmin|db_securityadmin固定数据库角色的成员可以修改角色成员身份和管理权限。向此角色中添加主体可能会导致意外的权限升级。|
|public|授予public角色的权限由所有其他用户和角色继承，因为默认情况下，它们属于public角色。 仅为public角色授予您希望所有用户都具有的权限。|