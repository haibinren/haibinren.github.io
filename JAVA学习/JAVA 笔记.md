# JAVA script 笔记
----
- 如何插入JS
  - 在HTML网页中插入JavaScript代码 <script></ srcipt>
  - 引入外部.js文件 <script src="script.js"></script> 
## 其他命令
- DOM 操作页面的命令
    - 写出到页面：
      - 可用于直接向输出流写内容。简单的说就是直接在网页中输出内容。。
      

           -      document.write("I love"); //内容用""括起来，""里的内容直接输出。
           document.write(mystr);//直接写变量名，输出变量存储的内容。
           document.write(mystr+"I love JavaScript");//多项内容之间用+号连接
           document.write(mystr+"<br>");//输出hello后，输出一个换行符
         
## 弹窗提示：
- prompt(str1, str2); 弹出对话框
    - str1: 要显示在消息对话框中的文本，不可修改
    - str2：文本框中的内容，可以修改
    - 1. 点击确定按钮，文本框中的内容将作为函数返回值
    - 2. 点击取消按钮，将返回null
- alert();    (字符串或变量); 
    -  alert弹出消息对话框(包含一个确定按钮)。
-  confirm(char内容);
    - confirm() 弹出一个确定和取消的窗口
    -  当用户点击"确定"按钮时，返回true
     -    当用户点击"取消"按钮时，返回false
             

                -            function rec(){
                    var mymessage=confirm("你是男士还是女士" )    ;
                    if(mymessage==true)
                    {
                    	document.write("你是女士!");
                    }
                    else
                    {  
                        document.write("你是男士!");
                    }
                  }  
     
- JavaScript-打开新窗口（window.open）   
    - window.open([URL], [窗口名称], [参数字符串])
    - 参数说明：
    
                URL：可选参数，在窗口中要显示网页的网址或路径。如果省略这个参数，或者它的值是空字符串，那么窗口就不显示任何文档    。
            窗口名称：可选参数，被打开窗口的名称。
                1.该名称由字母、数字和下划线字符组成。
                2."_top"、"_blank"、"_self"具有特殊意义的名称。
                   _blank：在新窗口显示目标网页
                   _self：在当前窗口显示目标网页
                   _top：框架网页中在上部窗口中显示目标网页
                3.相同 name 的窗口只能创建一个，要想创建多个窗口则 name 不能相同。
               4.name 不能包含有空格。
            参数字符串：可选参数，设置窗口参数，各参数用逗号隔开。
        -参数列表
        ![image](http://img.mukewang.com/52e3677900013d6a05020261.jpg)


        <script type="text/javascript">
        
        window.open('http://www.imooc.com','_blank','width=300,height=200,menubar=no,toolbar=no, status=no,scrollbars=yes')
        </script>
        
- JavaScript-关闭窗口（window.close）
    - window.close();   //关闭本窗口
    - <窗口对象>.close();   //关闭指定的窗口
    - 
                        - <script type="text/javascript">
                       var mywin=window.open('http://www.imooc.com'); //将新打的窗口对象，存储在变量mywin中
                       mywin.close();
                    </script>

## 变量
省略。。。。
## 函数
- function 函数名()
    - 1. function定义函数的关键字。
    - 2. "函数名"你为函数取的名字。
    - 3. "函数代码"替换为完成特定功能的代码。
## 多种查找元素（元素选择器）的方法：
- 1.getElementById(id)   
    - getElementById() 
    - 参数： 元素ID属性值 。 必须。
    - 返回： 指定ID元素的对象
    - 定义： 获取指定ID元素的对象  并返回。
    - 如果没有指定 ID 的元素返回 null
    - 如果存在多个指定ID的元素则返回 undefined。

- 2.getElementsByName() 
    - 返回带有指定名称的对象集合。
- 3.getElementsByTagName()。
    - 返回带有指定标签名的对象集合。



-----------------------



## 认识DOM
- 文档对象模型DOM（Document Object <br> Model）定义访问和处理HTML文档的标准方法。DOM <br> 将HTML文档呈现为带有元素、属性和文本的树结构（节点树）。
----
### HTML文档可以说由节点构成的集合，三种常见的DOM节点:
-  **元素节点：** 上图中<html>、<body>、p>等都是元素节点，即标签。
-   **文本节点:**
  向用户展示的内容，如li>.../li>中的JavaScript、DOM、CSS等文本。
-   **属性节点:**
元素属性，如a>标签的链接属性href="http://www.imooc.com"。
-----
## 通过ID获取元素
- 学过HTML/CSS样式，都知道，网页由标签将信息组织起来，而标<br>签的id属性值是唯一的，就像是每人有一个身份证号一样，只要通<br>过身份证号就可以找到相对应的人。那么在网页中，我们通过id先找到标签，然后进行操作。
- **语法:**
        
        document.getElementById(“id”) 
- **返回值：**
    结果:null或[object HTMLParagraphElement]
- **实例**

        <!DOCTYPE HTML>
        <html>
        <head>
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title>document.getElementById</title>
        </head>
        <body>
        <p id="con">JavaScript</p>
        <script type="text/javascript">
          var mychar= document.geElemenById("con"); //通过指定ID 获取元素 并赋值给变量
          document.write("结果:"+mychar); //输出获取的P标签。 
        </script>
        </body>
        </html>
        
**innerHTML 属性**
- innerHTML 属性用于获取或替换 HTML 元素的内容
    - **注意：**
     - Object是获取的元素对象，如通过document.getElementById("ID")获取的元素。
     
    - 我们通过id="con"获取p>元素，并将元素的内容输出和改变元素内容，代码如下:


            function myGetId(){
            var mychar = document.getElementById("con");
            document.write("原标题:" + mychar.innerHTML + "<br>"); //输出原h2标签内容
            mychar.innerHTML = "New text!";
            document.write("修改后的标题:" + mychar.innerHTML); //输出修改后h2标签内容
             }


**改变 HTML 样式**
- 基本属性表
- 用法：
    变量.样式.属性(下的属性)用大写

        mychar.style.backgroundColor ="blue";
     
     
    ![image](http://img.mukewang.com/52e4d4240001dd6c04850229.jpg)

    - 改变 p> 元素的样式，将颜色改为红色，字号改为20,背景颜色改为蓝：
        
            <p id="pcon">Hello World!</p>
            <script>
           var mychar = document.getElementById("pcon");
           mychar.style.color="red";
           mychar.style.fontSize="20";
           mychar.style.backgroundColor ="blue";
            </script>
            
**显示和隐藏（display属性）**
    
-  网页中经常会看到显示和隐藏的效果，可通过display属性来设置
-  **注意:** Object是获取的元素对象，如通过document.getElementById("id")获取的元素。
-  **语法：** Object.style.display = value
- **value取值:**
![image](http://img.mukewang.com/52e4dba5000179da04110095.jpg)
- 示例：

            <!DOCTYPE HTML>
            <html>
            <head>
            <meta http-equiv="Content-Type" content="text/html; charset=gb2312">
            <title>display</title>
                <script type="text/javascript"> 
                    function hidetext()  
            		{  
            		var mychar = document.getElementById("con");
                        mychar.style.display="none"
            		}  
            		function showtext()  
            		{  
            		var mychar = document.getElementById("con");
                        mychar.style.display= "block"
            		}
                </script> 
            </head> 
            <body>  
                <h1>JavaScript</h1>  
                <p id="con">做为一个Web开发师来说，如果你想提供漂亮的网页、令用户满意的上网体验，JavaScript是必不可少的工具。</p> 
                <form>
                   <input type="button" onclick="hidetext()" value="隐藏内容" /> 
                   <input type="button" onclick="showtext()" value="显示内容" /> 
                </form>
            </body> 
            </html>


 **控制类名（className 属性）**
- className 属性设置或返回元素的class 属性。
- **语法：** object.className = classname
- **作用：** <br>
1.获取元素的class 属性
2. 为网页内的某个元素指定一个css样式来更改该元素的外观<br>
==3. 为变量指派一个CSS样式 值：css的名称==
- 看看下面代码，获得 p> 元素的 class 属性和改变className：
- 
                <!DOCTYPE HTML>
            <html>
            <head>
            <meta http-equiv="Content-Type" content="text/html; charset=gb2312">
            <title>className属性</title>
            <style>
                body{ font-size:16px;}
                .one{
            		border:1px solid #eee;
            		width:230px;
            		height:50px;
            		background:#ccc;
            		color:red;
                }
            	.two{
            		border:1px solid #ccc;
            		width:230px;
            		height:50px;
            		background:#9CF;
            		color:blue;
            	}
            	</style>
            </head>
            <body>
                <p id="p1" > JavaScript使网页显示动态效果并实现与用户交互功能。</p>
                <input type="button" value="添加样式" onclick="add()"/>
            	<p id="p2" class="one">JavaScript使网页显示动态效果并实现与用户交互功能。</p>
                <input type="button" value="更改外观" onclick="modify()"/>
            
            	<script type="text/javascript">
            	   function add(){
            	      var p1 = document.getElementById("p1");
            	      p1.className = "one";
            	   }
            	   function modify(){
            	      var p2 = document.getElementById("p2");
            	      p2.className= "two";
            	   }
            	</script>
            </body>
            </html>

## 编程挑战
- 小伙伴们，请编写"改变颜色"、"改变宽高"、"隐藏内容"、"显示内容"、"取消设置"的函数，点击相应按钮执行相应操作，点击"取消设置"按钮后，提示是否取消设置，如是执行操作，否则不做操作。
##### 任务
一、定义"改变颜色"的函数<br>
提示:<br>
    obj.style.color<br>
    obj.style.backgroundColor <br>
二、定义"改变宽高"的函数<br>
提示:<br>
obj.style.width<br>
obj.style.height <br>
三、定义"隐藏内容"的函数<br>
提示:<br>
obj.style.display="none";<br>
四、定义"显示内容"的函数<br>
提示:<br>
obj.style.display="block";<br>
五、定义"取消设置"的函数<br>
提示: <br>
使用confirm()确定框，来确认是否取消设置。<br>
如是将以上所有的设置恢复原始值,否则不做操作。<br>
六、当点击相应按钮，执行相应操作，为按钮添加相应事件<br>

    <!DOCTYPE HTML>
    <html>
    <head>
    <meta http-equiv="Content-Type" Content="text/html; charset=utf-8" />
    <title>javascript</title>
    <style type="text/css">
    body{font-size:12px;}
    #txt{
        height:400px;
        width:600px;
    	border:#333 solid 1px;
    	padding:5px;}
    p{
    	line-height:18px;
    	text-indent:2em;}
    </style>
    </head>
    <body>
      <h2 id="con">JavaScript课程</H2>
      <div id="txt"> 
         <h5>JavaScript为网页添加动态效果并实现与用户交互的功能。</h5>
            <p>1. JavaScript入门篇，让不懂JS的你，快速了解JS。</p>
            <p>2. JavaScript进阶篇，让你掌握JS的基础语法、函数、数组、事件、内置对象、BOM浏览器、DOM操作。</p>
            <p id="onoff">3. 学完以上两门基础课后，在深入学习JavaScript的变量作用域、事件、对象、运动、cookie、正则表达式、ajax等课程。</p>
      </div>
      <form>
      <!--当点击相应按钮，执行相应操作，为按钮添加相应事件-->
        <input type="button" value="改变颜色" onclick="funcColor()">  
        <input type="button" value="改变宽高" onclick="funcWH()" >
        <input type="button" value="隐藏内容" onclick="funcDisplay1()">
        <input type="button" value="显示内容" onclick="funcDisplay2()" >
        <input type="button" value="取消设置" onclick="funcRest()" >
      </form>
      <script type="text/javascript">
    //定义"改变颜色"的函数
    var myCorlor = document.getElementById("con");
    
    function funcColor(){
        myCorlor.style.color="red";
    }
    //定义"改变宽高"的函数
    var myWH = document.getElementById("txt");
    
    function funcWH(){
        myWH.style.width="500px";
        myWH.style.height="300px";
    }
    //定义"隐藏内容"的函数
    var myDp1 = document.getElementById("onoff");
    function funcDisplay1(){
        
        myDp1.style.display="none"
    }
    //定义"显示内容"的函数
    function funcDisplay2(){
        myDp1.style.display="block";
    }
    //定义"取消设置"的函数
    var myConfirm;
    function funcRest() {
        myConfirm= confirm("是否重置样式");
        if(myConfirm==true){
            myCorlor.style.color="";
            myWH.style.width="";
            myWH.style.height="";
            myDp1.style.display="";
        }
        else{
           myConfirm= alert("你点击了取消");
        }
    }
      </script>
    </body>
    </html>
