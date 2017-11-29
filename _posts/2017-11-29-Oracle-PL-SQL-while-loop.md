---
layout: post
title: Oracle PL/SQL while loop循环实例
categories: 笔记
description: Oracle数据库学习
keywords: 笔记, Oracle, while loop, 循环, PL/SQL
---

用while loop语句进行循环计算的一个实例。最近做题遇到，在此记录。

<!-- more -->

## WHILE-LOOP语法

当**条件为真**时，执行语句。

```sql
WHILE condition LOOP
	some_statements;
END LOOP;
```

## 实例

### 题目

给出一个Power表(表 1)的数据如下：

<p><img src="/images/2017-11-29-Oracle-PL-SQL-while-loop/table1.png" alt="table1" width="446"></p>


**条件:**

1. 3日的电费=1日+2日
2. 4日的电费=2日+3日

**要求:**

编写SQL语句，最终显示出六月所有电费。

### 答题

#### 创建表，存入初始数据

```sql
create table power(mon int,day int,fee int);
insert into power values(6,1,60);
insert into power values(6,2,34);
```

<p><img src="/images/2017-11-29-Oracle-PL-SQL-while-loop/createtable.png" alt="create table" width="307"></p>

#### 计算整月的电费

```sql
declare
	a number;
	b number;
	x number;
	y number;
begin
	a:=1;
	b:=2;
	while (b<=29) loop
		select fee
		into x
		from power
		where day=a;
		select fee
		into y
		from power
		where day=b;
		insert into power values(6,a+2,x+y);
		a:=a+1;
		b:=b+1;
	end loop;
end;
/
```

<p><img src="/images/2017-11-29-Oracle-PL-SQL-while-loop/calculate.png" alt="calculate" width="341"></p>

#### 显示结果

```sql
select * from power;
```

<p><img src="/images/2017-11-29-Oracle-PL-SQL-while-loop/result.png" alt="result" width="254"></p>