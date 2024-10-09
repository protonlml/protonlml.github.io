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



