# 任务二

## CSS进阶&JS基础
<hr>
### 时间说明
##### 7.14 - 7.20

### Start

##### 1、盒模型及定位
###### 1.1 任务描述
- 用两种方法来实现一个背景色为<code>红色</code>、宽度为<code>960px</code>的<code>\<DIV></code>在浏览器中居中

- 用两种不同的方法来实现一个两列布局，其中左侧部分宽度固定、右侧部分宽度随浏览器宽度的变化而自适应变化

- 用两种不同的方式来实现一个三列布局，其中左侧和右侧的部分宽度固定，中间部分宽度随浏览器宽度的变化而自适应变化
- 实现一个浮动布局，红色容器中每一行的蓝色容器数量随着浏览器宽度的变化而变化
###### 1.2 达成
- 掌握块状元素、内联元素、和内联块状元素的概念与区别
- 掌握盒模型的所有概念，学会如何计算各种盒模型相关的数值
- 掌握<code>position</code>的相关知识
- 掌握<code>float</code>的相关知识
- 掌握基本的布局方式
###### 1.3 参考资料
- [慕课网](http://www.imooc.com/code/2047)
- [学习CSS布局](http://zh.learnlayout.com/no-layout.html)
- [CSS布局方式](http://teamtreehouse.com/library/css-layout-techniques)
- [双飞翼布局介绍-始于淘宝UED](http://www.imooc.com/wenda/detail/254035)
- [那些年我们一起清除过的浮动 by 一丝冰凉](http://www.iyunlu.com/view/css-xhtml/55.html)
- [CSS 101: Block Formatting Context](http://www.yuiblog.com/blog/2010/05/19/css-101-block-formatting-contexts)
- [w3school](http://w3school.com.cn/css/css_positioning.asp)
- [w3school](http://w3school.com.cn/css/css_boxmodel.asp)

##### 2、CSS综合练习
###### 2.1 任务描述
完成一个网页的计算器页面，不需要有括号，要求有+ - * / 四种运算，只需要展示出计算器的页面，使用CSS来进行布局，尽可能得好看，符合自己的审美。要求：

- 按钮有点击效果，鼠标悬浮的按钮能突出显示
- 整个计算器再页面的正中
- 尽量不使用表格来布局


##### 3、JS基础
###### 3.1 任务目的
掌握`JavaScript`基础知识，能够使用`JavaScript`编写一些复杂度不大的交互功能。
###### 3.2 任务描述
在自己的文件夹中创建一个新的目录，比如`task0002`，在该目录下首先创建一个没有内容的页面： `task0002.html`，这个页面需要包含最基本的HTML结构，它将用于我们后面的任务。

	<!DOCTYPE html>
	<html>
	<head>
    	<meta charset="UTF-8">
    	<title>task0002</title>
	</head>

	<body>
	</body>
	</html>


使用刚刚创建好的`task0002.html`，在这个页面的`</body>`前增加这么一段代码

	<script>
		alert("Hello World!");
	</script>

刷新一下页面，DONE

好吧，这是我们很多年前才干的事情，现在更多时候是这样的

	<script>
		console.log("Hello World!");
	</script>

刷新一下页面，在Chrome中打开开发者工具，看看控制台里发生了什么。记住这个`console.log`，后续你会经常用着它。

接下来来点稍微复杂的，在你的`task0002.html`的`<body>`后增加下面的代码

	<input id="number1" type="text">
	<input id="number2" type="text">
	<span id="result"></span>
	<button id="addbtn"></button>

同时，在`<script>`标签中做一下修改

	<script>
	function $(id) {
    	return document.getElementById(id);
	}

	function add(num1, num2) {
    	return num1 + num2;
	}

	function renderResult(result) {
    	$("result").innerHTML = result;
	}

	function addEventHandle() {
    	var num1 = $("number1").value;
    	var num2 = $("number2").value;
    	var result = add(num1, num2);
    	renderResult(result);
	}

	function initEvent() {
    	$("addbtn").addEventListener("click", addEventHandle, false);
	}

	initEvent();
	</script>

试试在Chrome下看看什么效果，再看看在IE8下什么效果。是不是有什么区别呢？先不着急寻找答案。

然后，试着建立一个新的`xxxx.js`的文件，把上面`<script>`里面的内容剪贴过去，在html中引入这个文件。

接下来的课程主要围绕JavaScript自身的一些基础知识，如果你对计算机编程本身还是不够熟悉，那就建议花比别人更多的时间多写点代码。

###### 3.3 目标
- 了解JavaScript是什么
- 如何在HTML页面加载JavaScript代码
- 搜索一下，为什么我们让你把`<script>`放在`</body>`前。

###### 3.4 参考资料
- [JavaScript 的性能优化：加载和执行](http://www.ibm.com/developerworks/cn/web/1308_caiys_jsload/index.html)

###### 4、JavaScript数据类型及语言基础
####### 4.1 2.1 任务描述

- 创建一个JavaScript文件，比如`util.js`；
- 实践判断各种数据类型的方法，并在`util.js`中实现以下方法：
```
	function isArray(arr) {
    	your implement
	}

	function isFunction(fn) {
    	your implement
	}
```
- 了解值类型和引用类型的区别，了解各种对象的读取、遍历方式，并在`util.js`中实现以下方法：
- 以下
```
	var srcObj = {
	    a: 1,
    	b: {
	        b1: ["hello", "hi"],
        	b2: "JavaScript"
    	}
	};
	var abObj = srcObj;
	var tarObj = cloneObject(srcObj);

	srcObj.a = 2;
	srcObj.b.b1[0] = "Hello";

	console.log(abObj.a);
	console.log(abObj.b.b1[0]);

	console.log(tarObj.a);      // 1
	console.log(tarObj.b.b1[0]);    // "hello"
```



