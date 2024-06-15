---
title: 搭建个人博客（四）Typora+Picgo+Gitee搭建免费云图床  # 添加博文标题
date: 2019-9-18 15:00:00
author: 𝚲𝚳𝚲
tags:   # 添加博文标签
  - 图床	
  - Picgo
categories:   # 添加博文分类
  - 搭建图床  
---

#  搭建个人博客（四）Typora+Picgo+Gitee搭建云图床

实现图床的方式有很多种

例如：

- [使用Typora+PicGo+阿里云 搭建图床 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/636646400?utm_id=0)

这里提供一种

在编写博文的时候，需要进行插入图片，但是此时的图片是在本地的，我们要使用Typora+Picgo+Gitee实现云图床将图片放在gitee仓库中，在线访问就可以查看到。

## 一、创建一个仓库

-  **初始化同时创建imgs文件夹**

![image-20240109014112710](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401090141623.png)

![image-20240109014422479](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401090144735.png)

## 二、生成私人令牌

- **生成仓库后，点击右上角的头像->设置->私人令牌->生成私人令牌->复制->确认**，保存好

## 三、安装PicGo软件

```java
https://picgo.github.io/PicGo-Doc/zh/
```

- 安装PicGo软件后，插件设置中搜索gitee-uploader安装插件
  - ![image-20240109015057668](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401090150816.png)
- 设置PicGo-Server确定一下
  - ![image-20240109015213994](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401090152341.png)
- 设置时间戳重命名，保证文件名中没有中文避免线上不显示
  - ![image-20240109015354215](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401090153991.png)
- 设置图床gitee为默认图床
  - ![image-20240109015634979](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401090156748.png)
- **设置gitee图床连接**
  - ![image-20240109020235694](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401090202298.png)

至此PicGo设置完毕

## 四、关联Typora和PicGo软件

- ####  打开Typora，偏好设置-图像，关联PicGo

  - ![image-20240109020753314](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401090208649.png)



- #### 使用Typora编写博客的时候，复制了图片到当前文章当中，直接点击上传

  - ![image-20240109021151932](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401090211054.png)

- #### 在仓库文件夹中就能看到了

  - ![image-20240109021340947](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401090213130.png)

----

## 五、说明

### 1.为什么不使用PicGo-Core(command line)

- ![image-20240109021747024](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401090420741.png)
- gitee上传设置命令的的上传方式，配置了配置文件，有时候也会上传不成功出现错误。如果你已经下载了PicGo-Core(command line)插件，然后又下载了PicGoApp上传，也有可能会出现错误。解决办法：将Typora软件卸载重新安装重新配置。
- Typora软件需要激活，这里提供[Typora旧版本](https://www.alipan.com/s/mjWB1SYYLpd)免激活使用

### 2.下拉框“复制图片到./${filename}.assests文件夹”选项说明：

- 复制图片到./${filename}.assests文件夹：以后在C:\working\blog\source\ _posts 中创建博客文章，先创建md文件，然后写博文在每次往md插入图片时，都会自动在同级目录生成assests文件夹将插入的图片拷贝一份在里面存放，这样以后拷贝文件将assests和md文件一起拷贝，就一直有效了。
- 上传图片：每次往md插入图片时，都会将图片上传到gitee仓库，图片名自动改为gitee仓库图片地址





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















