---
title: nodejs安装教程
date: 2019-09-07 9:00:00
author: 𝚲𝚳𝚲
tags:   # 添加博文标签
	- 经验
	- npm
	- nodejs
categories:   # 添加博文分类
	- 经验
password: 767136280
---

## 一、下载nodejs

- ### [Node.js 中文网 (nodejs.com.cn)](https://www.nodejs.com.cn/)

- #### 下载zip包，直接解压无须安装，node-v18.16.1-win-x64.7z   解压到C:\Program Files\nodejs 目录下

- #### 同时创建node_global和node_cach两个文件夹。

## 二、配置环境变量

- #### 1.系统变量下新建NODE_PATH

```java
C:\Program Files\nodejs\node_global\node_modules
```



- ![202401222307358](https://raw.githubusercontent.com/protonlml/blogimages/master/imgs/202406161016747.png)

---

- #### 2.系统变量path中添加如下

```java
%NODE_PATH%
C:\Program Files\nodejs
C:\Program Files\nodejs\node_global
```



- ![202401222308682](https://raw.githubusercontent.com/protonlml/blogimages/master/imgs/202406161016272.png)

---



- #### 3.更改用户path变量

  - ##### 这里我们需要将其中默认的C:\Users\用户名\AppData\Roaming\npm更改为：

```java
C:\Program Files\nodejs\node_global
```

## 三、修改配置

#### 在nodejs文件夹下使用GitBash进行命令配置

- #### 1.关闭代理以及配置淘宝镜像

  ```java
  npm config set proxy null
  npm config set https-proxy null
  npm config set registry https://registry.npmmirror.com
  ```

  - 查看是否修改成功

  ```java
  npm config get registry
  ```

  

- #### 2.配置默认目录

  ```java
  npm config set prefix "C:\Program Files\nodejs\node_global"
  npm config set cache "C:\Program Files\nodejs\node_cache"
  ```

- #### 3.设置权限

  ```java
  npm config set strict-ssl false
  ```

- #### 4.查看所有设置

  ```java
  npm config ls
  ```


---

---



## 四、查看安装版本

```java
node -v 
npm -v
```

## 五、测试是否配置成功

- #### 安装vue插件

```java
npm install -g  vue
```

![img](https://raw.githubusercontent.com/protonlml/blogimages/master/imgs/202406161016336.png)



---

---



## 六、npm install安装失败常见问题的解决办法小结



> #####  有时候前端安装npm install 安装包总是安装不上,下面这篇文章主要给大家介绍了关于npm install安装失败常见问题的解决办法,文中通过实例代码介绍的非常详细,需要的朋友可以参考下

- #### 显示当前的镜像地址

  ```java
  npm get registry
  ```

  

- ### 1. 安装cnpm

```java
npm install -g cnpm --registry=http://registry.npmmirror.com
```

- ##### 安装完之后可以通过cnpm -v 检验是否安装成功。

- ### 2.cnpm install安装依赖

  ```java
  cnpm install
  ```

  > ##### 在运行cnpm install中,你可以会遇到cnpm:无法加载文件C:Users\57883 AppData\Roaming\npm\cnpm.
  >
  > ##### ps:因为在此系统上禁止运行脚本的错误.
  >
  > #### 解决方法:
  >
  > - 在系统中搜索框输入Windos PowerShell
  > - 点击"管理员身份运行"
  > - ·输入"set-ExecutionPolicy RemoteSigned'"▣车
  > - ·根据提示,输入A,回车
  > - ·再次回到cnpm-v执行成功.
  > - ps:不只是cnpm命令,包括pnpm、yarn等这些命令,如果执行时,报这样的错误,都可以通过此方法解决.前提是,如果是用npm命令来安装这些CLI命令工具,必须安装到全局环境中,才能生效.

- ### npm install node-sass 报错如何解决呢?

- node 与node-sass版本不兼容导致安装依赖失败

![img](https://raw.githubusercontent.com/protonlml/blogimages/master/imgs/202406162259879.png)

- ### **解决办法**：

  > 1. //查看node版本
  >
  > 2. node-v
  >
  > 3. // –save-dev自动将node-sass加入到项目文件夹下的package.json中。
  >
  > 4. cnpm install --save-dev node-sass

# 附：npm install命令一直失败的坑

执行npm install命令一直失败，报错主要原因如下：reason: getaddrinfo EAI_AGAIN registry.npmjs.org   异常分析

- #### 1.解决代理问题

  ```java
  npm config set proxy null
  npm config set https-proxy null
  npm config set registry https://registry.npmmirror.com
  ```

- #### 2.所以大家可以把上面语句执行一遍试一下，还有要把权限执行下面语句

  ```java
  npm config set strict-ssl false
  ```

- ####  3.如果还不行，建议大家更换vscode，node版本，我使用的是：

  ```java
  node-v10.12.0-x64
  VSCodeUserSetup-x64-1.54.3
  ```

  - 换网络改为移动网络试试

参考：[npm install安装失败常见问题的解决办法小结_node.js_脚本之家 (jb51.net)](https://www.jb51.net/javascript/285453ta2.htm#_label4)









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































