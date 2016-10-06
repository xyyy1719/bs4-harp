[http://harpjs.com/]

#### harp有2个功能

1. 用来做为静态网页生成器
2. 本地服务器

#### 安装

```
npm install -g harp
harp version
```

#### 例子

创建项目目录bs4-harp, 并在该目录下创建子目录css和js, 把bootstrap.min.css放入css目录, 把bootstrap.min.js和jquery.min.js放入js目录
在项目根目录下创建文件_layout.ejs

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
	<meta http-equiv="x-ua-compatible" content="ie=edge">
	<link rel="stylesheet" type="text/css" href="css/bootstrap.min.css">
	<title>Document</title>
</head>
<body>
	<%- yield %>

	<script type="text/javascript" src="js/jquery.min.js"></script>
	<script type="text/javascript" src="js/bootstrap.min.js"></script>
</body>
</html>
```

再创建文件index.ejs

```
<h1>Hello World!</h1>
```

在项目根目录下打开命令行输入

```
harp compile
```

harp会把_layout.ejs作为静态网页的模板, 并把同一目录下的其他ejs文件的内容替换到<%- yield%>的位置, 产生新的html文件
命令运行完毕后, 会在根目录下生成一个www目录, 里面的文件可以直接发布的服务器上

运行harp服务器
在项目目录下打开命令行输入

```
harp server
```

打开网页, 输入网址http://localhost:9000

