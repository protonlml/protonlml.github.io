---
title: 搭建个人博客(三)：主题pure使用指南  # 添加博文标题
date: 2019-9-17 13:00:00
author: 𝚲𝚳𝚲
tags:   # 添加博文标签
  - Hexo
  - Pure主题
categories:   # 添加博文分类
  - 博客相关  

---

# 搭建个人博客(三)：主题pure使用指南

**Hexo-theme-pures是一个Hexo的主题框架**

## 一、安装pure主题

### 1. 在hexo根目录中的themes文件夹下克隆pure主题

![image-20240108224457543](https://gitee.com/lmlpla/blogimages/raw/master/imgs/image-20240108224457543.png)

```java
git clone https://github.com/cofess/hexo-theme-pure.git themes/pure
```

- #### 下载完毕，删除文件夹中所有.git相关的文件

### 2.修改配置文件

- 在 [Hexo](https://so.csdn.net/so/search?q=Hexo&spm=1001.2101.3001.7020) 中主要有两份配置文件，其名称都是 _config.yml。 一份位于博客根目录下，主要包含 Hexo 本身的配置；另一份位于主题根目录下，主要用于配置主题相关的选项。

  - （1.）**打开博客根目录配置文件_config.yml，做如下修改:**

    ```txt
    language: zh-CN //设置主题为中文版，若使用英文版则不修改
    theme: pure //修改hexo主题
    ```

  - **（2）在博客文件夹下打开git bash命令行窗口依次使用如下指令:**

    ```txt
    hexo clean
    hexo s
    ```

- 启动服务后：进入本地浏览器输入:http://localhost:4000/，如下图

  - ![image-20240108225753623](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401082257937.png)

### 3.安装pure插件

在博客文件夹下打开git bash命令行窗口依次使用如下指令：

```javascript
npm install hexo-wordcount --save
npm install hexo-generator-json-content --save
npm install hexo-generator-feed --save
npm install hexo-generator-sitemap --save
npm install hexo-generator-baidu-sitemap --save
npm install hexo-deployer-git --save
```

## 二、配置pure主题

### 1. 复制_source文件夹中的内容

**将主题目录中 /theme/_source/ 下的所有东西复制进博客根目录的source文件夹中**

![image-20240108230658560](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401082306949.png)

### 2. pure配置文件的修改：

- 打开主题根目录下的_config.yml配置文件：
- **（1）配置站点左边的主目录:**

```java
# menu
menu:
  Home: .
  Archives: archives  # 归档
  # categories指代博客根目录的source下的categories文件夹,可进行相关配置,下同
  Categories: categories  # 分类
  Tags: tags  # 标签
  Repository: repository  # github repositories
  #Books: books  # 豆瓣书单
  Links: links  # 友链
  About: about  # 关于
```

单个目录界面的相关配置可在博客根目录的source下的同名文件夹中进行配置

- **（2）配置站点标题:**

```java
# Site
site:
  logo:
    enabled: true
    width: 40
    height: 40
    url: ../images/logo.png
  title: 𝚲𝚳𝚲的博客 # 页面title
  favicon: ../favicon.ico
  board: <p>欢迎交流与分享经验!</p> # 站点公告
  copyright: true # 底部版权信息
```

- **（3）配置主题颜色:**

```java
# config
config:
  skin: theme-black # 主题颜色 theme-black theme-blue theme-green theme-purple
  layout: main-center # 布局方式 main-left main-center main-right
  toc: true # 是否开启文章章节目录导航
  menu_highlight: false # 是否开启当前菜单高亮显示
  thumbnail: false # 缩略图 ，enable posts thumbnail, options: true, false
  excerpt_link: Read More
  #New
  isNewTabLinks: false #是否链接打开新标签页
  autoUnfold: true # 默认展开文章目录
```

- **（4）配置页码信息:**

```java
# Pagination
pagination:
  number: true
  prev: 
    alwayShow: true
  next:
    alwayShow: true
  midSize: 2 # 当前页码左右到省略号显示的页码数，默认2，表现为 1 ... 4 5 6 7 8 ... 10
  showContent: true # 页面文章小于2篇时显示文章内容
```

- **（5）配置页面右侧栏目**

```java
# Sidebar  页面右侧栏目设置
sidebar: right
widgets:
  - board  
  - category
  - tag
  # - tagcloud  #隐藏“标签云”
  - archive
  - recent_posts
```

- **（6）配置打赏信息**

```java
# Donate
donate:
  enable: true
  # 微信打赏
  wechatpay:
    qrcode: images/donate/wechatpayimg.png # 在主题目录的source文件夹中进行图片的设定
    title: 微信支付
  # 支付宝打赏
  alipay: 
    qrcode: images/donate/alipayimg.png # 在主题目录的source文件夹中进行图片的设定
    title: 支付宝
```

- **（7）配置是否启用分享功能**

```java
# Share
# weibo,qq,qzone,wechat,tencent,douban,diandian,facebook,twitter,google,linkedin
share:
  enable: false   # true是否启用分享
  sites: weibo,qq,wechat,facebook,twitter  # PC端显示的分享图标
  mobile_sites: weibo,qq,qzone  # 移动端显示的分享图标
```

- **（7）开启搜索功能**

```java
# Search
search:
  insight: true # 内置搜索功能,
  baidu: false # 百度搜索功能,不可以同时使用
```

- **（8）配置“项目”导航栏 **

```java
# Repository Info (This will override 'github' option)
# 项目仓库信息（将会覆盖 github 项）
repository:
  platform: gitee # 托管平台（github | gitee）
  username: lmlpla # 用户名
```

- **（9）关闭评论功能**

*Valine*
一个无后端的评论框工具，其依赖于 Leancloud 开发，所以使用前需要先注册 Leancloud 账号
*Valine配置*

```java
comment:
  # type: valine  # 启用哪种评论系统
      
  valine: # Valine官方地址: https://valine.js.org
  	appid:  # 你的 leancloud 应用 appid
  	appkey:  # 你的 leancloud 应用 appkey
  	notify: true # 是否开始评论邮件提醒, 教程: https://github.com/xCss/Valine/wiki
  	verify: false # 是否开始验证码功能, 开始邮件提醒会自动开启验证码功能
  	placeholder: 说点什么... # 输入框默认内容
  	avatar: mm # 头像展示方式, 具体设置项教程: https://valine.js.org/configuration.html#avatar
  	meta: nick,mail,link # 自定义评论信息
  	pageSize: 10 # 评论列表分页
  	lang: zh-cn, # 多语言支持 zh-cn | en
  	visitor: true # 文章阅读量统计:  https://valine.js.org/visitor.html
  	highlight: true # 代码高亮
  	recordIP: true # 记录评论者的IP
```

- **(10) 开启文章字数统计以及阅读时长预计**

```java
# wordcount
postCount:
  enable: true
  wordcount: true  # 文章字数统计
  min2read: true  # 阅读时长预计 
```

- **（11）文章下面的个人信息修改**

```java
# profile
profile:
  enabled: true # Whether to show profile bar
  articleSelfBlock: false # 关闭文章下方的自我介绍
  avatar: images/avatar.jpg
  gravatar: # Gravatar email address, if you enable Gravatar, your avatar config will be overriden
  author: 𝚲𝚳𝚲 #𝓵𝓶𝓵
  author_title: ◙
  author_description: 业精于勤，荒于嬉；行成于思，毁于随！
  location: Shenzhen, China
  follow: 
```

- **（12）左下角链接设置**

```java
 # Social Links  左下角链接
  social:
    links:
      gitee: https://gitee.com/lmlpla
      #github: https://github.com/cofess
      #weibo: http://weibo.com/cofess
      #twitter: https://twitter.com/iwebued
      # facebook: /
      # dribbble: /
      #behance: https://www.behance.net/cofess
      rss: atom.xml
    link_tooltip: true # enable the social link tooltip, options: true, false
```

- **（13）“关于”导航页面的右侧栏目设置**

```java
 # My Skills 技能
  skills:
    Git: ★★☆☆☆
    Java: ★★★☆☆
    Javascript: ★☆☆☆☆
    Vue: ★★☆☆☆
    #HTML+CSS: ★★★☆☆
    #Bootstrap: ★★★☆☆
    #ThinkPHP: ★★★☆☆
    #平面设计: ★★★☆☆
```

- **（14）“关于”导航页面的右侧栏目设置**

```java
# My Personal Links 联系我链接
  links:
    Gitee: https://gitee.com/lmlpla
    Blog: https://lmlpla.gitee.io/blog/
    #微博: http://weibo.com/cofess
    #花瓣: http://huaban.com/cofess
    #Behance: https://www.behance.net/cofess
```

- **（15）“关于”导航页面的右侧栏目设置**

```java
# My Personal Labels 打标签
  labels:
    - 音乐街舞
    - 摄影生活
    - 
    - 
    - 
```

- **（16）关闭不需要的设置**

```java
 # My Personal Works
  #works:
  # name:
  #   link: http://www.example.com
  #    date: 2016
  # My Personal Projects
  #projects:
   # cofess/gulp-startpro: https://github.com/cofess/gulp-startpro
    #cofess/hexo-theme-pure: https://github.com/cofess/hexo-theme-pure
```

- **（17）添加背景动画[背景动画](https://github.com/hustcc/canvas-nest.js)基于canvas，在themes/pure/layout/layout.ejs的中面添加**

```java
<script type="text/javascript" src="//cdn.bootcss.com/canvas-nest.js/1.0.0/canvas-nest.min.js"></script>
```

- **（18）修改左下角的站点创建时间**（直接用VS Code打开，在主题目录中搜索 publishby）
  - ![image-20240109010042978](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401090100493.png)

- **（19）友情链接的配置:**
  - **选择博客根目录下 /source/_data/ 中的links.yml配置文件，可仿照其中样例进行配置**

```java
gentryhuang:
  link: https://gentryhuang.com/
  avatar: ../images/gentryhuang-logo.png
  desc: 脚踏实地,步步为营
```

-  **(20) 修改关于页面**

  - 找到\blog\source\about\index.md文件，添加样式

  ```java
  ---
  title: 关于我
  description: 集齐龙珠，召唤神兽！
  layout: about
  comments: false
  sidebar: custom
  ---
  ​```txt
  /**** 
  * 　　　┏┓　　　┏┓ 
  * 　　┃　　　　　　　┃ + +
  * 　　┃　　　━　　　┃ ++ + + +
  * 　████━████┃    🚂🚂🚂-<-< 欢迎访问我的博客
  * 　　┃　　　　　　　┃ + 
  * 　　┃　　　┻　　　┃ + + 
  * 　　┃　　　　　　　┃ 
  * 　　┗━┓　　　┏━┛Code is far away from bug with the animal protecting 
  * 　　　　┃　　　┃   神兽护体，永无bug 
  * 　　　　┃　　　┃ +
  * 　　　　┃　　　┗━━━┓+
  * 　　　　┃　　　　　　　┣┓    📬 联系我：lmle_mail@163.com
  * 　　　　┃　　　　　　　┏┛ + +          
  * 　　　　┗┓┓┏━┳┓┏┛ +
  * 　　　　　┃┫┫　┃┫┫ 
  * 　　　　　┗┻┛　┗┻┛ 
  */
  ​```
  
  
  ```

  

  - ![image-20240109011547156](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401090115476.png)

## 三、更新站点，查看效果

- **在博客文件夹下打开git bash命令行窗口依次使用如下指令：**

```java
hexo clean
hexo g
hexo s
```

启动服务后：进入本地浏览器输入:http://localhost:4000/ 进行查看

## 四、效果

[𝚲𝚳𝚲的博客 (gitee.io)](https://lmlpla.gitee.io/blog/)







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







