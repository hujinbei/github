# 在HTML中调用.js文件

1、首先建立一个.js文件，输入代码后尝试运行，为了方便查看，这里将输出结果定义为“C”；

```
function convert(celsius) {

	return fahrenheit=celsius*9/5+32;
}
var C= convert(30);

```



2、然后建立一个.html文件，将刚才的.js文件调用，输入以下代码：

```
<!DOCTYPE html>
<html>
<head>
	<title>html调用</title>
	<meta charset="utf-8">
<script src="test1.js"></script>  <!--在script标签中调用文件时，不同文件夹下的文件需要输入路径-->
</head>
<body>

</body>
</html>
```

![](/Users/huhuhu/Desktop/sublime文件/JS/调用js文件/image/1.png)

** 由于此时的.js文件没有对html进行写入，所以就算调用进.html文件后依然无法显示，所以**

## .js文件写入html的方法：

* 第一种方法：在.js文件中输入"alert(C);",利用弹框输出结果"C"的值

![](/Users/huhuhu/Desktop/sublime文件/JS/调用js文件/image/5.png)

* 效果如下图所示

![](/Users/huhuhu/Desktop/sublime文件/JS/调用js文件/image/2.png)

* 第二种方法：输入"document.write('< h1>'+'转换结果:'+C+'< /h1>');
",利用文字输出“C”的值，

```
function convert(celsius) {

	return fahrenheit=celsius*9/5+32;
}
var C= convert(30);
document.write('<h1>'+'转换结果:'+C+'</h1>');
```

![](/Users/huhuhu/Desktop/sublime文件/JS/调用js文件/image/4.png)

* 结果为

![](/Users/huhuhu/Desktop/sublime文件/JS/调用js文件/image/3.png)