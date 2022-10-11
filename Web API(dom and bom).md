# DOM

## console.dir

打印我们返回的元素对象更好的查看里面的属性和方法

## 获取元素

### getElementByld获取元素

```html
<body>
    <div id="time">2022-4-30</div>
    <script>
        var timer=document.getElement('time');
        conso1e.log(timer);
		console.log(typeof timer);
		//conso1e.dir打印我们返回的元素对象更好的查看里面的属			性和方法
		console.dir(timer);
    </script>
</body>
```

### getElementByTagName获取元素

```html
<body>
    <li>1</li>
    <li>1</li>
    <li>1</li>
    <li>1</li>
    <li>1</li>
    <script>
        var lis=document.getElementByTagName('li');
		for(var i=0;i<lis.length;i++){
            console.log(lis[i]);
        }
    </script>
</body>
```

### getElementByClassName获取元素

```html
<body>
   <div id="box" class="box" >cxk</div>
    <script>
        var box=document.getElementByClassName('box');
    </script>
</body>
```

### querySelector获取元素

```html
<body>
   <div id="box" class="box" >cxk</div>
    <script>
        var box=document.querySelector('#box');
    </script>
</body>
```

### querySelectorAll获取元素

### 获取body和html元素

```html
<script>
    //获取body元素
	var bodyEle= document.body;
	console.log(bodyEle);
	console.dir(bodyEle);
	//获取htm1元素
	var htmlEle= document.documentElement;
	console.log(htmlEle);
</script>
```

## 事件

### 注册事件

```html
<script>
var btns = document.queryselectorAll('button');
//1.传统方式注册事件
btns[0].onclick= function(){ 
alert('hi');
btns[0].onclick =function(){
alert('hao a u');
//2.事件侦听注册事件addEventListener里面的事件类型是字符串必定加引号而且不带on
btns[1].addEventListener('click',function(){
a1ert(22);
})
</script>
```

### 删除事件

```html
<script>
    //1.传统方式删除事件
	btns[0].onclick= null;
    //2.事件侦听删除事件
	Element.removeEventListener('click',fn)
</script>
```

### 事件对象

```html
<script>
	div.addEventListener('click',function(e){
		console.log(e);
    })

//1.event就是一个事件对象写到我们侦听函数的小括号里面当形参来看
//2.事件对象只有有了事件才会存在，它是系统给我们自动创建的，不需要我们传递参数
//3,事件对象是我们事件的一系列相关数据的集合跟事件相关的比如鼠标点击里面就包含了鼠标的相关信息，鼠标坐标啊，如果是键盘事件里面就包含的键盘事件的信息比如判断用户按下了那个键
//4.这个事件对象我们可以自己命名比如event、evt、e
//5,事件对象也有兼容性问题ie678通过window.event
</script>
```

### 事件对象属性方法

| 事件对象属性方法    | 说明                                               |
| ------------------- | -------------------------------------------------- |
| e.target            | 返回触发事件的对象                                 |
| e.type              | 返回事件的类型比如click mouseover不带on            |
| e.preventDefault()  | 该方法阻止默认事件（默认行为）标准比如不让链接跳转 |
| e.stopPropagation() | 阻止冒泡标准                                       |



### 鼠标事件



| 鼠标事件      | 触发条件             |
| ------------- | -------------------- |
| onclick       | 鼠标点击左键触发     |
| onmouseover   | 鼠标经过触发         |
| onmouseout    | 鼠标离开触发         |
| onfocus       | 获得鼠标焦点触发     |
| onblur        | 失去鼠标焦点触发     |
| onmousemove   | 鼠标移动触发         |
| onmouseup     | 鼠标弹起触发         |
| onmousedown   | 鼠标按下触发         |
| oncontextmenu | 鼠标右键菜单         |
| onselectstart | 鼠标选中（例如文字） |



### 鼠标坐标

```html
//鼠标事件对象MouseEvent
document.addEventListener('click',function(e){
//1.c1ient鼠标在可视区的x和y坐标
console.log(e.clientx);
console.log(e.clientY);
})
```

| 鼠标事件对象 | 说明                                  |
| ------------ | ------------------------------------- |
| e.clientX    | 返回鼠标相对于浏览器窗口可视区的X坐标 |
| e.clientY    | 返回鼠标相对于浏览器窗口可视区的Y坐标 |
| e.pageX      | 返回鼠标相对于文档页面的X坐标E9+支持  |
| e.pageY      | 返回鼠标相对于文档页面的Y坐标IE9+支持 |
| e.screenX    | 返回鼠标相对于电脑屏幕的X坐标         |
| e.screenY    | 返回鼠标相对于电脑屏幕的Y坐标         |

### 键盘事件

| 键盘事件   | 触发条件                                                     |
| ---------- | ------------------------------------------------------------ |
| onkeyup    | 某个键盘按键被松开时触发                                     |
| onkeydown  | 某个键盘按键被按下时触发                                     |
| onkeypress | 某个键盘按键被按下时触发<br/>但是它不识别功能键比如ctrl shift箭头等 |

```html
<script>
	e.KeyCode
键盘事件对象中的keyCode属性可以得到相应键的ASCII码值
我们的keyup和keydown事件不区分字母大小写a和A得到的都是	65
我们的keypress事件区分字母大小写a 97和A 得到的是65
</script>
```





## [操作元素属性](https://blog.csdn.net/zyb18507175502/article/details/123672551)

### element.innerText和element.innerHTML

element.innerText
从起始位置到终止位置的内容，但它去除html标签，同时空格和换行也会去掉
element.innerHTML
起始位置到终止位置的全部内容，包括html标签，同时保留空格和换行

1. element.style 行内样式操作
2. element.className 类名样式操作

### 自定义属性的操作

#### 1.获取属性值

element.属性 获取属性值。
element.getAttribute(‘属性’);
区别：

element.属性 获取内置属性值（元素本身自带的属性）
element.getAttribute(‘属性’); 主要获得自定义的属性 （标准） 我们程序员自定义的属性

#### 2.设置属性值

element.属性 = ‘值’ 设置内置属性值。
element.setAttribute(‘属性’, ‘值’);
区别：

element.属性 设置内置属性值
element.setAttribute(‘属性’); 主要设置自定义的属性 （标准)
注意：div.setAttribute(‘class’, ‘footer’); // class 特殊 这里面写的就是class 不是className

#### 3.removeAttribute移除属性

删除头部元素的 style 属性:

document.getElementsByTagName("h1")[0].removeAttribute("style");

删除属性前:

Hello World

删除属性后:

Hello World

## 节点操作

### 父节点

```html
parentNode
```

### 子节点

```html
childNodes
```

### 兄弟节点

```html
nextSibling
previousSibling
```

### 创建和添加节点

```html
<script>
	//1.创建节点元素节点
	var li = document.createElement('li');
	//2.添加节点node.appendChild(child)node父级child是子		级	后面追加元素类似于数组中的push
	var ul= document.queryselector('ul');
	ul.appendChild(li);
</script>
```

### 删除节点

```html
removeChild
```

### 克隆节点

```html
cloneNode
```

### 三种创建元素方式区别

```html
<script>
	//1.document.write()创建元素如果页面文档流加载完毕，再调	用这句话会导致页面重绘
	var btn = document.querySelector('button');
	btn.onclick= function(){
        document.write('<div>123</div>');
    }
    
	//2.innerHTML创建元素
    
    
	//3,document.createElement()创建元素
</script>
```

# BOM

## 页面加载

```html
<script>
	window.onload =function(){}
	或者
	window.addEventListener("load",function(){});
	window.onload是窗口页面加载事件，当文档内容完全加载完成会		触发该事件（包括图像、脚本文件、CSS
	文件等)，就调用的处理函数。
	注意：
1.有了window.onload就可以把jS代码写到页面元素的上方，因为onload是等页面内容全部加载完毕，
再去执行处理函数。
2.window.onload传统注册事件方式只能写一次，如果有多个，会以最后一个window.onload为准。
3.如果使用addEventListener则没有限制



document.addEventListener ('DOMContentLoaded',function(){})
DOMContentLoaded事件触发时，仅当DOM加载完成，不包括样式表，图片，flash等等。
ie9以上才支持
如果页面的图片很多的话，从用户访问到onload触发可能需要较长的时间，交互效果就不能实现，必然影响用
户的体验，此时用DOMContentLoaded事件比较合适
</script>
```

## 调整窗口大小事件

```html
<script>
	window.onresize =function(){}

window.addEventListener ("resize",function (){}
window.onresize是调整窗口大小加载事件，当触发时就调用的处理函数。
注意：
1.只要窗口大小发生像素变化，就会触发这个事件。
2.我们经常利用这个事件完成响应式布局。window.innerWidth当前屏幕的宽度
</script>
```

## 定时器

### setTimeout()

## 

```js
window.setTimeout(调用函数，[延迟的毫秒数])；
setTimeout0方法用于设置一个定时器，该定时器在定时器到期后执行调用函数。
注意：
1.window可以省略。
2.这个调用函数可以直接写函数，或者写函数名或者采取字符串函数名三种形式。第三种不推荐
3.延迟的毫秒数省略默认是0，如果写必须是毫秒。
```



### clearTimeout()

```js
window.clearTimeout (timeoutID)
clearTimeout()方法取消了先前通过调用setTimeout()建立的定时器。
注意：
1.window可以省略。
2.里面的参数就是定时器的标识符。
```



### setInterval()

```js
window.setInterval(回调函数，[间隔的毫秒数]);
setlnterval()方法重复调用一个函数，每隔这个时间，就去调用一次回调函数。
注意：
1.window可以省略。
2.这个调用函数可以直接写函数，或者写函数名或者采取字符串"函数名0'三种形式。
3.间隔的毫秒数省略默认是0，如果写，必须是毫秒，表示每隔多少毫秒就自动调用这个函数。
4.因为定时器可能有很多，所以我们经常给定时器赋值一个标识符。
```



### clearsetInterval()

```js
window.clearInterval(intervalID);
clearInterval()方法取消了先前通过调用setInterval()建立的定时器。
注意：
1.window可以省略。
2.里面的参数就是定时器的标识符。
```

### 同步和异步

```text
同步任务
同步任务都在主线程上执行，形成一个执行栈。
异步任务
JS的异步是通过回调函数实现的。
一般而言，异步任务有以下三种类型
1、普通事件，如click、resize等
2、资源加载，如load、error等
3、定时器，包括setInterval、setTimeout等
```

## location对象

### location对象属性

```text
protocol			
通信协议常用的http,ftp,maito等

host
主机（域名）
www.itheima.com

port
端口号可选，省略时使用方案的默认端口如http的默认端口为80

path
路径由零或多个符号隔开的字符串，一般用来表示主机上的一个目录或文件地址

query
参数以键值对的形式，通过&符号分隔开来

fragment
片段#后面内容常见于链接锚点
```

```text
location对象属性
返回值


location.href
获取或者设置整个URL

location.host
返回主机（域名）
www.itheima.com
location.port
返回端口号如果未写返回空字符串

location.pathname
返回路径

location.search
返回参数

location.hash
返回片段#后面内容常见于链接锚点

```

### location对像方法

```text

location.assign()
跟href一样，可以跳转页面（也称为重定向页面）

location.replace()
替换当前页面，因为不记录历史，所以不能后退页面

location.reload()
重新加载页面，相当于刷新按钮或者f5如果参数为true强制刷新
ctrl+f5
```

### navigator对象(了解)

### history对象方法

```text
back()
可以后退功能
forward()
前进功能
go(参数)
前进后退功能参数如果是1前进1个页面如果是-1后退1个页面
```

