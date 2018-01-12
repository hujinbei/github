# 创建方块之间的转换

** 插入一个红色方块，并在箭头移入红色方块中时变成更大的蓝色方块，鼠标移除方块时，再度回到初始的红色方框样式；**

1、打开sublime text 键入以下代码：

```javascript
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" 
	"http://www.w3.org/TR/html4/loose.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" >
<head>
<meta http-equiv="Content-Type" content="text/html" charset="utf-8" />
<title>JavaScript</title>
<style type="text/css">
	 #div1 {width: 100px; height: 100px; background:red; }
.boxs
 {	
	width: 200px;
	height: 200px;
	background:red; 
}
</style>
<script src="/Users/huhuhu/Desktop/sublime文件/JS/jquery-3.2.1.min.js"></script>
<script type="text/javascript">
window.onload=function ()
{
	var oDiv = document.getElementById('div1');
	oDiv .onmouseover=toGreen;
	oDiv .onmouseover=toRed;
}

function toGreen()
{

	var oDiv1 = document.getElementById('div1');

	oDiv1.style.width='200px';
	oDiv1.style.height='200px';
	oDiv1.style.background='green';
}

function toRed()
{

	var oDiv1 = document.getElementById('div1');

	oDiv1.style.width='100px';
	oDiv1.style.height='100px';
	oDiv1.style.background='red';
}
</script>
</head>
<body>
	<div id="div1" onmouseover="toGreen()" onmouseout="toRed()"></div>
	    
</body>
</html>


```

* 显示为，但是鼠标移入方块范围内时，无法改变其形状和颜色

![](/Users/huhuhu/Desktop/sublime文件/JS/redbox/image/4.png)

* 此时在浏览器页面空白处单击右键，选择"检查"，弹出代码检查的窗口，出现如下错误；

![](/Users/huhuhu/Desktop/sublime文件/JS/redbox/image/5.png)

![](/Users/huhuhu/Desktop/sublime文件/JS/redbox/image/1.png)

![](/Users/huhuhu/Desktop/sublime文件/JS/redbox/image/2.png)

![](/Users/huhuhu/Desktop/sublime文件/JS/redbox/image/3.png)

** 没有查找到相关的解决方案，所以更换了另一种代码的结构来实现此操作：**

2、更换结构后的代码为：

```javascript
<!DOCTYPE html>
<html>
<head>
	 <title>JS特效测试</title>
	<meta charset="utf-8">
	<style type="text/css">
		.div1{
			width: 100px;
			height: 100px;
			background-color: red;
		}			/*设置初始方块的形状和颜色*/
	</style>
	<script src="/Users/huhuhu/Desktop/sublime文件/JS/jquery-3.2.1.min.js"></script>
    <!--引入jQuery文件(javascript框架)-->
	<script type="text/javascript">
		$(document).ready(function(){
        //设置编辑function函数
			$(".div1").hover(function () {
				$(this).css('background-color','blue');
				$(this).css('width','200px');
				$(this).css('height','200px');
			 },	//鼠标放在初始方块上时变换为蓝色的大方块
			function () {
				$(this).css('background-color','red');
				$(this).css('width','100px');
				$(this).css('height','100px');
			});   //鼠标移除方框时，又变回初始方框的样式
		});
	</script>
</head>
<body>
	<div class="div1"></div>
</body>
</html>
```
* 保存后，在浏览器中打开新的.html文件，该代码成功得显示了预期的效果；

** 初始状态：红色方块**

![](/Users/huhuhu/Desktop/sublime文件/JS/redbox/image/7.png)

** 鼠标移入：蓝色大方块**

![](/Users/huhuhu/Desktop/sublime文件/JS/redbox/image/8.png)

** 鼠标移出：变回红色方块**

![](/Users/huhuhu/Desktop/sublime文件/JS/redbox/image/7.png)

