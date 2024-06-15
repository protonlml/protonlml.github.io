---
title: Maven
date: 2019-10-10 11:00:00
author: 𝚲𝚳𝚲
tags:   # 添加博文标签
	- maven
	- 项目自动化构建工具
categories:   # 添加博文分类
	- java
	- maven
---

<h1><center>Maven</center></h1>

## 一、Maven的一些理解  

- 1.项目的构建，是指项目的“打包”，“编译”，“部署”，“运行”等一系列操作。 
-  2.用Maven就可以使我们的项目，能够自动化构建。 
-  3.maven是java项目的自动化构建工具。   
- 4.Maven可以，将一个大型的项目的不同功能，拆分成多个模块，分别进行开发管理。 
-   5.Maven可以，通过配置poom文件，来导入某个技术的jar包，同时会自动的导入这个jar包的相关依赖jar包。

## 二、Maven程序的执行原理

1. maven核心程序指的是，解压后的maven程序目录。也是maven软件的目录里面的内容。

2. Maven在自动构建项目的时候，使用插件会在本地仓库中找，使用依赖jar包也在本地仓库中找。本地找不到就到中央仓库中下载。 

3. 怎么使用maven？（不用开发工具）

   1. 创建一个maven规定的项目目录结构，在有poom.xml文件的目录下面，执行maven命令
   2. 当我们执行的Maven命令需要用到某些插件的时候，Maven核心程序会首先到本地仓库中查找
   3. 本地仓库的默认位置：[系统当前用户的家目录]\.m2\repository(Maven找插件的时候，自动创建)
   4. Maven核心程序如果在本地仓库中找不到需要的插件的时候，那么它会自动联网，到中央仓库中下载。

4. Maven的生命周期就是指的是“项目的构建过程”，项目的构建是有顺序的，执行的任何一个Maven命令都是从生命周期的头开始。

5. Maven构建项目完成之后，生成的“产品”就放在“项目src所在目录”中的“target”目录中。

6. Pom

   1. 【1】含义：project Object Model 项目对象模型。
   2. pom.xml对于Maven工程师核心配置文件，与构建过程相关的一切设置都在这个文件中进行

7. Maven坐标类比一下：

   1. 数学中可以用（x,yz）三个项量来确定一个空间的点。

   2. Maven的pom文件中，也是使用三个项量，来在仓库中唯一定位一个Maven工程

      - [1]：**g**roupid：公司或组织域名倒序+项目名

      ```java
      <groupId>cn.itcast</groupId>
      ```

      - [2]：**a**rtifactid：模块名 
      - [3]：**v**ersion：版本
        - 只要讲“**gav**”就讲的是Maven的坐标。
      - [4] :Maven工程的坐标与仓库中的路径对应关系。
        - 在Maven仓库里面。每一个Maven工程，他的坐标一定是不重复的，即标识了这个Maven工程信息，同时也决定了他在仓库中存放的目录是什么。

8. 仓库中保存的内容：宽泛的说就是（Maven工程项目）  

   - 主要有3大块：
     - -[1]：Maven核心软件，自身所需要的一些插件
     - [2]：第三方框架或工具的jar包(其实就是第三方项目，打成了jar包)
     - [3]：我们自己开发的工程。Maven将“插件”、“框架jar包”、“我们自己的项目”都用统一的目录结构，放在了仓库中，这样就方便Maven核心程序的管理和使用。

9. pom.xml文件解析。

   - 创建的Maven项目中有pom.xml文件，他是Maven项目的核心配置文件。
     - 【1】.除了上面三个坐标用来，定位当前项目用Maven核心程序安装在仓库中的位置。
     - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281041857.png)
     - 2】.中间部分是“依赖部分”，就是指当前项目，所使用的到的“其他模块项目和jar包"，在Maven仓库中的坐标。如果仓库中没有指定的依赖jar包，就会自动从私服上面下载，私服上面没有就会到中央仓库中下载。
       - 但是如果当前项目，用到我们自己写的模块，这时候就需要将，要使用的模块项目给“安装”到仓库中，用“ mvn install”命令进行安装。是不可能从网上下载的，因为这是我们自己写的，不是第三方jar包项目。这样我们就可以将一个大的项目，进行拆分成很多小的模块，然后各个模块之间用“依赖坐标”，来互相关联。
       - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281041248.png)
     - 【3】最下面是“插件”部分。
       - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281041606.png)

10. 依赖

    1. ①Maven解析依赖信息时会到本地仓库中查找被依赖的jar包。
       - 对于我们自己开发的Maven工程，使用mvn install命令安装后就可以进入仓库。
    2. ②依赖的范围
       - 【1】在pom.xml文件中<scope>依赖的范围</scope>
       - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281042365.png)
       - 依赖的范围一般常用的有三个：compile，test、provided三个。
       - 依赖范围：意思就是，当前项目所依赖的这个“依赖”，在编译，测试，打包。过程当中时候有效。
         - [1]compile范围的“依赖”（编译范围）
         - 对主程序是否有效：有效
         - 对测试程序是否有效：有效
         - 是否参与打包：参与
         - 是否 参与部署：参与
         - [2]test范围的“依赖”（测试范围）
         - 对主程序是否有效：无效
         - 对测试程序是否有效：有效
         - 是否参与打包：不参与
         - 是否参与部署：不参与
         - 典型例子：“junit依赖”它就是测试依赖，这个jar包，不参与打包，在主程序中没有。
         - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281045023.png)
         - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281045144.png)
         - [3]provided范围的“依赖”，通常是为web工程来添加的（不参与部署的范围）。
           - 说明只要加了provided范围的“依赖”，web容器中都有。比如：servlet的这个依赖，部署的时候就不需要，因为Tomcat服务器本身就有servlet的jar包。
         - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281045793.png)
         - 对主程序是否有效：有效
         - 对测试程序是否有效：有效
         - 是否参与打包：不参与
         - 是否参与部署：不参与
         - 典型例子：servlet-api.jar

11. maven命令是什么？

    -  maven这个程序，用来构建项目所使用的命令。（这些命令的顺序，就是生命周期的顺序）
      - 比如【1】清理：mvn clean
      - 【2】：编译主程序：mvn compile
      - 【3】：编译测试程序：mvn test-compile
      - 【4】：执行测试：mvn test
      - 【5】：打包：mvn package
      - 【6】：安装：mvn install
      - 【7】：生成站点：mvn site这些命令，构成了Maven构建项目时的，不同生命周期，

12. 12.Maven的生命周期

    - 【1】意思：就是Maven构建项目的的，各个构建环节执行的顺序。：不能打乱顺序，必须按照既定的正确顺序来执行，是生命周期的各个阶段的命令来实现的。
    - 【2】生命周期是在Maven的核心程序中定义了，抽象的生命周期。 生命周期中各个阶段的具体任务是由插件来完成的。
    - 【3】有三套独立的生命周期：
      - ①Clean Lifecycle（清理生命周期）在进行，在真正的构建一个项目之前，必须先进行一些清理工作。
      - ②Default lifecycle（默认的生命周期）构建的核心部分，编译，测试，打包，安装，部署等等。
      - ③Site Lifecycle（生成站点生命周期）生成项目报告，站点，发布站点。
    - 【4】每个生命周期的具体实现
      - 比如：只执行“mvn clean 清理命令”就会进行清理生命周期。
      - 执行“mvn install 安装命令”就会进行Maven构建项目的默认生命周期，此时Maven核心程序，会从头开始执行“clean清理”,“compile 编译”，“test-compile 编译测试”，“test 执行测试”，“package 打包”，“install 安装”这一系列的过程。
      - 执行“site 生成站点”，也会从头开始，将所有过程进行一边。这是生成站点生命周期
      - Maven核心程序为了更好的实现自动化构建，按照这一的特点执行生命周期中的各个阶段：不论现在要执行生命周期中的哪一个阶段，都是从这个生命周期最初的位置开始执行。
    - 【5】生命周期的各个阶段仅仅定义了要执行的任务是什么（命令）完成这个命令，是由特定的Maven插件来完成的。
      - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281048751.png)

13. 创建Maven工程之前，需要将IDEA编辑器，和本地下载的Maven程序，进行关联配置。具体操作，见文末。

---

---



## 三、使用IDEA创建普通的javaMaven工程

![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281049426.png)

![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281050505.png)

![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281050614.png)

![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281050417.png)

## 四、.使用IDEA创建webMaven工程（Maven要聚合模块的做法）  

- 【1】必须先创建一个空的工程。在空的工程中添加模块。（每次添加模块都要使用快捷键“ctrl+alt+shift+s”来调出**Project Structure窗口，在这个窗口中添加模块，不能直接在模块上面右键添加模块。（在模块上右键模块会添加到“模块里面”）**）

- ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281051453.png)

- ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281051169.png)

- ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281051640.png)

- ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281052141.png)

- ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281052005.png)

- ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281052752.png)

- ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281052182.png)

- ### 【标准的Maven工程，分模块的大型web项目，目录结构】

- ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281052343.png)

## 说明

- #####  我们在用Maven程序，在开发web项目的时候，可以将一个大型的web项目拆分成多个“模块项目”，然后如果模块之间要相互使用的话，就要在pom文件中，添加一个指定“模块依赖坐标”就可以使用了，但是此时模块项目并没有安装到“仓库当中”，开发过程相互调用没有问题。但是如果部署运行的话就要在Maven仓库中安装。不过这个安装步骤不用我们做了，在我们开发完程序后，进行部署运行的时候，Maven程序会自动将所需要的“模块依赖”安装到仓库中。

## 五、依赖

- ### 依赖的传递性：

  - 【1】依赖的传递性是指，如果在一个大型的项目当中，各个模块相互依赖，那么在“最下面的模块（依赖关系最下面，这个模块只是被依赖，不去依赖别的模块）”中，pom.xml文件里面，配置的**compile**”范围的依赖jar包，其他模块的pom.xml文件虽然没有声明一样的**compile**”范围的依赖jar包，但是也可以使用这个依赖。
  - 【2】前提是“**compile**”范围的依赖才能传递，“**test**”“**provided**”范围的依赖不能传递。所以在各个工程模块中，能够传递的依赖，只在“最下面”模块中声明一次就可以了，不能够传递的“**test**”“**provided**”范围的依赖就得各个模块中重复声明依赖。比如：servlet的依赖，他就是“provided范围的模块”，需要在每一个项目模块pom.xml文件中，都要重复声明。
  - 【3】我们在开发项目的时候，会有一个专门的模块来负责维护这些框架jar包的依赖信息的。在这个模块中，全部都写“**compile**”范围的依赖”，让其他功能模块，来依赖这个“专门模块”，就可以实现“**compile**”范围的依赖”通用。
  - 【4】子类继承了父类模块，也可以实现依赖传递，默认就是依赖的，不需要再在子类中，重新声明依赖父类，只在子类中声明父类就可以了。

- ### 依赖的排除：

  - 依赖的排除，在哪个工程里面排除的，就在哪个工程里面生效。
  - 【1】当我们导入某些依赖jar包的时候，Maven会自动将这个jar的其他依赖jar包也一起导入到工程当中，这个时候，如果不需要这个额外的jar包，就可以用“排除依赖”来进行排除。
  - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281054619.png)
  - 【2】找到要排除的依赖的ID（假如spring-jcl依赖要被排除）
  - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281054870.png)
  - 3】添加<exclusions> </exclusions>标签
  - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281054912.png)

- ### 依赖原则：

  - #### 解决的是依赖“jar包”冲突的问题。（Maven中内置的一个原则，我们也改变不了，发生jar包冲突的时候，Maven会自动的将冲突解决）

  - 前提是因为“依赖的传递性”导致的jar包冲突问题。

  - 冲突情景：

  - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281057370.png)

  - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281057892.png)

  - **properties标签**配合自定义标签声明数据的配置并。(可以利用这个标签，实现在一个页面上，同种类型的框架jar包，版本号相同，)在父模块中就更简便了

  - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281057518.png)

  - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281057000.png)

    ```xml
    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <spring.version>5.0.2.RELEASE</spring.version> <!--不是只能用于声明依赖的版本号。凡是需要统一声明后再引用的场合都可以使用。-->
    </properties>
    
    
    <!--spring-core依赖-->
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-core</artifactId>
        <version>${spring.version}</version>
    </dependency>
    <!--spring-core依赖-->
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-core</artifactId>
        <version>${spring.version}</version>
    </dependency>
    ```



## 六、Mavne继承（pom文件的继承）

- 存在的问题：我们都知道在一个“模块项目1”中配置了“**compile**”范围的依赖jar包”，“其他模块项目”来依赖这个“模块项目1”的时候，“其他模块项目”中会自动的存在了“项目模块1的”“**compile**”范围的依赖jar包”。这是依赖的传递性。只用在“模块项目1”中声明一份就可以了。

- 但是：如果是““**test**”“**provided**”范围的依赖是不能传递的”，需要在每一个模块中都要，重复的手动添加““**test**”“**provided**”范围的依赖”，比如“junit依赖”，他就是“test范围的依赖”。（不能够传递的依赖，他就是零散的分散在各个模块当中，就很容易造成各个模块工程之间的版本不一致）。

- 这就存在一个问题，开发一个大型项目的时候，各个模块是不同开发组来开发的，使用“junit这种依赖”的时候，可能版本号就会不相同，导致各个模块之间不统一。

-  解决办法：使用Maven的继承，统一成同一个版本。（以junit依赖为例）

  - 【1】专门创建一个模块是所有模块的“父模块”，可以用作““**compile**”范围的依赖jar包”传递依赖。也可以用作““**test**”“**provided**”范围的依赖”的版本管理。

  - 【2】解决思路：将junit依赖统一提取到“父"工程中，在子工程中声明junit依赖时不指定版本，以父工程中统一设定的为准。同时也便于修改。

  - 【3】操作步骤  [1]创建一个Maven工程作为父工程。注意：打包的方式pom

    ```xml
      <groupId>com.atlml.maven</groupId>
        <artifactId>Parent</artifactId>
        <version>1.0-SNAPSHOT</version>
        <packaging>pom</packaging>
    ```

  - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281059822.png)

  - [2]在子工程中声明对父工程的引用（认干爹的一个仪式）

    ```xml
    <!--子工程中声明父工程-->
    <parent>
         <groupId>com.atlml.maven</groupId>
         <artifactId>Parent</artifactId>
         <version>1.0-SNAPSHOT</version>
    
    <!--以当前pom文件为基准的,找父工程pom.xml文件的相对路径-->
        <relativePath>../Parent/pom.xml</relativePath>
    </parent>
    ```

  - [3]在父工程中统一管理junit的依赖

    ```xml
    <!--依赖管理，这里专门用来管理，不能够传递的依赖，进行版本号控制-->
    <dependencyManagement>
        <dependencies>
          <!-- junit是“test”范围的依赖，不能够传递，在这里面统一管理版本号-->
             <dependency>
                 <groupId>junit</groupId>
                 <artifactId>junit</artifactId>
                 <version>4.12</version>
                 <scope>test</scope>
             </dependency>
    
    
        </dependencies>
    </dependencyManagement>
    ```

  - [4]在子工程中删除junit依赖的版本号部分 

    ```xml
    <dependency>
          <groupId>junit</groupId>
          <artifactId>junit</artifactId>
          <!--<version>4.11</version>--> 删除掉
          <scope>test</scope>
    </dependency>
    ```

  - [5]实现效果

    - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281101844.png)

  - [6]：父模块的Pom.xml文件的配置。

    - ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401281101254.png)

## 七、Maven的聚合：

- （聚合就是Maven中，各个模块的一键安装。）

- 注意：配置了继承的模块，在执行安装命令（ install）的时候，要先安装 “父模块”再安装其他模块才能成功。

- Maven中的一件安装，就可以自动的按顺序，将每个模块都按依赖顺序进行安装。

- 实现一件安装步骤：

  - 【1】创建一个“总的聚合工程”，（一般把“父模块”作为“总的聚合工程”，大的情况下也是将，聚合的配置，也配在父模块内）

  - 【2】在一个"总的聚合工程"的pom.xml文件中，配置各个參与聚合的模块

    ```xml
    <!--配置聚合-->
    <modules>
         <!--指定各个子工程的相对路径-->
         <module>../Hellow</module>
         <module>../HellowFriend</module>
    </modules>
    ```

## 八、Maven仓库地址

- [Maven Repository: Search/Browse/Explore (mvnrepository.com)](https://mvnrepository.com/)
- [仓库服务 (aliyun.com)](https://developer.aliyun.com/mvn/search)



## 九、IDEA中Maven配置

[IDEA配置Maven的超详细步骤_java_脚本之家 (jb51.net)](https://www.jb51.net/article/259780.htm)

[IDEA配置Maven（详细版）_idea maven-CSDN博客](https://blog.csdn.net/qq_42057154/article/details/106114515)









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







