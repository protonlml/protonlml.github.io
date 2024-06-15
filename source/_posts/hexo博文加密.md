---
title: hexo博文加密密码是hello
date: 2019-09-20 11:46:00
author: 𝚲𝚳𝚲
tags:
  - Hexo
categories:
  - 博客相关
password: hello
---

# hexo博文加密

## 前言

>- 你可能需要写一些私密的博客, 通过密码验证的方式让人不能随意浏览.
>- 这在 wordpress, emlog 或是其他博客系统中都很容易实现, 然而 hexo 除外. 😦
>- `hexo-blog-encrypt`插件就能很好地解决这个问题.

- ### 在线演示

  - 点击[Hexo (mhexo.github.io)](https://mhexo.github.io/) **所有的密码都是 `hello`**.

## 一、安装

```java
npm install --save hexo-blog-encrypt
```

- ##### 下载失败，建议换nodejs版本推荐node-v16.19.1-win-x64

- ##### 或者更换网络。使用移动网试试

## 二、开启文章加密

- ##### 在博客根_config.yml 配置文件最后一行加入

```java
#开启文章加密 
#Security
encrypt: # hexo-blog-encrypt
  enable: true
  silent: true
  message: 请输入密码
  theme: Shrink # 这是加密框主题
  wrong_pass_message: 抱歉, 这个密码看着不太对, 请再试试.
  wrong_hash_message: 抱歉, 这个文章不能被校验, 不过您还是能看看解密后的内容.
```

- ####  注意：theme: Shrink 是加密框主题

- #### 以下是在线主题样式

- >[Default ](https://mhexo.github.io/2020/12/23/Theme-Test-Default/)
  >
  >[Blink ](https://mhexo.github.io/2020/12/23/Theme-Test-Blink/)
  >
  >[Shrink](https://mhexo.github.io/2020/12/23/Theme-Test-Shrink/)   
  >
  >[Flip](https://mhexo.github.io/2020/12/23/Theme-Test-Flip/)
  >
  >[Up](https://mhexo.github.io/2020/12/23/Theme-Test-Up/)
  >
  >[Surge](https://mhexo.github.io/2020/12/23/Theme-Test-Surge/)
  >
  >[Wave](https://mhexo.github.io/2020/12/23/Theme-Test-Wave/)  
  >
  >[Xray](https://mhexo.github.io/2020/12/23/Theme-Test-Xray/)

## 三、在文章信息头上加入password: xxxx

```txt
---
title: 博文加密
date: 2069-05-20 00:00:00
author: 
tags:
  - Hexo
categories:
  - 博客相关
password: 自定义的密码
---
```

## 四、本地启动查看样式

![image-20240124011016958](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401240110631.png)









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











































