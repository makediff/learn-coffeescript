第五章 细说函数
==

说到函数不外乎四大要素：函数的名字、函数的参数、函数体和函数的返回值。coffeescript的核心的思想，
就是让你用最少最舒服的代码写出原有同样的功能，
而且更优雅。

##麻雀虽小五脏俱全
先来看一个原生的例子，假设我要写一个这样的函数`var isGreatThenTen = function (x){ return x>10; }`，
这个函数用来判断一个数是否大于10，那我们用coffeescript要怎么写呢？如下：

    isGreatThenTen = (x) -> x>10

看明白了吗？是不是很简洁？那我们来分解一下，四大要素都在哪儿。

1. `isGreatThenTen`是函数的名字
2. `(x)` 用来指定参数
3. `->` 相当于原来的`function`关键字
4. `x>10`在这里既是函数体同时也是返回值， coffeescript会默认的把函数体里的 **最后执行的** 一条语句的值最为函数的返回值， **注意** ：这里并不一定是最后一条语句，大家试着去理解一下。

> 不要怜惜你的手，赶快去执行一下吧

完整的代码如下：

    isGreetThenTen = (x) -> x>10
    console.log isGreatThenTen(20)
    console.log isGreatThenTen(9)
如果没有出意外的话你的结果也因该是

    true
    false

##极致的精简
那如何定义一个空的函数呢？ `var emptyFunc = function(){};`
其实很简单，`emptyFunc = -> `，是不是简单到让人看不懂？
coffeescript中`(x) -> x` 代表了函数的参数、函数体和函数返回值，其中参数和函数体不是必须的，但 **->** 是必须的！
那我要返回一个函数，这样写你能看得懂了吧? ` tfunc = -> ->`。

> Tips: 实践出真知，要多动手，记住这里的一条就够了： 多用 coffee -c 编译coffescript脚本和你预期的对比来学习。

##函数的调用
对于上面定义的`isGreetThenTen`函数，我们可以通过有括号的和没有括号两种方式来调用， `isGreatThenTen(10)`或`isGreatThenTen 10`。
如果一行上同时有多个函数的调用，为了避免优先级的混淆，建议加上括号。建议采用`console.log isGreqtThenTen(10) `而不是`console.log isGreetThenTen 10`。

##函数体
