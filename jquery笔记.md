# jquery

## $('div').hide();

## 入口函数

```js
$(function (){
...//此处是页面DOM加载完成的入口
});
$(document).ready (function (){
此处是页面DOM加载完成的入口
})
    
    
1.等着DOM结构渲染完毕组即可执行内部代码，不必等到所有外部资源载完成，Quy帮我们完成了封装。
2.相当于原生js中的DOMContentLoaded,
3.不同于原生js中的Ioad事件是等页面文档、外部的js文件、css文件、图片加载完毕才执行内部代码。
```

##  jQuery的顶级对象$

$是jQuery的别称，在代码中可以使用jQuery代替$，但一般为了方便，通常都直接使用$。

## jQuery对象和DOM对象

1.用原生JS获取来的对象就是DOM对象
2.jQuery方法获取的元素就是jQuery对象。
3.jQuery对象本质是：利用$对DOM对象包装后产生的对象（伪数组形式存储）。

## 转换对象

```text
1.DOM对象转换为jQuery对象：$(DOM对象)

$('div')
2.jQuery对象转换为DOM对象（两种方式）
$('div')[index]
index是索引号
$('div').get(index)		
index是索引号
```

## 选择器

```text
ID选择器
$("#id")
获取指定ID的元素

全选选择器
$(*)
匹配所有元素

类选择器
$(".class")
获取同一类class的元素

标签选择器
$("div")
获取同一类标签的所有元素

并集选择器
$("div,p,li")
选取多个元素

交集选择器
$("li.current")
交集元素

:first
$('li:first')
获取第一个元素

:last
$('li:last')
获取最后一个元素

:eq(index)
$("li:eq(2)")
获取到的1元素中，选择索引号为2的元素，素引号index从0开始。

:odd
$("li:odd")
获取到的元素中，选择索引号为奇数的元素

:even
$("li:even")
获取到的元素中，选择索引号为偶数的元素


parent()
$("li").parent();
查找父级

children(selector)
$("ul").children("li")
相当于$("u1>1i"),最近一级（亲儿子）

find(selector)
$("ul").find("li");
相当于$("u"),后代选择器

siblings(selector)
$(".first").siblings("li");
查找兄弟节点，不包括自己本身

nextAll([expr])
$(".first").nextAll()
查找当前元素之后所有的同辈元素

prevtAll([expr])
$(".last").prevAll()
查找当前元素之前所有的同辈元素

检查当前的元素是否含有某个特定的类，如
hasClass(class)
$('div').hasClass("protected")
果有，则返回true

eq(index)
$("1i").eq(2);
相当于$("1i:eq(2)"),index从0开始
```

## 设置样式

```text
遍历内部DOM元素（伪数组形式存储）的过程就叫做隐式迭代。
简单理解：给匹配到的所有元素进行循环遍历，执行相应的方法，而不用我们再进行循环，简化我们的操作，方便我们调用。

修改样式css方法

1.参数只写属性名，则是返回属性值
$(this).css("color");

2.参数是属性名，属性值，逗号分隔，是设置一组样式，属性必须勋加引号，值如果是数字可以不用跟单位和引号
$(this).css("color","red");

3.参数可以是对象形式，方便设置多组样式。属性名和属性值用冒号隔开，属性可以不用加引号，
$(this).css({"color":"white","font-size":"20px"));



修改样式操作类
1.添加类
$("div").addClass("current");
2.移除类
$("div").removeClass("current');
3.切换类
$("div").toggleClass("current');
```

## 显示和隐藏效果

```text
显示隐藏效果
1.显示语法规范
show ([speed,[easing],[fn]])
hide()
toggle()
同上


2.显示参数
(1)参数都可以省略，无动画直接显示。
(2)speed:三种预定速度之一的字符串(“slow”，“normal”,or“fast”)或表示动画时长的毫秒数值（如：1000）。
(3)easing:(Optional)用来指定切换效果，默认是“swing”,可用参数“linear'"。
(4)fn:回调函数，在动画完成时执行的函数，每个元素执行一次。
```

## 滑动效果

```text
slideDown()
slideUp()
slideToggle()

[speed,[easing],[fn]]
```

## 停止动画排队

```text
stop()
(1)stop()方法用于停止动画或效果。
(2)注意：stop()写到动画或者效果的前面，相当于停止结束上一次的动画。
```

## 淡入淡出效果

```text
fadeOut()
fadein()
fadeToggle()
[speed],[easing],[fn]

fadeTo()
[speed],opacity,[easing],[fn]
opacity透明度必须写，取值0~1之间。

```

## 自定义动画

```text
1.语法
animate(params,[speed],[easing],[fn])
2.参数
(1)params:想要更改的样式属性，以对像象形试传递，必须写。属性名可以不用带引号，如果是复合属性则需要采取驼峰命名法borderLeft。其余参数都可以省略。
(2)speed:三种预定速度之一的字符串(“slow”，“normal'”,or"fast”)或表示动画时长的毫秒数值（如：1000）。
(3)easing:(Optional)用来指定切换效果，默认是“swing”,可用参数“linear'"。
(4)fn:回调函数，在动画完成时执行的函数，每个元素执行一次。
```

## 属性操作

```text
所谓元素固有属性就是元素本身自带的属性，比如<a>元素里面的href,比如<input>元素里面的type。
1.获取元素固有属性语法
prop("属性")
2.设置元素固有属性语法
prop("属性”，"属性值")

1.获取元素自定义属性语法
attr("属性")//类似原生getAttribute()
2.设置属性语法
attr("属性"，"属性值")//类似原生setAttribute()
```

## 内容文本

```text
1.普通元素内容html(相当于原生innerHTML)
html
html() //获取元素的内容
html("内容")  //设置元素的内容
val() //获取表单的值
val("内容")  //设置表单的值
```

## 遍历

```text
遍历元素
jQuery隐式迭代是对同一类元素做了同样的操作。如果想要给同一类元素做不同操作，就需要用到遍历。
语法1：
$("div").each(function (index,domEle){xxx;}
1.each()方法遍历匹配的每一个元素。主要用DOM处理。each每一个
2.里面的回调函数有2个参数：index是每个元素的索引号；demEle是每个DOM元素对象，不是jquery对象
3.所以要想使用jquery方法，需要给这个dom元素转换为jqueryx对像$(domE1e)




语法2：
$.each(object,function (index,element){xxx;}
1.$.each()方法可用于遍历任何对象。主要用于数组处理，比如数组，对象
2.里面的函数有2个参数：index是每个元素的索引号key；element遍历内容value
```

## jquery尺寸

```text
jQuery尺寸

width()/height()
取得匹配元素宽度和高度值只算width/height

innerWidth()/innerHieght()
取得匹配元素宽度和高度值包含padding

outerWidth()/outerHeight()
取得匹配元素宽度和高度值包含padding、border

outerWidth(true)/outerHeight(true)
取得匹配元素宽度和高度值包含padding、borde、margin
```

## jQuery位置

```text
位置主要有三个：offset()、position()、scrollTop()/scrollLeft()
offset()设置或获取元素偏移
offset()方法设置或返回被选元素相对于文档的偏移坐标，跟父级没有关系。

用法
offset()
offset().top()
offset({
	top:200,
	left:200
})
```

## 事件处理

```text
事件处理on()绑定事件
on()
方法优势1：
可以绑定多个事件，多个处理事件处理程序。
$("div").on ({
	mouseover:function(){},
	mouseout:function (){},
	click:function(){}
})
如果事件处理程序相同
$("div").on ("mouseover mouseout",function(){
	$(this).togglaclass ("current");
});
```

## 事件委派

```text
on()方法优势2：
可以事件委派操作。事件委派的定义就是，把原来加给子元素身上的事件绑定在父元素身上，就是把事件委派给父元素。

s('ul').on ('click','li',function(){
	alert('hello world!');
});

on可以给未来动态创建的元素绑定事件
```

## 事件解绑

```text
off()方法可以移除通过on()方法添加的事件处理程序。

$("div").off("click");/这个是解除了div身上的点击事件
$("u1").off("c1ick","1i");

//2.one()但是它只能触发事件一次
$("p").one("click",function(){
		alert(11)
})
```

## 自动触发事件

```text
element.click()//第一种简写形式
element.trigger("type")//第二种自动触发模式
element.triggerHandler("type")/第三种自动触发模式
```

## 事件对象

```text
事件被触发，就会有事件对象的产生。



element.on(events,[selector],function(event){}) 
阻止默认行为：event.preventDefault()或者return false
阻止冒泡：event.stopPropagation0


$("div").on("click",function(event){
	console.log(event);
	console.log("点击了div");
	event.stopPropagation();
})

```

## 对象拷贝

```text
$.extend([deep],target,object1,[objectN])

1.deep:如果设为true为深拷贝，默认为false浅拷贝
2.target:要拷贝的目标对象
3.object1:待拷贝到第一个对象的对象。
4.objectN待拷贝到第N个对象的对象。
5.浅拷贝是把被拷贝的对象复杂数据类型中的地址拷贝给目标对像，修改目标对象会影响被拷贝对象。



```

