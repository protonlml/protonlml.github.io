---
title:  matery主题的使用  # 添加博文标题
date: 2020-3-17 11:00:00
author: 𝚲𝚳𝚲
tags:   # 添加博文标签
  - Hexo
  - matery主题
categories:   # 添加博文分类
  - 博客相关  
---

# matery主题的使用

# 一、下载matery主题

- ### 1.GitHub源项目

- [GitHub - blinkfox/hexo-theme-matery: 一个基于材料设计和响应式设计而成的全面、美观的Hexo主题。](https://github.com/blinkfox/hexo-theme-matery)

- ### 2.在本地clone下来

```java
git clone https://github.com/blinkfox/hexo-theme-matery.git
```



# 二、配置hexo根yml文件

- ![image-20240112005024106](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401120050772.png)

# 三、自定义主题

- ### 1.修改导航名称和路径图标

  - ##### 添加导航二级菜单的写法（如下是“关于”一级菜单修改）

  - 注意：1.菜单导航名称可以是中文也可以是英文(如：`Index`或`主页`) 

  - ​             2.图标icon 可以在[Font Awesome](https://fontawesome.com/icons) 中查找  ,线上的

  ```java
   About:
      url: /about
      # icon: fas fa-user-circle 注释掉原来的，加上下面这一段
      icon: fas fa-list
      children:
        - name: 爱的颜色
          url: /love
          icon: fas fa-heart
        - name: 生日快乐
          url: /birthday
          icon: fas fa-cake
  ```

- ### 2.手机二级菜单配置

  ```yaml
  navMenu:
    mleft: true    #  二级侧栏子菜单是否对齐左边
    bgColor: " "   #  二级侧栏子菜单背景颜色,留空即为全局背景色
  ```

- ### 3.首页中间右侧 banner

  ```yaml
  githubLink:
    enable: true                                   # 是否开启
    url: https://github.com/sitoi/sitoi.github.io  # GitHub 仓库地址
    title: Fork Me                                 # 显示文字
  ```

- ### 4.首页轮播图相关配置

  ```yaml
  cover:
    showPrevNext: false     # 是否显示左右切换按钮
    showIndicators: false   # 是否显示指示器
    autoLoop: false         # 是否自动轮播
    duration: 120           # 切换延迟时间，默认单位 秒
    intervalTime: 5000      # 自动切换下一张的间隔时间
  ```

参考：

[Hexo博客主题之hexo-theme-matery的介绍 | 闪烁之狐 (blinkfox.github.io)](https://blinkfox.github.io/2018/09/28/qian-duan/hexo-bo-ke-zhu-ti-zhi-hexo-theme-matery-de-jie-shao/)

[基于 Hexo GitHub 从零开始搭建个人博客（三）：Matery 主题（DIY 版）详细配置教程，附博客源码 | Sitoi](https://sitoi.cn/posts/63466.html)

[(๑•̀ㅂ•́) ✧被发现了～ (sunhwee.com)](https://sunhwee.com/posts/6e8839eb.html#toc-heading-23)



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







































