第四章 万丈高楼平地起 函数、对象和数组
==

> 这一章节里的知识点会比较的多和杂，走马观花的过一遍，在其后的章节中会更加详细的介绍。

##函数的定义
coffeeScript中屏弃了`function`这个关键字的用法，取而代之的使用 `->` 来表明一个函数。

如定义函数 `cube = (x)-> x*x*x`，编译成原生的javascript,则为

     var cube;
     cube = function(x){ return x*x*x; }

上面定义的是一个带有参数的函数，如果没有参数，则可以这样`noncube = -> true`

如果要定义一个空的函数，则更加的简单，如  `nothing = ->`

你还可以给函数的参数指定默认值，如 `incrNum = (num=3)-> num`

函数体的最后一句会认为是函数的返回值，所以 `cube = (x)-> return x*x*x` 可以简写成 `cube = (x)-> x*x*x`

##函数的调用#
对于上面定的cube函数，调用的格式如下

`cube 3`
也可以写成 `cube(3)`, 括号不是必须的， 当单条语句很复杂时，最好加上括号，来区分优先级。

对于熟悉jQuery的读者对于回调函数肯定不会陌生，比如`$.post`，使用coffeescript的语法来调用，就会类似于这样

     data = {age:22, addr:"BeiJing"}
     $.post data, (strret)->
          console.log strret


##数组的定义#
coffeescript的数组的定义和原生的javascript基本是类似的，如
`shopping = ["油", "盐", "酱", "醋"]` 和原生的javascript代码是一样的, 不同的是，你可以这样来定义

     shopping = [
          "油"
          "盐"
          "酱"
          "醋"
     ]
     
在这里，逗号不是必须的。如果你加了也是没有关系的，而且coffeescript会帮你做好浏览器的兼容。

数组的定有还有一个讨厌的兼容性问题，比如这个 `var shopping = [1, 2, 3, 4, ]`  ,这里后面多一个逗号，这个Javascript代码在IE下就不能很好的工作。
但是在coffeescript中，如这个`shopping = [1,2,3,4,]` ,是没有问题,coffeescript会帮你做好兼容处理。


##对象字面量的定义

     scores = { zhangsan:78, lisi: 82 }
     scores = 
          zhangsan: 78
          lisi: 82
以上两种写法都是没有问题的，而且不用担心key的名字和javascript的关键字有冲突，如有以下原生的javascript代码，
`var studentA = {"class":"一班级", name:"张三" }; `,注意，为了不和关键字冲突，这里需要用引号做处理，而coffeescript是不用担心这个问题的。
把对象的值赋给变量的时候有一个很酷的功能， `{age, addr} = obj`
将会把obj.age和obj.addr的值分别赋值。
