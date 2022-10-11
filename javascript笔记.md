# js书写

## 1.行内式JS

```css
<input type="button"value="点我试试"onc1ick="alert('Hello World')"/>
。可以将单行或少量jS代码写在HTML标签的事件属性中（以on开头的属性），如：onclick
·注意单双引号的使用：在HTML中我们推荐使用双引号，JS中我们推荐使用单引号
。可读性差，在html中编写S大量代码时，不方便阅读；
·引号易错，引号多层嵌套匹配时，非常容易弄混：
。特殊情况下使用
```

## 2.内嵌JS

```css
<script>
alert ('Hello World~!');
</script>
可以将多行jS代码写到<script>标签中
内嵌jS是学习时常用的炳式
```



## 3.外部js

```css
<script src="my.js"></script>
哈
。利于HTML页面代码结构化，把大段S代码独立到HTML页面之外，既美观，也方便文件级别的复用
·引用外部jS文件的script标签中间不可以写代码
。适合于jS代码量比较大的情况
```

# 输入输出

| 方法             | 说明                           | 归属   |
| ---------------- | ------------------------------ | ------ |
| alert(msg)       | 浏览器弹出警示框               | 浏览器 |
| console.log(msg) | 浏览器控制台打印输出信息       | 浏览器 |
| prompt(info)     | 浏览器弹出输入框，用户可以输入 | 浏览器 |

# 关键字

## var

## let

## const

# 数据类型

## 数字型Number

现阶段我们只需要记住，在js中八进制前面加0，十六进制前面加0x

### isNaN()

用来判断一个变量是否为非数字的类型，返true或者false

### 转换为数字型

| 方式                   | 说明                         | 案例                |
| ---------------------- | ---------------------------- | ------------------- |
| parselnt(string)函数   | 将string类型转成整数数值型   | parselnt('78')      |
| parseFloat(string)函数 | 将string类型转成浮点数数值型 | parseFloat('78.21') |
| Number()强制转换函数   | 将string类型转换为数值型     | Number('12')        |
| js隐式转换(- * /)      | 利用算术运算隐式转换为数值型 | '12'-0              |



## 字符串型String

### 字符串拼接

多个字符串之间可以使用+进行拼接，其拼接方式为

字符串+任何类型=拼接之后的新字符串
拼接前会把与字符串相加的任何类型转成字符串，再拼接成一个新的字符串

我们经常会将字符串和变量来拼接，因为变量可以很方便地修改里面的值

### 拼接字符串concat

连接两个或多个数组不影响原数组
返回一个新的数组

等效于+，+更常用

### 转换为字符串

| 方式             | 说明                         | 案例                                    |
| ---------------- | ---------------------------- | --------------------------------------- |
| toString()       | 转成字符串                   | var num=1;<br>alert(num.toString());    |
| String()强制转换 | 转成字符串                   | var num =1;<br>alert(String(num));      |
| 加号拼接字符串   | 和字符串拼接的结果都是字符串 | var num=1;<br>alert(num+"我是字符串")； |

### 替换字符

```js
arr.replace('被替换的字符','替换为的字符');
```

### 字符转换为数组split('分隔符')

### 转换大写/转换小写

#### toUpperCase()/toLowerCase()

## Undefined和Null

一个声明后没有被赋值的变量会有一个默认值undefined(如果进行相连或者相加时，注意结果)

一个声明变量给null值，里面存的值为空（学习对象时，我们继续研究null

## typeof 变量名	检测数据类型

## Boolean

true和false

```css
Boolean()函数
其他类型转成布尔值
Boolean('true');
```

# js基础语法

略(和c/c++很像) 这里不做笔记

# 数组

## 利用new创建数组

```js
var 数组名=new Array();
var arr1=new Array(2);
//这个2表示数组的长度为2里面有2个空的数组元素
var arr1=new Array(2,3);
//等价于[2,3]这样写表示里面有2个数组元素是2和3
```

## 利用数组字面量创建数组

```js
//1.使用数组字面量方式创建空的数组
var 数组名=[];
//2.使用数组字面量方式创建带初始值的数组
var 数组名=['小白','小黑','大黄','瑞奇'];
```

## 数组长度

```js
array.length;
```

## 检测数组

```js
//instanceof运算符它可以用来检测是否为数组
var arr = [];
console.log(arr instanceof Array);

console.log(Array.isArray(obj));
```

## 添加数组元素

```js
var arr=[1,2,3];

arr.push(4,'red');
push()在我们数组的末尾添加一个或者多个数组元素

arr.unshift('red',4);
unshift是可以给数组追加新的元素
```

## 删除数组元素

```js
具体与上面 添加数组元素 相似
pop();
shift();
```

## 展开运算符

### 复制数组

```text
ES6 中又引入了一个简洁且可读性强的语法：展开运算符（spread operator），它能让我们方便地复制数组中的所有元素。 展开语法写出来是这样：...

我们可以用展开运算符(扩展运算符)来复制数组：

let thisArray = [true, true, undefined, false, null];
let thatArray = [...thisArray];
thatArray 等于 [true, true, undefined, false, null]。 thisArray 保持不变， thatArray 包含与 thisArray 相同的元素。
```

### 合并数组

```text
展开语法（spread）的另一个重要用途是合并数组，或者将某个数组的所有元素插入到另一个数组的任意位置。 我们也可以使用 ES5 的语法连接两个数组，但只能让它们首尾相接。 而展开语法可以让这样的操作变得极其简单：

let thisArray = ['sage', 'rosemary', 'parsley', 'thyme'];

let thatArray = ['basil', 'cilantro', ...thisArray, 'coriander'];
thatArray 会有值 ['basil', 'cilantro', 'sage', 'rosemary', 'parsley', 'thyme', 'coriander']

使用展开语法，我们就可以很方便的实现一个用传统方法会写得很复杂且冗长的操作。
```



## 数组翻转reverse

```js
arr.reverse();
```

## 数组排序sort

```js
arr.sort(function(a,b){
    return a-b;//升序排列
    //return b-a;//降序排列
});
```

## 获取数组索引

```js
indexOf();
数组中查找给定元素的第一个索引
如果存在返回索引号如果不存在，则返回-1。
lastIndexof();
在数组中的最后一个的索引，
如果存在返回索引号如果不存在，则返回-1。
```

## 数组去重unique

```js
unique(arr);
return 新数组;
```

## 数组转字符串

```js
toString();
把数组转换成字符串，逗号分隔每一项
返回一个字符串
join('分隔符');
方法用于把数组中的所有元素转换为一个字符串。
返回一个字符串


```

## map()

语法：array.map(function(currentValue,index,arr), thisValue)
其中
callback为数组中每个元素执行的函数，该函数可接受1-3个参数：

  currentvalue参数表示数组的当前元素项，必须的参数
  index参数表示的当前元素下标，可选参数
  arr参数表示当前元素所属的数组，可选参数

thisValue表示执行回调函数callback()时的this指向。可选参数。当不写时，则默认是指向window全局
map() 方法返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。

## map和forEach的区别

我们先来看看他们的相同点：

```javascript
var arr = ['a','b','c','d'];

arr.forEach(function(item,index,arr){//item表示数组中的每一项，index标识当前项的下标，arr表示当前数组
    console.log(item);
    console.log(index);
    console.log(arr);
    console.log(this);
},123);　　　　　　//这里的123参数，表示函数中的this指向，可写可不写，如果不写，则this指向window
```


```javascript
arr.map(function(item,index,arr){   //参数含义同forEach
    console.log(item);
    console.log(index);
    console.log(arr);
    console.log(this);
},123);
```

运行之后，可以看出两者参数没有任何的区别，除此之外两者之间还有一个特性，就是不能停止里面的遍历，除非程序报错。

```javascript
var arr2 = [1, 3, , 13, 2];
  var newarr = [];
  arr2.map(function (item, index) {
    if (arr2[index] == 3) {
      arr2.push(14);
      arr2.push(5);
    }
    console.log("数组循环了" + index + "次");
  });
  console.log(arr2);
```

map方法同样也不能循环的同时增加数组元素试图改变循环次数。

那他们的区别在哪呢？

返回值
  

```javascript
    var arr = [1, 3, 5, 13, 2];
      var res = arr.map(function (item, index) {
        item += 1;
        return item + 1;
      });
      console.log(res);
  var res2 = arr.forEach(function (item, index) {
    item += 1;
    return item + 1;
  });
  console.log(res2);
```
map方法会返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。
forEach方法返回值则永远是undefined。

## slice()

`slice` 方法可以从已有数组中返回指定元素。 它接受两个参数，第一个规定从何处开始选取，第二个规定从何处结束选取（不包括该元素）。 如果没有传参，则默认为从数组的开头开始到结尾结束，这是复制整个数组的简单方式。 `slice` 返回一个新数组，不会修改原始数组。

举个例子：

```js
const arr = ["Cat", "Dog", "Tiger", "Zebra"];
const newArray = arr.slice(1, 3);
newArray` 值为 `["Dog", "Tiger"]
```

------

在 `sliceArray` 函数中使用 `slice` 方法，给出 `beginSlice` 和 `endSlice` 索引，返回 `anim` 数组的一部分。 这个函数应返回一个数组。

## splice()

数组删除splice(第几个开始，要删除个数)
返回被删除项目的新数组注意，这个会影响原数组

1.splice()方法始终会返回一个数组，该数组中包含从原始数组中删除的项，如果没有删除任何项，那么将会返回一个空数组

1.第一个参数 表示起始位置

2.第二个参数 表示删除个数

3.其他参数  添加元素

## substr(start,length)

从start位置开始（索引号），length取的个数重点记住这个

## substring(start,end)值

从start位置升始，截取到end位置，end取不到基本和slice相同但是不接受负值

## map

让我们从一些简单的数组函数开始，这些函数是数组对象原型上的方法。 在本练习中，我们来了解下数组的 `map` 方法（即 `Array.prototype.map()`）。

请记住，`map`方法是迭代数组中每一项的方式之一。 在对每个元素应用回调函数后，它会创建一个新数组(不改变原来的数组)。 它这样做时没有改变原始数组。

当调用回调函数时，传入了三个参数。 第一个参数是当前正在处理的数组项。 第二个参数是当前数组项的索引值，第三个参数是在其上调用 `map` 方法的数组。

看下在 `users` 上使用 `map` 方法的例子，返回了一个新数组只包含了用户的名字。 为了简化，例子里只使用了回调函数的第一个参数。

```js
const users = [
  { name: 'John', age: 34 },
  { name: 'Amy', age: 20 },
  { name: 'camperCat', age: 10 }
];

const names = users.map(user => user.name);
console.log(names);
```

控制台将显示值 `[ 'John', 'Amy', 'camperCat' ]`。

## filter

`filter` 接收一个回调函数，将回调函数内的逻辑应用于数组的每个元素，新数组包含根据回调函数内条件返回 `true` 的元素。 换言之，它根据传递给它的函数过滤数组。 和 `map` 一样，filter 不会改变原始数组。

回调函数接收三个参数。 第一个参数是当前正在被处理的元素。 第二个参数是这个元素的索引，第三个参数是在其上调用 `filter` 方法的数组。

看下在 `users` 上使用 `filter` 方法的例子，返回了一个包含了 30 岁以下的用户新数组。 为了简化，例子里只使用了回调函数的第一个参数。

```js
const users = [
  { name: 'John', age: 34 },
  { name: 'Amy', age: 20 },
  { name: 'camperCat', age: 10 }
];

const usersUnder30 = users.filter(user => user.age < 30);
console.log(usersUnder30); 
```

控制台将显示值 `[ { name: 'Amy', age: 20 }, { name: 'camperCat', age: 10 } ]`

## reduce

`reduce()`（即`Array.prototype.reduce()`），是 JavaScript 所有数组操作中最常用的方法。 几乎可以用`reduce`方法解决所有数组处理问题。

`reduce`方法是处理数组更通用的方式，而且`filter`和`map`方法都可以当作是`reduce`的特殊实现。 `reduce`方法遍历数组中的每个项目并返回单个值（即字符串、数字、对象、数组）。 这是通过在每次迭代中调用一个回调函数来实现的。

回调函数接受四个参数。 第一个参数称为叠加器，它是上一次迭代中回调函数的返回值，第二个参数是当前正在处理的数组元素，第三个参数是该参数的索引，第四个参数是在其上调用 `reduce` 方法的数组。

除了回调函数，`reduce` 还有一个额外的参数做为叠加器的初始值。 如果没有第二个参数，会跳过第一次迭代，第二次迭代给叠加器传入数组的第一个元素。

见下面的例子，给 `users` 数组使用 `reduce` 方法，返回所有用户数组的和。 为了简化，例子仅使用了回调函数的第一个参数和第二个参数。

```js
const users = [
  { name: 'John', age: 34 },
  { name: 'Amy', age: 20 },
  { name: 'camperCat', age: 10 }
];

const sumOfAges = users.reduce((sum, user) => sum + user.age, 0);
console.log(sumOfAges);
```

这里控制台将显示值 `64`。

在另一个例子里，查看如何返回一个包含用户名称做为属性，其年龄做为值的对象。

```js
const users = [
  { name: 'John', age: 34 },
  { name: 'Amy', age: 20 },
  { name: 'camperCat', age: 10 }
];

const usersObj = users.reduce((obj, user) => {
  obj[user.name] = user.age;
  return obj;
}, {});
console.log(usersObj);
```

控制台将显示值 `{ John: 34, Amy: 20, camperCat: 10 }`。

------

`watchList` 是包含一些电影信息的对象。 使用 `reduce` 查找由 `Christopher Nolan` 导演的电影的 IMDB 评级平均值。 回想一下之前的挑战，如何 `filter` 数据，以及使用 `map` 来获取你想要的数据。 您可能需要创建其他变量，并从 `getRating` 函数返回平均评分。 请注意，评级在对象中是字符串，需要将其转换为数字再用于数学运算。


# 函数

## 声明

```js
function xx(){
    alert(1);
}


var xx=function(){
    alert(1);
}
```

## 调用

```js
xx();
```

## 传参

```js
function xx(a){
    alert(a);
}
```

## 返回值

```js
return 值;
```

函数没有return	返回undefined

## arguments伪数组的使用

当我们不确定有多少个参数传递的时候，可以用arguments来获取。在JavaScript中，arguments实际上是当前函数的一个内置对象。所有函数都内置了一个arguments对象，arguments对象中存储了传递的所有实参。

# 对象

## 创建对象

### 利用对象字面量创建对象

```js
var obj={};
var obj={
    name:'王珂',
    sex:'女',
    sayHi:funtion(){
    	alert('hi!');
	}
}
```

### 利用new Object创建对象

```js
var obj=new Object();
obj.name:'王珂';
obj.sex:'';
obj.sayHi=funtion(){
    	alert('hi!');
	}
```



### 构造函数创建对象

```js
function Star(name,age,sex){
this.name= name;
this.age =age;
this.sex=sex;
}
var cxk=new Star('蔡徐坤'，18，'女');
```

## 删除对象

```text
在之前的挑战中，我们已经试过添加和修改对象中的键值对。 现在我们来看看如何从一个对象中移除一个键值对。

我们再来回顾一下上一个挑战中的 foods 对象。 如果我们想移除 apples 属性，可以像这样使用 delete 关键字：

delete foods.apples;
```



## 遍历对象

```js
for (var k in obj){
console.1og(k);//k变量输出
得到的是属性名
console.1og(obj[k]);//obj[k]得到是属性值
}
```

## 内置对象

## 使用 Object.keys() 生成由对象的所有属性组成的数组

```text
我们可以给 Object.keys() 方法传入一个对象作为参数，来生成包含对象所有键的数组。 这会返回一个由对象中所有属性（字符串）组成的数组。 需要注意的是，数组中元素的顺序是不确定的。
```

```js
let users = {
  Alan: {
    age: 27,
    online: false
  },
  Jeff: {
    age: 32,
    online: true
  },
  Sarah: {
    age: 48,
    online: false
  },
  Ryan: {
    age: 19,
    online: true
  }
};

function getArrayOfUsers(obj) {
  // 只修改这一行下面的代码
  return   Object.keys(obj);
  // 只修改这一行上面的代码
}
console.log(getArrayOfUsers(users));
// 测试完成
// 打印输出
[ 'Alan', 'Jeff', 'Sarah', 'Ryan' ]
```



## Math对象

```js
Math.PI
//圆周率
Math.floor (
//向下取整
Math.ceil()
//向上取整
Math.round()
//四舍五入版就近取整
注意-3.5		结果是-3
Math.abs()
//绝对值
Math.max()/Math.min()//求最大和最小值
Math.random()
返回一个随机的小数0<=×<1
```

## Date日期对象

```js
var date = new Date();
console.log(date);
数字型
2019,10,01
或者是字符串型
'2019-10-1 8：8：8'
var datel= new Date(2019,10,1);
conso1e.1og(date1);/返回的是11月不是10月
var date2= new Date('2019-10-1 8:8:8');I
console.log(date2);
```

### 日期格式化

| 方法名        | 说明                       | 代码               |
| ------------- | -------------------------- | ------------------ |
| getFullYear() | 获取当年                   | dObj.getFullYear() |
| getMonth()    | 获取当月(0-11)             | dObj.getMonth()    |
| getDate()     | 获取当天日期               | dObj.getDate()     |
| getDay()      | 获取星期几（周日0到周六6） | dObj.getDay()      |
| getHours()    | 获取当前小时               | dObj.getHours()    |
| getMinutes()  | 获取当前分钟               | dObj.getMinutes()  |
| getSeconds()  | 获取当前秒钟               | dObj.getSeconds()  |

### Date总的毫秒数（时间戳）

```js
Date.now();返回的是当前时间总的毫秒数
+new Date();返回的是当前时间总的毫秒数
+new Date(time);返回的是用户输入时间总的毫秒数
```

# 简单数据类型传参传的是值

string ，number，boolean，undefined，null

# 复杂数据类型传参传的是地址

通过 new 关键字创建的对象（系统对象、自定义对象），如 Object、Array、Date等；
