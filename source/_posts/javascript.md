---
title: javaScript
date: 2019-10-01 12:00:00
author: 𝚲𝚳𝚲
tags:   # 添加博文标签
	- javaScript
categories:   # 添加博文分类
	- java
---



<h1><center>javaScript</center></h1>

> 静态网页资源的三剑客：HTML（文本），CSS（样式），JavaScript（行为）。把后面两个效果，加在HTML文本上，就会呈现出很好看的网页界面。
>
> 1. 程序设计有两种架构：1 c/s架构，是客户端和服务器端，要开发两个程序。2 b/s架构，是浏览器和服务端。只用浏览器来申请服务器端的资源，再展示出来就好了。只用开发服务器端一个软件。
> 2. javaWeb开发，是B/S架构的。
> 3. 事件：事件是什么意思？通俗的理解，HTML中的元素组件，被某个动作（事件的属性），触动后，会发生一定的变化。（执行了另一个js代码）。
> 4. 将HTML，CSS，JavaScript分别独立出来，可以降低耦合度，
>
> javaScript最初被设计用于浏览器中，他和java语言没有关系，他是客户端脚本语言
>
> javaScript语言运行出错，要在浏览器控制台上面查看。F12打开控制台。

- 

## 一、javaScript

- 注意：在一个html的页面中，可以定义多个script的标签，而且存放的位置是任意的，但是会影响运行的先后顺序，一般都是等html页面元素全部加载完毕，再运行js代码，并且是一种等待状态。当在html中的某个位置，触发了某个事件，此时对应的js等待代码，就会执行。从而产生行为效果

### 1.javascript与HTML的关联方式：

- 内部关联

- ![image-20240130214055735](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302141892.png)
- 外部关联
- ![image-20240130214133935](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302141171.png)



### 2.javascript的数据类型

- >
  >
  >原始数据类型：
  >
  >          1. number：数字 。 整数/小数/ NAN （not  a number 一个不是数字的数字类型）
  >             2. string ：字符串。字符串 "abc" "a" 'abc'
  >             3. boolean：true 和 false
  >             4. null：一个对象为空的占位符
  >             5. undefined：未定义，如果一个变量没有给他初始化值，则会被默认赋值为undefined
  >
  >注意：NaN是number类型，他是（不是数字的数字）。在js当中，运算符，后面的运算数，不是运算符要求的类型，js就会自动的将运算数进行类型转换。比如：numb= +"abc";此时：number根据"+"运算符，如果是数字，就会直接转换成数字，但是转换符后面跟的不是数字类型，则会转换成不是数字的数字类型。值为NaN.

### 3.JavaScript的变量

- 什么是变量：变量就是内存空间中的一小片区域。有类型，有名称，有值。比如：int a=3;
- JavaScript的变量是弱类型的，什么叫弱类型，就是不管定义什么类型的变量，都用var开头。
- 而java中定义整型用int，定义字符型用char 。所以java是强类型的。
- ☆ 通过typeof(变量名)可以得到变量的类型
- ![image-20240130215045915](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302150588.png)

- 注释:你也许会问,为什么typeof运算符对于nul值会返回"object".这实际上是javaScript最初实现中的个错误,然后被
  ECMAScript沿用了,现在,null被认为是 对象的占位符,从而解释了这一矛盾,但从技求上来说,它仍是原始值。

### 4.javascript中的运算符

- #### ①一元运算符：就是只有一个运运算数的运算符。

  - ++ 、--、+（正号）、-（负号）
  - “++（--）”在前，先自增（自减），再运算。
  - “++（--）”在后，先运算，再自增（自减）。
  - +（-）（正负号）

- ![Image](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302204727.png)

- ####  ②算数运算符：“+”，“-”，“* ”，“/” ，“%”（和java中使用方法相同）

- #### ③赋值运算符：“+=”，“-=”“=”（和java中使用方法相同）

- #### ④ 比较运算符：“>”，“<”，“>=”，“<=”，“==”，   “= ==（全等于）”

  - “= =”是比较两个数是否相等，“===全等于”是加上了类型的比较。

- ### ⑤ 逻辑运算符：“&&”，“||”，“！”

  - ![Image [3]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302211570.png)

- ### ⑥ 三元运算符“ <u>？：表达式</u>”

  - ![Image [4]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302211345.png)

## 二、javascript 中的特殊语法.

(了解一下就好，但是要和java规范一样写代码，不要省“；”，也不要省“var”，带var的变量，是局部变量，不带var的变量是全局变量 。)

## 三、流程控制语句

![Image [5]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302213021.png)

## 练习 ：javascript（9x9乘法表）

![Image [6]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302213809.png)

---

---

## 四、BOM对象：

- #### 概念：Browser object Model 浏览器对象模型。将浏览器各个组成部分封装为对象。

- ![Image [13]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302312704.png)

- #### BOM对象有五个：窗口对象、历史记录对象、地址栏对象、浏览器对象、显示器对象。

  ### ① window窗口对象。

  - #### window窗口的第一类方法：弹窗有关的方法

  - ![image-20240130231750600](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302317649.png)

  -  ####  window窗口的第二类方法：打开关闭窗口的方法。

  - ![image-20240130232026695](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302320023.png)

  - #### window窗口的第三类方法：与定时器有关的方法

  - ![image-20240130232218944](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302322466.png)

  - #### Window窗口对象属性，可以获取其他BOM对象，和一个DOM对象document（.html文件对象）。直接写就可以用

  - ![Image [27]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302327561.png)

## ②、 Location地址栏对象

- Location 对象的方法。reload().用来刷新当前页面。 属性：href

- Location地址栏对象，他的一个属性href。有两个作用，设置当前页面的URL和获取当前页面的完整的URL.（这里面的设置和获取URL都是针对当前页面的。设置的话，就是重新赋值，设置为新的地址，这样当前页面就会跳转到设置的地址页面中去）

- ![Image [28]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302328922.png)

- ### 倒计时跳转网页案例

- ![image-20240130233011287](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302330863.png)

## ③、 history当前页面历史记录对象。

- 属性：length：history.length；返回的是。历史记录的个数。 
- 方法：back();加载history列表中的上一个URL。绑定单击事件，就可以做一个后退的按钮。
- 方法： forword(); 加载history列表中的下一个URL。绑定单击事件，就可以做一个前进的按钮。
- 方法：go(); 加载history列表中的某一个具体页面。

---

---

## 五、DOM对象（只要是标记语言都有DOM对象，我们这里说的是HTML DOM对象。）

- #### ☆ DOM对象，其实就是把html文档里面的各个标签，都看做是一个对象。

- #### ☆操作DOM对象，就相当于，在内存层面，来写HTML的代码。没有实体的标签，每个标签，都定义成了对象，每个标签都是一个节点对象。

- #### DOM方式：就是将标记语言，把文本全部给加载到内存里面去，形成一个DOM树。（标记语言文本的解析） 

- #### DOM对象：通俗理解就是将HTML或者XML标记语言，各个部分封装为一个一个的对象。（一对标签可以看做一个对象，也叫节点，因为在树上）。在内存中对应着DOM树形结构。

- ![Image [7]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302230077.png)

- ### ①：document对象、最大的DOM对象。（html文档对象），其他的标签对象，都在他的内部，所以是通过document来，获取Element(其他标签对象)对象。或者是创建Element (其他标签对象)对象。

  - ##### document.write("<hr>")   向页面上写出一条横线（就是往页面写出信息的）     

  - #### 1.1 document对象：获取element对象的方法。

  - >
    >
    >1. getElementById（） ：根据id属性值获取元素对象。id属性值一般唯一
    >2. getElementsByTagName （） ：根据元素名称获取元素对象们。返回值是一个数组
    >3. getElementsByClassName （）：根据Class属性值获取元素对象们。返回值是一个数组
    >4. getElementsByName（）：根据name属性值获取元素对象们。返回值是一个数组

  - #### 1.2  document对象：创建其他DOM对象：

  - >
    >
    >1. createElement（“标签名”）：创建元素节点（记住）
    >2. createAttribute（name）：创建拥有指定名称的属性节点，并返回新的Attr对象。（了解）
    >3. createComment（）：创建注释节点。（了解）
    >4. createTextNode（）：创建文本节点。（了解）

- ### ②：Element对象（元素标签对象）

  - 1，获取/创建：通过document来获取和创建
  - 2.方法：
    - removeAttribute（“”） ：删除属性
    - setAttribute（“属性名”，“属性值”） ：设置属性值。
  - 补充：input框框，有个value属性，用其节点对象.value可以得到，文本框里面的内容。
  - ![Image [8]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302239426.png)

- ### ③：Node对象 （是所有DOM对象的父亲），它里面定义了，对节点的，增删改的方法。所以所有的DOM对象，都有这三类方法。这样所有的当前节点，都可以添加它的子节点，也都可以删除它的子节点，也可以获取它的父节点。

- appendchild（节点对象名） ：向节点的子节点列表的结尾添加新的子节点。（增）

- removechild（节点对象名） ：删除（并返回）当前节点的指定子节点。（删）

- replacechild（节点对象名） ：用新节点替换一个子节点。（改，不常用）。

- 属性：父节点=当前节点.parentNode; 返回当前节点的父节点。

- ![Image [9]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302240885.png)

## 六、☆javascript 中的几个对象的学习。

- ### 1.☆ function函数方法对象、Array数组对象。

- function对象，在javascript 中，定义方法，是用function对象，来定义方法的。

  > - 语法：function 方法名（参数列表）{方法体}
  > - // javascript中定义方法，的写法和java类似。 但是是用的function对象定义的方法
  > - // js中用function定义的方法，参数列表不用写类型，返回值不用写类型
  > - // js中用function定义的方法，如果有多个同名的方法，那么后面的同名方法，会覆盖前面的同名方法，
  > - // js中用function定义的方法，在调用方法时，只要方法名确定就会调用最后面的同名不同参数的方法。他和参数列表无关。
  > - /* js中用function定义的方法，参数列表的括号里面隐藏了一个内置对象，是一个arguments的数组。 所以当参数列表中不写形式参数时，function add(){ 方法体} 括号里面就是一个可变形参 每一个传递过来的实参，都存在arguments[0].arguments[1]........等数组中。 */

- ![Image [31]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302336101.png)
- ![Image [32]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302336754.png)

- ### 2.☆ Array数组对象

  - ![image-20240130233856091](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302338259.png)
  - ![image-20240130233912957](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302339764.png)
  - ![image-20240130233952371](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302339719.png)
  - ![image-20240130234025914](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302340524.png)
  - ![image-20240130234102744](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302341187.png)

- ### 3.☆ Date日期对象

  - ![image-20240130234717315](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302347839.png)

- ### 4.☆Math数学对象

  - ![image-20240130234909211](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302349463.png)

- ### 5.☆ regExp：正则表达式对象。

  - ##### 先了解什么是正则表达式

  - 正则表达式就是定义字符串的组成规则（通用的规则，在Java中或者其他语言中都可以使用）。在表单的输入框的地方，实现校验输入的字符串是不是符合正则表达式的规则。不符合校验失败，阻止表单的提交。 

  - ☆ Javascript对表单的校验，是依赖于正则表达式的。

  - ![image-20240130235118937](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302351087.png)

  - ### 正则表达式对象。regExp

  - ![image-20240130235241803](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302352011.png)

- ### 6.☆全局对象

  - 在javascript中，有一个全局对象Global，他不用创建对象，直接用其内部的方法，就可以实现对应的功能，一般有字符串的URL编解码方法。
  - ![image-20240130235441038](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302354439.png)

---

---

## 七、 事件绑定的方式

![Image [10]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302309137.png)

![Image [11]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302310432.png)

- ### 得到标签元素的对象。来换其属性值，和换其内容值。要查看参考文档找对应对象的方法。

![Image [12]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401302310594.png)

---

---

## 八、HTML DOM：是关于如何获取、修改、添加或删除HTML元素的标准

- ### ☆①所有的节点对象都有的关键的属性innerHTML

  - innerHTML。是获取节点对象，里面的所有内容。就是获取了，一对“<>标签体</>”中的标签体的内容。标签体可以是一段文字，也可以是其他标签。 

  - 通过给innerHTML赋值或者追加值，可以改表标签体的内容。如下图

  - ![image-20240131000856980](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310008885.png)

  - ![image-20240131000909451](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310009414.png)

  - ![image-20240131000922589](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310009904.png)

  - ##### 上图中第3行，之后的表格，都是通过JavaScript代码（里面操作各种对象），一行一行添加的。很面向对象。写出来的代码非常的多。就会想简化写法。用innerHTML可以直接获取到上面的table的标签体，并且在后面追加样式就好了。这样简化了js代码，但不是面向对象了。

- ### ☆②所有的节点对象都有的关键的属性style。

  - #### 1.给style属性赋值，就可以改变其样式。

    - ![Image [70]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310010681.png)

  - 注意：两个单词的写法

  - ![Image [71]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310011498.png)

  - ![image-20240131001138257](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310011810.png)

  - ### 2. 改变节点对象的class值。用className属性。

  - ![Image [72]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310012825.png)

  - ![Image [73]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310012327.png)

  - #### 3.要想设置和修改，节点的属性值。查Api文档。例如：<img> 标签图片标签，每出现一次，一个 Image 对象就会被创建。找image对象的属性，src设置或返回图像的 URL

---

---

##  九、事件

![Image [74]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310015267.png)

- ### 事件分类

  - #### 1.点击事件

  - >1. onclick：单机事件
    >
    >2. ondblclick ：双击事件

  - #### 2.焦点事件

  - >1. onblur：失去焦点
    >   * 一般用于表单验证,当光标不在输入框时，就会失去焦点，触发onblur事件发生。
    >2. onfocus：元素获得焦点

  - #### 3.加载事件

  - >1. onload：一张页面或者一幅图像完成加载
    >
    >- 内部加载方式：script标签如果写在head标签里面，在上面的话，要使用窗口的事件机制，加载事件来控制，js 代码，在HTML页面加载完全，才运行。
    >- 如下图
    >- ![Image [80]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310030871.png)

  - #### 4.鼠标事件

  - >1. onmousedown ：标按钮披按下.
    >
    >* 定义方法时,定义一个形参,接受 event 对象.
    >* eventi对象的button属性可以获取鼠标按钮键被点击了.
    >
    >2. onmouseup  ：鼠标按键被松开.
    >3. onmousemove ：鼠标被移动.
    >4. onmouseover：鼠标移到某元素之上.
    >5. onmouseout：鼠标从某元素移开.

  - #### 5.键盘事件

  - >1. onkeydown： 某个键盘按键被按下.
    >2. onkeyup ：某个键盘按键被松开.
    >3. onkeypress： 某个键盘按键被按下并松开.

  - #### 6.选择和改变事件

  - >1. onchange：域的内容被改变.
    >
    >   - #### ☆ 当在选择的下拉列表上，选择某个选项会触发该事件。
    >
    >   - ![Image [81]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310032281.png)
    >
    >2. onselect：文本被选中.

  - #### 7.表单事件:

  - >1. onsubmit：确认按钮被点击.
    >   * 可以阻止表单的提交
    >     * 方法返回falsel则表单被阻止提交.
    >   * 写法：
    >   * ![Image [82]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310033920.png)
    >   * ![Image [83]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310033022.png)
    >
    >2. onreset：重置按钮被点击.

---

---

## 练习：动态表格案例

![image-20240131000210183](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310002855.png)

![image-20240131000243636](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310002593.png)

![image-20240131000254150](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310003451.png)

![image-20240131000332037](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310003911.png)

- ☆动态表格案例总结：用DOM对象在内存层面你，不管创建了多少子节点或者父节点，这些结构都是在内存层面上的，在浏览器页面上不能够直接显示，要想显示，必须有html的已有标签对象。先获取已有的html标签对象节点，将内存层面上的节点，appendChild为已有节点的子节点。同时，属性的样式会关联到css样式表中，只要和css表中的选择器对应的上，就可以显示样式。
- ☆ 技巧：怎样获取当前标签的对象，直接在html标签后面，加上事件属性。绑定事件方式一，事件调用指定方法，括号里面写this。
- ![image-20240131000404203](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310004539.png)
- 那么就可以在方法声明的地方，形式参数就是当前对象。如下图：
- ![Image [62]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310004456.png)

---

---

## 总结1：

- ### 怎么来理解BOM对象和DOM对象以及HTML DOM对象？

- 1 . BOM对象，就是将浏览器各个组成部分，封装为对象。有显示器对象、浏览器对象、windows窗口对象、URL地址栏对象、以及历史记录对象，这5个BOM对象。windows窗口对象，是BOM对象中的主要对象，因为其他对象都在一个窗口当中。可以通过windows对象来获取，其他4个BOM对象。
- 2 .在windows窗口获取的document对象，是DOM对象。
  
  - document对象是DOM对象的主要对象。DOM对象也在窗口内，但是只有document对象（.html文件对象）是通过窗口获取，其他DOM对象是通过document对象获取的。
- 3 .document对象，他是将整个文档封装成一个document对象。对应着HTML里面最外层标签<html></html>。他可以获取其他节点对象
  
  - document.getElementById()；。或者对象们；另外也可以创建其他DOM对象。
- 4.有了一些基础的DOM对象，也就是有了某个标签的（节点）的对象之后。然后用HTML DOM来、对这个对象进行获取、修改、添加或删除操作。
- 5.从上往下看，一层一层的，从窗口(window)——>文本对象(document)——>单个文本元素对象(element)——>单个文本元素操作（HTML DOM）这样方便记忆。也便于理解。
- 节点：在HTML中所有的单个元件，就是单个节点。对应着一对，一对的标签。
- 子节点：外标签包着内标签，也就是节点包着子节点。例如：<body>文字 <a>超链接</a></body>。
- Node 节点对象：他可以认为是虚有的，它里面的方法用来“CRUDdom树”
- 其实就是所有的DOM对象，都是一个节点，DOM对象本身，就可以增加节点，删除节点，替换节点，查询节点。
- 有了DOM这些对象，用他们的功能。就可以用javaScript语言对HTML的标签进行操作。
- 要记住：虽然能用，JavaScript语言来操作，内存层面的HTML的元素对象代码，使其在浏览器上面显示样式。但是他和HTML里面的标签没有，任何关系。
  
  - 执行了“JavaScript语言操作的元件对象，比如添加节点，删除节点”不会再HTML文档中自动生成，HTML代码。

![Image [84]](https://gitee.com/lmlpla/blogimages/raw/master/imgs/202401310036188.png)



- ### 理解、标签、标签体、标签属性、控制元素的样式。

  >1.1标签: 标签就是一对对的<></>。例如：``<img> </img> ``
  >
  >1.2标签体:一对标签里面的内容。例如：``<img>这是标签体，可以是子标签也可以是文字 </img>``
  >
  >1.3 标签属性: 定义在标签<>里面的。例如：``<a href="javascript:void(0)"></a>``
  >
  >1.4 标签控制样式:

## 总结2：

- #### 一般都是先加载了web的HTML界面之后，JavaScript脚本语言才会加载，这样js里面获取的元素对象，才会被拿到。如果是内部加载的话。所以要求 ``<script>js代码</script>``，标签一般都写在``<body>......<script></body>``body标签的最下面。

- ####  js代码（可以理解为一个一个的等待的动作），就像是当HTML页面加载完全之后，它已经运行了内部代码，但是，都还是在等待的状态。如果界面中触发了某个事件，就会执行相应“事件器代码”，完成效果。

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



