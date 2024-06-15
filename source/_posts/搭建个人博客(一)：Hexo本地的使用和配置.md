---
title:  搭建个人博客(一)：Hexo本地的使用和配置  # 添加博文标题
date: 2019-9-17 11:00:00
author: 𝚲𝚳𝚲
tags:   # 添加博文标签
  - Hexo
  - Pure主题
categories:   # 添加博文分类
  - 博客相关  
---

# 搭建个人博客(一)：Hexo本地的使用和配置

## 一，准备工作

### 1.了解hexo

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

----

### 2. 搭建博客之前,需要安装几个工具

- #### 2.1 git版本控制工具 
  - Git是一个免费的、开源的版本控制软件。在Windows上安装git，一般为msysgit，
    官方下载地址 :http://code.google.com/p/msysgit/downloads/list
    安装步骤下一步即可…最后在-shell窗口中输入命令 ``git --version 检查安装是否成功``

- #### 2.2 Node.js环境

  - **安装nodejs在官网上面，下载绿色的zip包 最好安装node-v18.16.1-win-x64.7z**

  - ### 详情请看本站文章“nodejs安装教程” [𝚲𝚳𝚲的博客 (gitee.io)](https://lmlpla.gitee.io/blog/2019/09/07/nodejs安装教程/)
    

----

### 3.**安装hexo,下载hexo 搭建博客**

- **创建一个 Blog文件夹，在这个文件夹中,使用Git窗口,依次执行下面的命令**

  ```java
  npm install -g hexo-cli  # 安装hexo客户端
  hexo init #初始化hexo
  npm i #安装npm工具 
  hexo g # 生成
  hexo s # 启动服务
  ```

- ###### ==（注意：下载后文件夹中有.git文件夹，给删除掉，后面要上传到自己的远程仓库，进行版本控制。）==

### 二、启动后存在的问题

- #### 1.启动hexo 创建成功后 ，浏览器 “localhost 已拒绝连接。” 

  - ##### 不是端口问题，4000端口打不开,是因为你是从git窗口里复制的,或者直接点击的。

    - ##### 在url地址栏里面重新敲 localhost:4000 就行了，或者 127.0.0.1:4000

      ---

      ---

      

- #### 2.启动后能正常访问，访问发现白屏了，什么也没有

- - 主要原因是 nodejs版本不兼容
- 导致在public文件夹下index.html文件是空白的。
  
  - ##### 重新安装nodejs 推荐node-v16.19.1-win-x64->nodejs安装教程：[𝚲𝚳𝚲的博客 (gitee.io)](https://lmlpla.gitee.io/blog/2019/09/07/nodejs安装教程/)
  
- **然后在本地启动查看结果。localhost:4000查看能不能访问, Ctrl+C 停止本地服务**

- 重启本地服务,要先
  - hexo clean 清理缓存
  - hexo g 生成
  - hexo s 启动本地服务查看本地,能不能将这个项目跑起来





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

