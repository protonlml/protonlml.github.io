---
title: 对Mysql中的sql语句的理解
date: 2019-10-01 00:00:00
author: 𝚲𝚳𝚲
tags:   # 添加博文标签
	- mysql8.0.22
categories:   # 添加博文分类
	- mysql8.0.22


---

<h1><center>对Mysql中的sql语句的理解</center></h1>





##  理解SQL语句的执行顺序

> 1.理解sql的执行顺序，对理解整个sql语句想要表达的什么内容，尤为重要。



![image-20241008225541514](https://raw.githubusercontent.com/protonlml/blogimages/master/imgs/202410082255599.png)

上图 ④和⑤颠倒一下顺序

```mysql
# where或者on  后面的过滤条件,可以读作,得到 满足 条件所存在的行.如下
# on 后面可以读作, e员工表中有 部门的行,取出来.
   通用句式 表中 有 xxx 的值取出来 。 
```



![image-20241008231137358](https://raw.githubusercontent.com/protonlml/blogimages/master/imgs/202410082311840.png)

```mysql
如上：
from employees e join departments d 
on d.department_id = e.department_id 后面可以读作：部门中有员工的数据 取出来
----------------------------------------------------------------------------
from employees e right join departments d 
on d.department_id = e.department_id  读作 部门中有员工的行取出来，右因 right join departments（右外连接departments） 所以departments部门中没有员工的行也去出来。就是连接后  departments这一边所有的数据都出来，不管这个部门有没有员工都取出来
```



## 你需要记住 SELECT 查询时的两个顺序:

### 1. 关键字的顺序是不能颠倒的:

####  ``SELECT ... FROM ... WHERE ... GROUP BY ... HAVING ... ORDER BY ... LIMIT...``

### 2.SELECT 语句的执行顺序(在 MySQL 和 Oracle 中,SELECT 执行顺序基本相同):

#### ``FROM -> WHERE -> GROUP BY -> HAVING -> SELECT 的字段 -> DISTINCT -> ORDER BY -> LIMIT``

### 3.比如你写了一个 SQL 语句,那么它的关键字顺序和执行顺序是下面这样的:

```mysql
SELECT DISTINCT player_id, player_name, count(*) as num # 顺序 5
FROM player JOIN team ON player.team_id = team.team_id # 顺序 1
WHERE height > 1.80 # 顺序 2
GROUP BY player.team_id # 顺序 3
HAVING num > 2 # 顺序 4
ORDER BY num DESC # 顺序 6
LIMIT 2 # 顺序 7
```

- #### 在 SELECT 语句执行这些步骤的时候,每个步骤都会产生一个 虚拟表 ,然后将这个虚拟表传入下一个步骤中作为输入。需要注意的是,这些步骤隐含在 SQL 的执行过程中,对于我们来说是不可见的。

### 同时因为 SQL 是一门类似英语的结构化查询语言,所以我们在写 SELECT 语句的时候,还要注意相应的关键字顺序,

### 所谓底层运行的原理,就是我们刚才讲到的执行顺序。



---


----

© 版权声明

<escape>

<div>
    <h3 align="center"  style="color: brown;" >版权声明</h3>
    <table>
   		<tr>
    		<ol>
				<li>本网站名称：𝚲𝚳𝚲</li>
				<li>𝚲𝚳𝚲提供的资源仅供您个人用于非商业性目的。</li>
				<li>本站文章部分内容可能来源于网络，仅供大家学习与参考，如有侵权，请联系我进行删除处理。</li>
				<li>本站一切资源不代表本站立场，并不代表本站赞同其观点和对其真实性负责。</li>
        		<li>本站一律禁止以任何方式发布或转载任何违法的相关信息，访客发现请举报</li> 
        		<li>本站资源大多存储在云盘，如发现链接失效，请联系我，我会第一时间更新。</li>
        		<li>本站强烈打击盗版/破解等有损他人权益和违法作为，请支持正版！</li>  
			</ol>
		</tr>
	</table>
</div>





</escape>

----



