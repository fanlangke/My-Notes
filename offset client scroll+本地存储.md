# offset client scroll

## offset

### offset概述

offset翻译过来就是偏移量，我们使用offset系列相关属性可以动态的得到该元素的位置（偏移）、大小等。

1.获得元素距离带有定位父元素的位置
2.获得元素自身的大小（宽度高度)
3.·注意：返回的数值都不带单位

```html
offset系列属性
element.offsetParent
返回作为该元素带有定位的父级元素如果父级都没有定位则返回body
element.offsetTop
返回元素相对带有定位父元素上方的偏移
element.offsetLeft
返回元素相对带有定位父元素左边框的偏移
element.offsetWidth
返回自身包括padding、边框、内容区的宽度，返回数值不带单位
element.offsetHeight
返回自身包括padding、边框、内容区的高度，返回数值不带单位
```

## client

```text
client系列属性

element.clientTop
返回元素上边框的大小
element.clientLeft
返回元素左边框的大小
element.clientWidth
返回自身包括padding、内容区的宽度，不含边框，返回数值不带单位
element.clientHeight
返回自身包括padding、内容区的高度，不含边框，返回数值不带单位
```

## scroll

```text
元素scro川系列属性
scroll翻译过来就是滚动的，我们使用scroll系列的相关属性可以动态的得到该元素的大小、滚动距离等。
scroll系列属性

element.scrollTop
返回被卷去的上侧距离，返回数值不带单位

element.scrollLeft
返回被卷去的左侧距离。返回数值不带单位

element.scrollWidth
返回自身实际的宽度，不含边框，返回数值不带单位

element.scrollHeight
返回自身实际的高度，不含边框，返回数值不带单位
```

## window.sessionStorage

```text
1、生命周期为关闭浏览器窗口
2、在同一个窗口页面下数据可以共享
3.以键值对的形式存储使用
存储数据：
sessionStorage.setItem(key,value)
获取数据：
sessionStorage.getItem(key)
删除数据：
sessionStorage.removeItem(key)
删除所有数据：
sessionStorage.clear()
```

## window.localStorage

```css
1、生命周期永久生效，除非手动删除否则关闭页面也会存在
2、可以多窗口（页面）共享（同一浏览器可以共享）】
3.以键值对的形式存储使用
存储数据：
localStorage.setItem(key,value)
获取数据：
localStorage.getItem(key)
删除数据：
localStorage.removeItem(key)
删除所有数据：
localStorage.clear()
```

