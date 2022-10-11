# css选择器

| 选择器                                                       | 示例       | 示例说明                             | CSS  |
| :----------------------------------------------------------- | :--------- | :----------------------------------- | :--- |
| [.*class*](https://www.runoob.com/cssref/sel-class.html)     | .intro     | 选择所有class="intro"的元素          | 1    |
| [#*id*](https://www.runoob.com/cssref/sel-id.html)           | #firstname | 选择所有id="firstname"的元素         | 1    |
| [*](https://www.runoob.com/cssref/sel-all.html)              | *          | 选择所有元素                         | 2    |
| *[element](https://www.runoob.com/cssref/sel-element.html)*  | p          | 选择所有<p>元素                      | 1    |
| *[element,element](https://www.runoob.com/cssref/sel-element-comma.html)* | div,p      | 选择所有<div>元素和<p>元素           | 1    |
| [*element* *element*](https://www.runoob.com/cssref/sel-element-element.html) | div p      | 选择<div>元素内的所有<p>元素         | 1    |
| [*element*>*element*](https://www.runoob.com/cssref/sel-element-gt.html) | div>p      | 选择所有父级是 <div> 元素的 <p> 元素 | 2    |

# 字体

```css
设置字体系列
font-family:"Microsoft Yahei";
字体大小
font-size:16px;
字体粗细
font-weight:bold;
```

| 属性值  | 描述                                                    |
| ------- | ------------------------------------------------------- |
| normal  | 默认值（不加粗的）                                      |
| bold    | 定义粗体（加粗的）                                      |
| 100-900 | 400等同于normal,而700等同于bold注意这个数字后面不跟单位 |

```css
font-style:normal;
```

| 属性值 | 作用                                                 |
| ------ | ---------------------------------------------------- |
| normal | 默认值，浏览器会显示标准的字体样式font-style:normal; |
| italic | 浏览器会显示斜体的字体样式。                         |

# 文本

```css
颜色
color:red;
color:#ff0000;
color:rgb(200,0,0);

对齐
text-align:center;
text-align:left;
text-align:right;

装饰
text-decoration:
none
默认。没有装饰线
underline
下划线。链接a自带下划线（常用）
overline
上划线。
line-through
删除线。

缩进
text-indent:2em;
段落的首行缩进（自然段）
em是一个相对单位，就是当前元素（font-size)1个文字的大小，如果当前元素没有设置大小，则会按照父元素的1个文字大小。

行间距
line-height:26px;
行间距=上间距+下间距+文本高度



```

# css引入方式

## 第一种：内联

这种是在标签内直接写的，style="  "，如图所示：

给一个div块加一个宽高都为300px的样式。这种方式会让html代码冗余，做小demo或者刚接触html的可以使用，但是不建议使用这种方式，知道有这种方式就可以了。

## 第二种：内嵌

这种是在head标签里，加一个style标签，在style里添加样式，如图所示：

给这个div块加一个背景颜色为红色的样式。这种方式会让这个页面太“重”了，同样是做小demo或者刚接触html的可以使用，也不建议使用。

## 第三种：外联

这种是新建一个.css文件，通过link来引入样式，如图所示：

在css文件中，直接写样式即可，通过link来把样式引到.html文件中。这种方式是常用的方式，单独的一个css文件夹内放css的内容，把每个部分分的详细一些，也好去管理。

# Emmet语法

## 1.1快速生成HTML结构语法

1.生成标签直接输入标签名按tab键即可比如div然后tab键，就可以生成\<div>\</div>
公
2.如果想要生成多个相同标签加上*就可以了比如
div\*3就可以快速生成3个div
3.如果有父子级关系的标签，可以用，比如ul>li就可以了	
4.如果有兄弟关系的标签，用+就可以了比如div+p
5.如果生成带有类名或者id名字的，直接写.demo或者#two tab键就可以了
6.如果生成的div类名是有顺序的，可以用自增符号$ 

7.div{1}*3可以生成3个内容为1的div

# 链接伪类选择器

```css
a:link	/*选择所有未被访问的链接*/
a:visited	/*选择所有已被访间的链接*/
a:hover	/*去选择鼠标指针位于其上的链接*/
a:active	/*选择活动链接（鼠标按下未弹起的链接）*/
```

# focus伪类选择器

:focus伪类选择器用于选取获得焦点的表单元素。
焦点就是光标，一般情况\<input>类表单元素才能获取，因此这个选择器也主要针对于表单元素来说。

```css
input:focus {
    background-color:yellow;
}
```

# 背景

```css
背景颜色
background-color:transparent;
transparent(透明色)

背景图片
background-image:url();
background-image:none;

背景平铺
background-repeat:
repeat
no-repeat
repeat-x
repeat-y

背景图片位置
background-position:x y;
参数值			说明
length		百分数|由浮点数字和单位标识符组成的长度值
position	top|center|bottom|left|center|right方位名词

背景图像固定
background-attachment:
scroll	背景图像是随对象内容滚动
fixed	背景图像固定

背景色半透明
background:rgba(0,0,0,0.5);

背景缩放
background-size
background-size属性规定背景图像的尺寸
background-size:背景图片宽度背景图片高度；
单位：长度|百分比cover |contain;
covr把背景图像扩展至足够大，以使背景图像完全覆盖背景区域。
contair把图像图像扩展至最大尺寸，以使其宽度和高度完全适应内容区域
```

# CSS三个特性

## **一、CSS层叠性**

- 说明
  层叠性是多种CSS样式的叠加，是浏览器处理样式冲突的方式。在HTML中对于同一个元素可以有多个CSS样式存在，当有相同权重的样式存在时，会根据这些样式出现的先后顺序来决定，处于最后面的CSS样式将会覆盖前面的CSS样式。
- 举例
  下面代码，出现一个div 标签指定了相同样式不同值的情况，这就是样式冲突。

```css
div{
    color:red;
}
div{
    color:blue;
}
```

- 原则
  通常出现样式冲突，会按CSS书写的顺序，以最后的样式为准。

1. 样式不冲突，不会层叠。
2. 样式冲突，遵循就近原则。 长江后浪推前浪，后面样式盖前面。

## **二、CSS继承性**

- 说明
  简单的理解为—“子承父业“，是指子标签会继承父标签的==**某些**==样式，如文本颜色和字号。想要设置一个可继承的属性，只需将它应用于父元素即可。
- 举例

```css
<style>
    div{color:pink;font-size:20px;}
</style>
<div>
    <span>
        我是什么颜色的？
    </span>
</div>
```

- 注意

1. 合理使用继承可以简化代码，降低CSS样式的复杂性。对于字体、字号、颜色、行距等**==文本类属性==**具有继承性，都可以在body中统一设置，然后影响文档中所有文本。
2. 但是，并不是所有的CSS属性都可以继承，如边框、外边距、内边距、背景、定位、元素高度等**==与块级元素相关的==**属性都不具有继承性

## **三、CSS优先级**

在复杂CSS样式表，往往并不是相同样式不同值的堆叠这么简单，经常出现两个或多个不同样式规则应用在同一元素上，这时到底采用哪个样式呢？这就是典型的CSS优先级问题。

处理优先级问题，就是考虑样式权重的高低。这里先给大家介绍一些特殊的情况：

1. **==继承样式的权重为0。==**也就是说，在嵌套结构中，无论父元素样式权重多大，子元素继承时，应用在子元素上的权重都为0，即子元素定义的样式会覆盖所有继承来的样式。
2. **==行内样式优先。==**应用style属性的元素，其行内样式的权重非常高，可以理解为远大于100。总之，他拥有比上面提高的选择器都大的优先级。
3. 权重相同时，CSS遵循就近原则。也就是说靠近元素的样式具有最大的优先级，或者说排在最后的样式优先级最大。
4. CSS定义了一个!important命令，该命令被赋予最大的优先级。也就是说不管权重如何以及样式位置的远近，!important都具有最大优先级。

# 盒子模型

## 1.块级盒的默认宽度

如果未声明宽度，并且盒子是静态或者相对定位的，宽度会保持 100％的 宽度，padding 和 border 会向内推动，而不是向外扩展。

但是，如果明确设置盒子的宽度为 100％，那么 padding 就会向外延展。

## 2.无宽度的绝对定位盒子

未设定宽度的绝对定位的盒子的表现有点不一样。它们的宽度只需要适合它们所包含的内容即可。因此，如果盒中只有一个单词，盒子就会像那个词的表现一样宽。如果变成两个词，盒子的宽度也会相应增加。这种情况会持续到盒子的宽度达到父元素宽度的 100%（最近的相对定位的父元素或者浏览器窗口），然后就会折行。

## 3.无宽度浮动盒子

同无宽度的绝对定位盒子的表现一样。盒子的宽度只需要扩展到所包含内容的宽度，直到其父元素的宽度（其父元素不必是相对定位的）。

## 关于子盒子和父盒子大小之间的关系

1.当父盒子不给高度宽度的时候，默认由子盒子撑开父盒子的大小，相当于子盒子和父盒子此时是重叠在一起的
2.当父盒子给了宽高，如果子盒子的大小超出了父盒子，子盒子就会溢出

## border边框

```css
border-width	定义边框粗细，单位是px
border-style	边框的样式
实线	solid	
虚线	dashed
border-color	边框颜色
border-bottom	下边框
border-top	上边框


表格<table>细线边框
border-collapse:collapse;
合并相邻边框
```

## padding内边距

```css
padding:5px;
1个值，代表上下左右都有5像素内边距：
padding:5px 10px;
2个值，代表上下内边距是5像素	左右内边距是10像素；
padding:5px 10px 20px;
3个值，代表上内边距5像素	左右内边距10像素下内边距20像素；
padding:5px 10px 20px 30px;
4个值，上是5像素	右10像素	下20像素	左是30像素	顺时针

padding-left:
padding-top:

如果盒子本身没有指定width/height属性，则此时padding不会撑开盒子大小。

```

## margin外边距

```css
块级盒子水平居中
margin:0 auto;

外边距合并
嵌套块元素垂直外边距的塌陷
对于两个嵌套关系（父子关系）的块元素，父元素有上外边距同时子元素也有上外边距，此时父元素会塌陷较大的外边距值。

解决方案：
1.可以为父元素定义上边框。
形成一个外边距
内容区城
2.可以为父元素定义上内边距。
内容区城
3.可以为父元素添加overflow:hidden
```

## margin负值运用

## 行内元素或者行内块元素水平居中

给其父元素添加

```css
text-align:center
```

即可

# 圆角边框

```css
border-radius:length;
50%为圆或椭圆
```

# 阴影

```css
盒子阴影
box-shadow:		;
h-shadow
必需。水平阴影的位置。允许负值。
v-shadow
必需。垂直阴影的位置。允许负值。
blur
可透。模期距离。
spread
可选。阴影的尺寸。
color
可选，阴影的颜色。
请参问CSS颜色值.
inset
可选，将外部阴影(outset)改为内部阴影。


文字阴影
text-shadow:		;
h-shadow
必需。水平阴影的位置。允许负值，
v-shadow
垂直阴影的位置。允许负值。
blur
可选。模糊的距离。
color
可选。阴影的颜色。
参阅CSS颜色值。
```

# 浮动

```css
float:none;
none
元素不浮动
(默认值)
left
元素向左浮动
right
元素同右浮动
```

## 清除浮动

```css
父盒子自身不方便给高度

方法
1.额外标签法会在浮动元素末尾添加一个空的标签。例如<div style=”clear:both”></div>,或者其他标签
(如<br/>等)。
element::after {
     /* 我是父盒子元素后面新增的伪元素，背景颜色绿色
      content: '';
      display: block;
      clear: both;
      background-color: green;
  }
2.父级添加overflow属性 value为hidden,auto,scroll

```

## 浮动不会压住标准流的文字

```css
4.绝对定位（固定定位)会完全压住盒子
浮动元素不同，只会压住它下面标准流的盒子，但是不会压住下面标准流盒子里面的文字（图片）
但是绝对定位（固定定位）会压住下面标准流所有的内容。
浮动之所以不会压住文字，因为浮动产生的目的最初是为了做文字环绕效果的。文字会围绕浮动元素
```

# 定位

## 静态定位

```css
position:static	 标准流
在流中的元素定位属性值默认都为"static"，即没有定位。此时元素会忽略"top"、"bottom"、"left"、"right"和"z-index"定位属性。
```

## 相对定位

```css
相对定位是元素在移动位置的时候，是相对于它原来的位置来说的（自恋型）。
position:realtive;

相对定位的特点：（务必记住）
1.它是相对于自己原来的位置来移动的（移动位置的时候参照点是自己原来的位置）。
2.原来在标准流的位置继续占有，后面的盒子仍然以标准流的方式对待它。（不脱标，继续保留原来位置）
```

## 绝对定位

```css
position:absolute;
绝对定位的特点：（务必记住）
1.如果没有祖先元素或者祖先元素没有定位，则以浏览器为准定位(Document文档)。
2.不占有原来位置
```

## 粘性定位

```css
position:sticky;
top:10px;
粘性定位的特点：
1.以浏览器的可视窗口为参照点移动元素（固定定位特点）
2.粘性定位占有原先的位置（相对定位特点）
3.必须添加top、left、right、bottom其中一个才有效
```

## 定位叠放次序

```css
z-index:1;
数值可以是正整数、负整数或0，默认是auto,数值越大，盒子越靠上
```

# display

```css
display属性用于设置一个元素应如何显示。
●display:none;隐藏对象
●display:block；除了转换为块级元素之外，同时还有显示元素的意思
display隐藏元素后，不再占有原来的位置。
后面应用及其广泛，搭配S可以做很多的网页特效。
```

# visibility

```css
visibility属性用于指定一个元素应可见还是隐藏。
●isibility:visible;元素可视
●visibility:hidden;元素隐藏
visibility隐藏元素后，继续占有原来的位置。
```

# overflow

```css
overflow属性指定了如果内容谥出一个元素的框（超过其指定高度及宽度）时，会发生什么。
属性值
描述
visible
不剪切内容也不添加滚动条
hidden
不显示超过对象尺寸的内容，超出的部分隐藏掉
scroll
不管超出内容否，总是显示滚动条
auto
超出自动显示滚动条，不超出不显示滚动条
一般情况下，我们都不想让溢出的内容显示出来，因为溢出的部分会影响布局。
但是如果有定位的盒子，请慎用overflow:hidden因为它会隐藏多余的部分。
```

# 精灵图

1.精灵图主要针对于小的背景图片使用。
2.主要借助于背景位置来实现background-position。
3.一般情况下精灵图都是负值。（千万注意网页中的坐标：轴右边走是正值，左边走是负值，y轴同理。）

# 字体图标

```css
在CSS样式中全局声明字体：简单理解把这些字体文件通过css引入到我们页面中。
注意字体文件路径的问题。
@font-face{
font-family:'icomoon';
src:url (fonts/icomoon.eot?7kkyc2');
src:url (fonts/icomoon.eot?7kkyc2#iefix')format ('embedded-opentype'),
url('fonts/icomoon.ttf?7ktyc2')format ('truetype'),
url (fonts/icomoon.woff?7kkyc2')format ('woff'),
url (fonts/icomoon.svg?7kkyc2#icomoon')format ('svg');
font-weight:normal;
font-style:normal;
    }
```



# css三角

```css
div {
width:O;
height:0;
    
  /*考虑兼容性  */
line-height:0;
font-size:0;
    
    
border:50px solid transparent;
border-left-color:pink;
}
```



# 鼠标样式

```css
cursor:			;
default
小白默认
pointer
小手
move
移动
text
文本
not-allowed
禁止
```

# 取消表单轮廓和防止拖拽文本域

```css
给表单添加outline:O;或者outline:none;样式之后，就可以去掉默认的蓝色边框。

resize:none;
防止拖拽文本域
```

行内块和文字垂直居中对齐

```css
<style>
textarea {
    vertical-align:middle;
}
</style>
<body>
<textarea name=-"id-"cols="30"rows="10"></textarea>请您留言
</body>
```

# 文本溢出省略号

```css
1.单行文本溢出显示省略号-必须满足三个条件
/*1.先强制一行内显示文本*/
white-space:nowrap;(默认normal自动换行)
/*2.超出的部分隐藏*/
overflow:hidden;
/*3.文字用省略号替代超出的部分*/
text-overflow:ellipsis;
```

# html5

## 语义话标签

```css
<header>:头部标签
<nav>:导航标签
<article>:内容标签
<section>:定义文档某个区域
<aside>:侧边栏标签
<footer>:尾部标签
```

## 视频标签

```css
<video>
```

| 属性     | 值                                        | 描述                                              |
| -------- | ----------------------------------------- | ------------------------------------------------- |
| autoplay | autoplay                                  | 视频就绪自动播放（谷歌浏览器需要添加muted来解决） |
| controls | controls                                  | 向用户显示播放控件                                |
| width    | pixels(像素)                              | 设置播放器宽度                                    |
| height   | pixels(像素)                              | 设置播放器高度                                    |
| loop     | loop                                      | 播放完是否继续播放该视频，循环播放                |
| preload  | auto(预先加载视频)<br/>none(不应加裁视频) | 规定是否预加载视频如果有了autoplay就忽略该属性    |
| src      | url                                       | 视频url地址                                       |
| poster   | Imgurl                                    | 加载等待的画面图片                                |
| muted    | muted                                     | 静音播放                                          |

## 音频标签

```css
<audio>
```

| 属性     | 值       | 描述                                           |
| -------- | -------- | ---------------------------------------------- |
| autoplay | autoplay | 如果出现该属性，则音频在就绪后马上播放         |
| controls | controls | 如果出现该属性，则向用户显示控件，比如播放按钮 |
| loop     | loop     | 如果出现该属性，则每当音频结束时重新开始播放。 |
| src      | url      | 要播放的音频的URL。                            |

## input类型

```css
type="email"
限制用户输入必须为Email类型
type="url"
限制用户输入必须为URL类型
type="date"
限制用户输入必须为日期类型
type="time"
限制用户输入必须为时间类型
type="month"
限制用户输入必须为月类型
type="week"
限制用户输入必须为周类型
type="number"
限制用户输入必须为数字类型
type="tel"
手机号码
type="search""
搜索框
type="color"
生成一个颜色选择表单
```

## 表单属性

```css
required	required
表单拥有该属性表示其内容不能为空，必填
placeholder			提示文本
表单的提示信息，存在默认值将不显示
autofocus		autofocus
自动聚焦属性，页面加载完成自动聚焦到指定表单

autocomplete			off on
当用户在字段开始键入时，浏览器基于之前键入过的值，应该显示出在字段中填写的选项。
默认已经打开，如autocomplete="on",关闭autocomplete="off
需要放在表单内，同时加上name属性，同时成功提交
multiple		multiple
可以多选文件提交
```

# css3

## 属性选择器

```css
E[att]
选择具有att属性的E元素
E[att="val"]
选择具有att属性且属性值等于val的E元素
E[att^="val"]
匹配具有att属性且值以val开头的E元素
E[att$="val"]
匹配具有att属性且值以val结尾的E元素
E[att*="val"]
匹配具有att属性且值中含有val的E元素
```

## 结构伪类选择器

```css
E:first-child
匹配父元素中的第一个子元素E
E:last-child
匹配父元素中最后一个E元素
E:nth-child(n)
匹配父元素中的第n个子元素E
E:first-of-type
指定类型E的第一个
E:last-of-type
指定类型E的最后一个
E:nth-of-type(n)
指定类型E的第n个
```

## 盒子模型border-sizing

```css
1.box-sizing:content--box
盒子大小为width+padding+border(以前默认的)

2.box-sizing:border-box
盒子大小为width
如果盒子模型我们改为了box-sizing:border-box,那padding和border就不会撑大盒子了（前提padding和border不会超过width宽度)
```

## 图片模糊处理

```css
filter:函数();例如：filter:blur(5px);
blur模糊处理数值越大越模糊
```

## 计算

```css
calc()
此CSS函数让你在声明CSS属性值时执行一些计算。
width:calc(100%-80px);
括号里面可以使用+-*/来进行计算。
```

## 属性过渡

```css
transition:要过渡的属性花费时间运动曲线何时开始；
1.属性：想要变化的css属性，宽度高度背景颜色内外边距都可以。如果想要所有的属性都变化过渡，写一个all就可以。
2.花费时间：单位是秒（必须写单位）比如0.5s
3.运动曲线：默认是ease(可以省略)
4.何时开始：单位是秒（必须写单位）可以设置延迟触发时间默认是0s(可以省略)
```

# transform

## translate

```css
transform:translate(x,y);或者分开写
transform:translateX(n);
transform:translateY(n);
定义2D转换中的移动，沿着X和Y轴移动元素
translate最大的优点：不会影响到其他元素的位置
translate中的百分比单位是相对于自身元素的translate:(50%,50%):
对行内标签没有效果
和相对定位很像
```

## rotate

```css
1.语法
transform:rotate(度数)
2.重点
rotate里面跟度数，单位是deg比如rotate(45deg)
角度为正时，顺时针，负时，为逆时针
默认旋转的中心点是元素的中心点
```

## 2D转换中心点transform-origin

```css
我们可以设置元素转换的中心点
1.语法
transform-origin:x y
2.重点
注意后面的参数X和y用空格隔开
x y默认转换的中心点是元素的中心点(50% 50%)
还可以给xy设置像素或者方位名词(top bottom left right center)
```

## 2D转换之缩放scale

缩放，顾名思义，可以放大和缩小。只要给元素添加上了这个属性就能控制它放大还是缩小。

```css
1.语法
transform:scale(x,y);
2.注意
注意其中的x和y用逗号分隔
transform:scale(1,1):宽和高都放大一倍，相对于没有放大
transform:scale(2,2):宽和高都放大了2倍
transform:scale(2):只写一个参数，第二个参数则和第一个参数一样，相当于scale(2,2)
transform:scale(0.5,0.5):缩小
sacle缩放最大的优势：可以设置转换中心点缩放，默认以中心点缩放的，而且不影响其他盒子
```

# 动画

## 1.用keyframes定义动画（类似定义类选择器）

```css
@keyframes 动画名称{
 0%{
		width:100px;
}
 100%{
        width:200px;
 }

```

## 使用动画

```css
animation-name:动画名称;
animation-duration:持续时间;
```

## 常用属性

```css
@keyframes
规定动画。
animation
所有动画属性的简写属性，除了animation-play-state属性。
animation-name
规定@keyframes动画的名称。（必须的）
animation-duration
规定动画完成一个周期所花费的秒或毫秒，默认是0。（必须的）】
animation-timing-function
规定动画的速度曲线，默认是“ease”。
6
animation-delay
规定动画何时开始，默认是0。
animation-iteration-count
规定动画被播放的次数，默认是1，还有infinite
animation-direction
规定动画是否在下一周明逆向播放，默认是“normal",alternatej逆播放
animation-play-state
规定动画是否正在运行或暂停。默认是"running"还有"pause"。
animation-fill-mode
规定动画结束后状态，保持forwards回到起始packwards
```

## 简写

```css
animation:动画名称 持续时间 运动曲线 何时开始播放 次数 是否反方向 动画起始或者结束的状态；
animation:myfirst 5s linear 2s infinite alternate;
简写属性里面不包含animation-play-state
暂停动画：animation-play-state:puased;经常和鼠标经过等其他配合使用
想要动画走回来，而不是直接跳回来：
animation-direction:alternate
盒子动画结束后，停在结束位置：animation-fill-mode:forwards
```

# 3D 转换

```css
3D移动在2D移动的基础上多加了一个可以移动的方向，就是z轴方向。
translform:translateX(1OOpx):仅仅是在x轴上移动
translform:translateY(100px):仅仅是在Y轴上移动
translform:translateZ(100px):仅仅是在Z轴上移动（注意：translateZ一般用px单位）
transform:translate3d(x,y,z):其中x、y、Z分别指要移动的轴的方向的距离
```

## 透视perspective

```css
在2D平面产生近大远小视觉立体，但是只是效果二维的
如果想要在网页产生3D效果需要透视（理解成3D物体投影在2D平面内）。
模拟人类的视觉位置，可认为安排一只眼睛去看
透视我们也称为视距：视距就是人的眼睛到屏幕的距离
距离视觉点越近的在电脑平面成像越大，越远成像越小、
透视的单位是像素
透视与在被观察元素的父盒子上面的
d:就是视距，视距就是一个跄璃人的眼睛到屏幕的距离。
z：就是Z轴，物体距离屏幕的距离，轴越大（正值）我们看到的物体就越大。
```

## 3D转换

```css
transform:rotateX(45deg):沿着x轴正方向旋转45度
transform:rotateY(45deg):沿着y轴正方向旋转45deg
transform:rotateZ(45deg):沿着Z轴正方向旋转45deg
transform:rotate3d(X,y,z,deg):沿着自定义轴旋转deg为角度（了解即可）
```

## meta视口标签

```css
<meta name="viewport"content="width=device-width,user-scalable=no,
initial-scale=1.0,maximum-scale=1.0,minimum-scale=1.0">
属性
解释说明
width
宽度设置的是viewporti宽度，可以设置device-width特殊值
initial-scale
初始缩放比，大于0的数字
maximum-scale
最大缩放比，大于0的数字
minimum-scale
最小缩放比，大于0的数字
user-scalable
用户是否可以缩放，yes或no(1或0)
```

# 流式布局(百分比布局)

- 流式布局，就是百分比布局，也称非固定像素布局。
- 通过将盒子的宽度设置成百分比，从而根据屏幕的宽度来进行伸缩，不受固定像素的限制，内容向两侧填充。
- 注意事项：需要定义页面的最大和最小支持宽度。

# flex布局

```css
flex-direction:设置主轴的方向
justify-content:设置主轴上的子元素排列方式
flex-start
默认值从头部开始如果主轴是轴，则从左到右
flex-end
从尾部开始排列
center
在主轴居中对齐（如果主轴是轴侧水平居中）
space-around
平分利余空间
space-between
先两边贴边再平分剩余空间（重要〕



flex-wrap:设置子元素是否换行
nowrap
默认值，不换行
wrap
换行



align-content:设置侧轴上的子元素的排列方式（多行）
flex-start
默认值在侧轴的头部开始排列
flex-end
在侧轴的尾部开始排列
center
在侧轴中间显示
space-around
子项在侧轴平分利余空间
space-between
子项在侧轴先分布在两头，再平分剩余空间
stretch
设置子项元素高度平分父元素高度



align--items:设置侧轴上的子元素排列方式（单行）
flex-start
从上到下
flex-end
从下到上
center
挤在一起居中（垂直居中）
stretch
拉伸（默认值）



fley-flow:复合属性，相当于同时设置了flex-direction和flex-wrap



flex布局子项
fleX属性定义子项目分配剩余空间，用flex来表示占多少份数。
item{
	flex:<number>;/*default 0 */
}


align-self控制子项自己在侧轴上的排列方式
align-self属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。
默认值为auto,表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。
span:nth-child(2){
/*设置自己在侧轴上的排列方式*/
align-self:flex-end;
}


order属性定义项目的排列顺序
数值越小，排列越靠前，默认为0。
注意：和z-index不一样。
```

# rem布局

```css
rem单位
rem(root em)是一个相对单位，类似于em,em是父元素字体大小。
不同的是rem的基准是相取对于html元素的字体大小。
比如，根元素(html)设置font-size=12px非根元素设置width:2rem;则换成px表示就是24pX
```

# 媒体查询

### 语法规范

```css
@media mediatype and|not|only (media feature){
CSS-Code;
}
用@media开头注意@符号
mediatype媒体类型
关键字and not only
media feature媒体特性必须有小括号包含	
```



### 例子

```css
<link rel="stylesheet"href="style320.css"media="screen and (min-width:320px)">
<link rel="stylesheet"href="style640.css"media="screen and (min-width:640px)">
```

## less

vscode插件easy less

vscode插件cssrem 自动将px转为rem

```css
Less变量
变量是指没有固定的值，可以改变的。因为我们CSS中的一些颜色和数值等经常使用。
vscode下载


@变量名:值：
变量命名规范   
必须有@为前缀
不能包含特殊字符
不能以数字开表
大小写敏感
@color:red;
@font14:14px;
div{
color:@color;
font-size:@font14;
}

    
Less嵌套
我们经常用到选择器的嵌套
#header .logo{
		width:300px
}
Less嵌套写法
#header{
    .logo {
        width:300px;
    }
}



 a:hover{
		width:300px
}
Less嵌套写法
a{
    &:hover {
        width:300px;
    }
}


@baseFont:50px;
html{
font-size:@baseFont;
}
@border:5px+5;
div{
width:200px - 50;
height:200px * 2;
border:@border solid red;
}
img{
width:82 / @baseFont;
height:82 @baseFont;	
}

注意：
乘号(*)和除号(/)的写法
运算符中间左右有个空格隔开1px + 5
对于两个不同的单位的值之间的运算，运算结果的值取第一个值的单位
如果两个值之间只有一个值有单位，则运算结果就取该单位

```

## swiper插件（轮播图插件）

## Bootstrap框架技术（官方文档）

# vh and vw

**相对于视口的高度和宽度**，而不是父元素的（CSS百分比是相对于包含它的最近的父元素的高度和宽度）。 1vh 等于1/100的视口高度，1vw 等于1/100的视口宽度。

# [display:grid;布局](https://www.jianshu.com/p/8be74e02c897)

