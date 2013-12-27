第二章 万物始为先，环境的搭建
=

在介绍怎么用CoffeeScript之前，我们先来搭建环境，就像给没有用过和学过电脑的人说什么是窗口肯定会是一头雾水的，想起高中时学习编程时，第一堂课就讲顺序、选择和循环，听得我直哆嗦，到第二天都还不明白，直到上机了才知道。

CoffeeScript主要用于两种环境中，一、浏览器里。 二、服务器端。下面介绍这两种环境的配置。

###在浏览器里运行
主要分为两步

1. 包含coffee-script.js，官网下载地址：<http://coffeescript.org/extras/coffee-script.js> 。
1. CoffeeScript代码写在标签`<script type="text/coffeescript">`内。



如下：


	<script src="../coffee-script.js" ></script>
	<script type="text/coffeescript">
	# 你的CoffeeScript代码
	alert "世界你好!"
	</script>

> 虽然在浏览器里能直接的运行，但是不建议这样做，主要是考虑到性能的原因。 推荐使用 `coffee`的`-c`参数将coffesscript代码转换到原生的javascript代码，再引入到页面里。

###在服务器上运行
我们需要安装coffee-script脚本，有个比较方便的工具可以使用，npm。打开你熟悉的终端，输入以下命令
`npm -g install coffee-script`
就可以把coffee-script以全局的方式安装到机器，如果只需要安装到当前目录下，可以去掉参数 `-g` 。
安装完成后，测试一下是否安装成功。

	chendeMacBook-Pro:chp1 cheneifei$ npm -gl list|grep -i coffee
		├── coffee-script@1.6.3
		│   git://github.com/jashkenas/coffee-script.git
		│   http://coffeescript.org
		chendeMacBook-Pro:chp1 cheneifei$

表示成了。 接下来就可以使用她提供的命令 coffee来运行文件了，对了CoffeeScript文件一般以coffee为扩展名。
运行一下吧， `coffee chp1_code2.coffee`

好了，环境就到此为止了，如果你还不知道npm, 去这里看看 <https://npmjs.org>

