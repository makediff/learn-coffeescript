第四章 万丈高楼平地起 函数、对象和数组
==

＃函数的定义＃
CoffeeScript中屏弃了function关键字的用法，取而代之的使用 -> 来表明一个函数。如定义函数
`cube = (x)-> x*x*x`
编译成原生的javascript,则为
     var cube;
     cube = function(x){ return x*x*x; }
上面定义的是一个带有参数的函数，如果没有参数，则可以这样
     getTrue = -> true
如果要定义一个空的函数，则更加的简单，如 
nothing = ->
你还可以给函数的参数指定默认值，如
incrNum = (num=3)-> num
函数体的最后一句会默认是函数的返回值，所以 `cube = (x)-> return x*x*x` 可以简写成 `cube = (x)-> x*x*x`

＃函数的调用＃
对于上面定的cube函数，调用的格式如下
cube 3
也可以写成 cube(3), 括号不是必须的， 当单条语句很复杂时，最好加上括号，来区分优先级。
对于熟悉jQuery的读者对于回调函数肯定不会陌生，比如$.post，使用#CS#的语法来调用，就会类似于这样
data = {age:22, addr:"BeiJing"}
$.post data, (strret)->
     console.log strret
函数还支持变参的处理，#todo#查阅资料

＃数组的定义＃
＃CS#的数组的定义和原生的javascript基本时类似的，如
shopping = ["油", "盐", "酱", "醋"] 和原生的javascript代码时一样的, 不同的是，你可以这样来定义
shopping = [
     "油"
     "盐"
     "酱"
     "醋"
]
在这里，逗号不是必须的。如果你加了也是没有关系的，而且#CS#会帮你做好浏览器的兼容。比如原生的这个Javascript代码在IE下就不能很好的工作，但是#CS#可以这样写。
原生的： var shopping = [1, 2, 3, 4, ]  //后面多一个逗号，兼容性不好
#CS#: shopping = [1,2,3,4,] #没有问题

@todos 数组的使用

＃对象字面量的定义＃
scores = { zhangsan:78, lisi: 82 }
scores = 
     zhangsan: 78
     lisi: 82
以上两种写法都是没有问题的，而且不用担心key的名字和javascript的关键字有冲突，如有以下原生的javascript代码，
var studentA = {"class":"一班级", name:"张三" }; //注意，为了不和关键字冲突，这里需要用引号做处理，而#CS#是不用担心这个问题的。
把对象的值赋给变量的时候有一个很酷的功能， {age, addr} = obj
将会把obj.age和obj.addr的值分别赋值

@toods对于数字常量有什么不一样的地方呢
