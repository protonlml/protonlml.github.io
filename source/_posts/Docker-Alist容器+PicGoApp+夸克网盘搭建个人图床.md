---
title: Docker-Alist容器+PicGoApp+夸克网盘搭建个人图床  # 添加博文标题
date: 2019-9-18 18:00:00
author: 𝚲𝚳𝚲
tags:   # 添加博文标签
	- 图床	
	- Picgo
	- Alist
categories:   # 添加博文分类
	- 搭建图床  
---

# Docker-Alist容器+PicGoApp+夸克网盘搭建个人图床

- ##### 前言：在搭建自己的博客时，我们会把博文的图片上传到如：七牛云，阿里云oss，腾讯云等。这些第三方云图床上面，优点方便快捷安全。其次是使用“Typora+PicGoApp+gitee”实现远程仓库管理图片。但是作为图片的仓库是公开的，没法实现图片私密。再者就是现在自己搭建图床。

- ##### Docker-Alist容器+PicGoApp+夸克网盘搭建个人图床，这里服务端我使用的是自己电脑中的虚拟机，当然自己搭建服务器，或者搭建Nas以及购买第三方服务器都行。

# 一、准备工作

- #### 1.本地安装PicGOApp并且关联了Typora

  - 具体可查看文章[搭建个人博客（四）Typora+Picgo+Gitee搭建免费云图床](https://lmlpla.gitee.io/blog/2024/01/09/搭建个人博客（四）Typora+Picgo+Gitee搭建免费云图床/)

- #### 2.PicGo下载alist插件

  - ![image-20240111035237540](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110352301.png)

- #### 3.远程服务器上面安装Alist

  - ###### [Alist所有操作参照 AList文档 (nn.ci)](https://alist.nn.ci/zh/guide/install/docker.html)

  - ###### 这里使用本地虚拟机Docker安装Alist，使用VSCode连接远程服务器，在bash终端使用docker命令下载镜像

  ```linux
  docker run -d --restart=unless-stopped -v /etc/alist:/opt/alist/data -p 5244:5244 -e PUID=0 -e PGID=0 -e UMASK=022 --name="alist" xhofe/alist:latest
  ```

  

  - ![image-20240111040222965](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110402017.png)

  - ##### Alist容器运行起来，同时也下载了。使用命令查看

  ```java
  docker ps 
  ```

  - ![image-20240111040525844](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110405604.png)

  - ##### 生成登陆密码，并且修改登陆密码

  ```linux
  # 先随机生成一个密码
  docker exec -it alist ./alist admin random
  # 手动设置一个密码,`NEW_PASSWORD`是指你需要设置的密码
  docker exec -it alist ./alist admin set NEW_PASSWORD
  ```

- #### 4.浏览器中访问Alist客户端

  - ##### 端口是5244

  - 192.168.56.30:5244  这里我是本地服务器地址

# 二、挂载网盘

- #### 1.登陆Alist添加存储（将夸克网盘挂载到Alist上）

  - ![image-20240111041344234](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110419215.png)

- #### 2.添加一个新的驱动，驱动选择“夸克”。挂载路径和序号根据自己需求填写，缓存过期时间填0。Webdav策略选择“本地代理”。

![image-20240111042523636](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110426955.png)

- ##### 我们需要获取Cookie

  - ##### 打开电脑浏览器（使用Chrome浏览器）并登录夸克网盘账号(用网页版登录)，然后按键盘上的F12，进入开发者模式。点击上方的Network(网络)选项卡，在左侧的Name(名称)中找到“sort?pr=u”开头的条目并选中(如果该条目没刷新出来，需要稍等几秒钟)，然后在右侧的Request Headers中，找到Cookie值并复制：

  - ![eaae](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110429917.png)

  - ##### 将复制的Cookie值填入alist设置页面，其他选项全部保持默认，然后点击添加即可。

- #### 3.Alist两个设置

  - ##### 关闭签名所有

  - ![image-20240111045238334](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110452329.png)

  - ##### 复制令牌

  - ![image-20240111045328961](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110453217.png)

- #### 7.夸克网盘挂载成功。

  - ![image-20240111043528976](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110435996.png)



# 三、PicGo关联alist

- ![image-20240111045434304](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110459536.png)

- #### 设置配置

- ![image-20240111045700284](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110457438.png)

# 四、在Typora中复制一张图片测试上传

- #### 注意要将 alist设置为 默认图床

参考链接

[Typora+PicGo+Alist 私人图床教程_alist 图床-CSDN博客](https://blog.csdn.net/whale0306/article/details/128870341)

[轻松打造智能家庭数据中心——袋鼠叔叔带你玩转绿联DX4600 (篇3—Docker中搭建Alist本地挂载阿里/百度/夸克网盘小白保姆教程) (zhihu.com)](https://www.zhihu.com/tardis/bd/art/652325981?source_id=1001)





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





