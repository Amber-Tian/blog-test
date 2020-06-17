# jQuery 介绍
jQuery 是目前前端最长寿的库，2006年发布距今14年；  

jQuery 是世界上使用最广泛的库，全球80%的网站使用（来源：buildwith.com）  

<img src='https://bkimg.cdn.bcebos.com/pic/9f510fb30f2442a79d8d54ced943ad4bd01302dd?x-bce-process=image/watermark,g_7,image_d2F0ZXIvYmFpa2U4MA==,xp_5,yp_5' alt='jQuery图片' height='100px'>  

# jQuery 功能介绍

## 一、获取元素

jQuery的基本设计思想和主要用法，就是**"选择某个网页元素，然后对其进行某种操作"**。这是它区别于其他Javascript库的根本特点。  

使用jQuery的第一步，往往就是将一个选择表达式，放进构造函数jQuery()（简写为$），然后得到被选中的元素。  

选择表达式可以是CSS选择器：  

~~~js
$(document) //整个文档对象

$('#myId') //id元素

$('div.myClass') //class元素

$('input[name=first]') //name属性为first的input元素
~~~

也可以是jQuery特有的表达式：

~~~js
$('a:first') //选择网页中第一个a元素

$('tr:odd') //选择表格的奇数行

$('#myForm :input') // 选择表单中的input元素

$('div:visible') //选择可见的div元素

$('div:gt(2)') // 选择所有的div元素，除了前三个

$('div:animated') // 选择当前处于动画状态的div元素
~~~

## 二、链式操作

$('xxx')获取的元素返回值是一个api对象，可以对它进行一系列操作，并且所有操作可以连接在一起，以链条的形式写出来，比如：

~~~js
$('#myId').find('.myClass').eq(1).html('Hello').css('color', 'red');

//分解开

$('#myId') //找到id为myId的元素

.find('.myClass') //选择其中className为myClass的元素

.eq(1) //选择第2个myClass元素

.html('Hello') //将它的内容改为Hello

.css('color', 'red'); //将它的color改为red
~~~

这是jQuery最令人称道、最方便的特点。它的原理在于每一步的jQuery操作，返回的都是一个jQuery对象，所以不同操作可以连在一起。

jQuery还提供了.end()方法，使得结果集可以后退一步：

~~~js
$('#myId')

.find('.myClass')

.eq(1)

.html('Hello')

.end() //退回到选中所有的myClass元素的那一步 

.eq(0)

.html('World')
~~~

## 三、创建、复制和删除元素

1. 创建

~~~js
$('<p>Hello</p>'); 

$('<li class="new">new list item</li>'); //创建带class属性的元素

$('ul').append('<li>list item</li>'); //创建li并插入到ul
~~~

2. 复制元素使用.clone()

3. 删除元素使用.remove()和.detach()。两者的区别在于，前者不保留被删除元素的事件，后者保留，有利于重新插入文档时使用。清空元素内容（但是不删除该元素）使用.empty()。

## 四、移动元素

jQuery提供两组方法来操作元素在网页中的位置移动。一组方法是直接移动该元素，另一组方法是移动其他元素，使得目标元素达到我们想要的位置。

假定我们选中了一个div元素，需要把它移动到p元素后面。

第一种方法是使用.insertAfter()，把div元素移动p元素后面：

~~~js
$('div').insertAfter($('p'));
~~~

第二种方法是使用.after()，把p元素加到div元素前面：

~~~js
$('p').after($('div'));
~~~

表面上看，这两种方法的效果是一样的，唯一的不同似乎只是操作视角的不同。但是实际上，它们有一个重大差别，那就是返回的元素不一样。第一种方法返回div元素，第二种方法返回p元素。你可以根据需要，选择到底使用哪一种方法。

使用这种模式的操作方法，一共有四对：

~~~js
.insertAfter()和.after() //在现存元素的外部，从后面插入元素

.insertBefore()和.before() //在现存元素的外部，从前面插入元素

.appendTo()和.append() //在现存元素的内部，从后面插入元素

.prependTo()和.prepend() //在现存元素的内部，从前面插入元素
~~~

## 五、修改元素

jQuery使用同一个函数，来完成取值（getter）和赋值（setter），即"取值器"与"赋值器"合一。到底是取值还是赋值，由函数的参数决定。

~~~js
$('h1').html(); //html()没有参数，表示取出h1的值

$('h1').html('Hello'); //html()有参数Hello，表示对h1进行赋值
~~~

常见的取值和赋值函数如下：

~~~js
.html() //取出或设置html内容

.text() //取出或设置text内容

.attr() //取出或设置某个属性的值

.width() //取出或设置某个元素的宽度

.height() //取出或设置某个元素的高度

.val() //取出某个表单元素的值
~~~

需要注意的是，如果结果集包含多个元素，那么赋值的时候，将对其中所有的元素赋值；取值的时候，则是只取出第一个元素的值（.text()例外，它取出所有元素的text内容）。