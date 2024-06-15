---
title:  搭建个人博客（二）：Hexo部署到 Gitee  # 添加博文标题
date: 2019-9-17 12:00:00
author: 𝚲𝚳𝚲
tags:   # 添加博文标签
  - Hexo
  - Pure主题
categories:   # 添加博文分类
  - 博客相关  
---

# **搭建个人博客（二）：Hexo部署到 Gitee**

## 一、新建 Gitee 仓库

![image-20240111064936662](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110649958.png)

- #### 新建的仓库，先不要初始化，同时仓库名要和本地博客所在文件夹名称相同。

  - ![image-20240111053205537](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110532369.png)

- ##### 没有初始化的仓库有命令提示

---

# 二、本地博客文件夹中使用git命令，将本地文件推送到远程仓库

- ### 1. 本地文件夹内删除已有的 .gite文件

  - ##### 使用Gitbash窗口 运行 如下命令，将本地文件夹绑定到远程仓库上去

  - ![image-20240111065033225](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110650711.png)

  ```java
  git init 
  git add .
  git commit -m "first commit"
  git remote add origin https://gitee.com/lmlpla/xxxx.git  # xxxx指远程仓库名字
  git push -u origin "master"
  ```

  - ##### 刷新远程仓库，就可以看见本地博客文件被推送到仓库中去了

- ### 2.远程仓库创建新的分支hexo

  - ![image-20240111063625729](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110636415.png)

- 

- ### 3.设置hexo分支为默认分支

  - ![image-20240111063726826](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110637939.png)

  - ##### （目的是为了保存hexo博客的源文件，迁移主机，随时拉取就可以使用，再master分支上进行hexo d 命令推送编译后的文件会默认到hexo分支上）

- #### 4.使用Sourcetree管理本地博客

  - ![image-20240111064748835](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110648129.png)



- 

# 三、在 Gitee 中添加 SSH 公钥

- ### 使用SSH公钥可以让你在你的电脑和 Gitee 通讯的时候使用安全连接（Git的Remote要使用SSH地址）

- ## ==如果之前gitee上面已经添加过，就跳过第三步==

- #### 检查本地电脑上是否已有 SSH，在本地打开 git bash 命令行窗口，输入以下命令

  ```java
  cd ~/.ssh
  ```

- ##### 如果没有，显示

  ```java
  bash: cd: /c/Users/Administrator/.ssh: No such file or directory
  ```

  

- ##### 如果有的话，标识本地已经有创建过的 SSH key 了

  - ![image-20240108051750431](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401080517713.png)


---

---



- #### 1.如果本地没有就创建 SSH key

  - ##### 运行如下命令   最后一个参数替换为自己的 注册Gitee时使用的邮箱，然后直接回车两次

    ```java
    ssh-keygen -t rsa -C "your_email@example.com"
    ```

    

- #### 2.**找到生成的.ssh文件，打开将内部的公钥复制下来**

  - ![image-20240108052356500](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401080523568.png)

- #### 3.测试 SSH 连接

  - 输入命令

  ```java
  ssh -T git@gitee.com
  ```

  - 会得到如下输出，询问是否确认连接，输入yes回车确认

    ```java
    The authenticity of host 'gitee.com (180.97.125.228)' can't be established.
    ECDSA key fingerprint is SHA256:FQGC9Kn/eye1W8icdBgrQp+KkGYoFgbVr17bmjey0Wc.
    Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
    ```

  - 最后连接成功会看到如下输出

  ```java
  Warning: Permanently added 'gitee.com,180.97.125.228' (ECDSA) to the list of known hosts.
  Hi dulily! You've successfully authenticated, but GITEE.COM does not provide shell access.
  ```

- #### 在 Gitee 中添加 SSH 公钥

  - 先在 C 盘指定目录中找到 `id_rsa_pub` 文件，复制内容然后打开 gitee 个人设置里面的 安全设置 - SSH公钥，标题可以随便取，把粘贴的内容复制到公钥里面，点击确定就可以
  - ![image-20240108052722568](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401080527894.png)

# 四、本地修改 _config.yml

- 修改hexo博客``根目录``中的配置文件``_config.yml``
  - ![image-20240108053407307](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401080534846.png)
  - ![image-20240111071011444](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401110710135.png)

- ### 安装 `hexo-deployer-git`（master分支操作）

  ```java
  npm install hexo-deployer-git --save
  ```

- ### 推送博客目录到远程 Gitee（master分支操作）

  ```java
  hexo g  
  hexo d
  ```

  - #### 这时候，远程仓库的 blog 目录下的文件(并且在hexo分支上会被更新一遍)


# 五、开启 Gitee Pages 服务

- ![image-20240108054009786](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401080540455.png)
- ![image-20240108054137413](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401080541525.png)

- **后期，如果更新了文章，使用 hexo g -d 命令就可以直接推送到远程hexo分支了，然后再更新一下就可以访问到新的博客文章**







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







