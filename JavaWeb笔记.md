[视频](https://www.bilibili.com/video/BV1Qf4y1T7Hx)
# 架构模式

## CS:客户端服务器架构模式

优点：充分利用客户端机器的资源，减轻服务器的负荷(一部分安全要求不高的计算任务存储任务放在客户端执行，不需要把所有的计算和
存储都在服务器端执行，从而能够减轻服务器的压力，也能够减轻网络负荷)

缺点：需要安装；升级维护成本较高

## BS:浏览器服务器架构模式

优点：客户端不需要安装；维护成本较低

缺点：所有的计算和存储任务都是放在服务器端的，服务器的负荷较重；在服务端计算完成之后把结果再传输给客户端，因此客户端和服务器端会进行非常频繁的数据通信，从而网络负荷较重

# http协议

```text
HTTP协议特点：
1.基于TCP协议：面向连接，安全
2.基于请求-响应模型的：一次请求对应一次响应
3.HTTP协议是无状态的协议：对于事务处理没有记忆能力。每次请求-响应都是独立的。
缺点：多次请求间不能共享数据。
优点：速度快
```
请求格式
```
请求数据分为3部分：
1.请求行：请求数据的第一行。其中GET表示请求方式，/
表示请求资源路径，HTTP/1.1表示协议版本
2.请求头：第二行开始，格式为key:value形式。
3.请求体：POST请求的最后一部分，存放请求参数
```
响应格式
```
响应数据分为3部分：
1.响应行：响应数据的第一行。其中HTTP/1.1表示协议版
本，200表示响应状态码，OK表示状态码描述
2.响应头：第二行开始，格式为key:value形式
3.响应体：最后一部分。存放响应数据
```


# tomcat
[点我跳转tomcat](https://blog.csdn.net/fanlangke/article/details/127272143)
# Servlet
Servlet是Java提供的一门动态web资源开发技术
## 快速入门
[视频](https://www.bilibili.com/video/BV1Qf4y1T7Hx?p=94)
1.创建web项目，导入Servlet依赖坐标
```xml
    <dependency>
      <groupId>javax.servlet</groupId>
      <artifactId>javax.servlet-api</artifactId>
      <version>3.1.0</version>
      <scope>provided</scope>
```
必须加      \<scope>provided\</scope>
因为运行时存在Servlet和tomcat会有相同jar包发生冲突

2.创建：定义一个类，实现Servlet接口，并重写接口中所有方法，并在service方法中输入一句话

3.配置：在类上使用@WebServlet注解，配置该Servlet的访问路径

4.访问：启动Tomcat,浏览器输入URL访问该Servlet
```java
import javax.servlet.*;
import javax.servlet.annotation.WebServlet;
import java.io.IOException;



@WebServlet("/demo1")
public class ServletDemo1 implements Servlet {

    @Override
    public void service(ServletRequest req,ServletResponse res) throws ServletException,IOException{
        System.out.println("11111");
    }

    @Override
    public void init(ServletConfig servletConfig) throws ServletException {

    }

    @Override
    public ServletConfig getServletConfig() {
        return null;
    }

    @Override
    public String getServletInfo() {
        return null;
    }

    @Override
    public void destroy() {

    }

}

```
5.当你访问URL时IDEA的控制台会输出11111
## Servlet执行流程
1.Servlet由谁创建？Servlet方法由谁调用？
Servlet由web服务器创建，Servlet方法由web服务器调用。

2.服务器怎么知道Servlet中一定有service方法？
因为我们自定义的Servlet,必须实现Servlet接口并复写其
方法，而Servlet接口中有service方法
## Servlet生命周期
对象的生命周期指一个对象从被创建到被销毁的整个过程

Servlet运行在Servlet容器(web服务器)中，其生命周期由容器来管理，分为4个阶段：
 ```text
1.加载和实例化：默认情况下，当Servlet第一次被访问时，由容器创建Servlet对象
2.初始化：在Servlet实例化之后，容器将调用Servlet的init()方法初始化这个对象，完成一些如
加载配置文件、创建连接等初始化的工作。该方法只调用一次
3.请求处理：每次请求Servlet时，Servlet容器都会调用Servlet的service()方法对请求进行处理。
4.服务终止：当需要释放内存或者容器关闭时，容器就会调用Servlet实例的destroy()方法完成
资源的释放。在destroy()方法调用之后，容器会释放这个Servlet实例，该实例随后会被Java的
垃圾收集器所回收
```
```text
@WebServlet(urlPatterns ="/demo",loadOnStartup=1)
负整数：第一次被访问时创建Servlet对象
0或正整数：服务器启动时创建Servlety对象，数字越小优先级越高
```
## Servlet方法介绍
```java
初始化方法，在Servlet被创建时执行，只执行一次
void init(ServletConfig config)

提供服务方法，每次Servlet被访问，都会调用该方法
void service(ServletRequest req,ServletResponse res)

销毁方法，当Servlet被销毁时。调用该方法。在内存释放或服务器关闭时销毁Servlet
void destroy()

获取ServletConfig对象
ServletConfig getServletConfig()

获取Servlet信息
String getServletlnfo()
```
## Servlet体系结构
Servlet->Servlet体系根接口
GenericServlet->Servlet抽象实现类
HttpServlet->对HTTP协议封装的Servlet实现类

我们将来开发B/S架构的web项目，都是针对HTTP协议
,所以我们自定义Servlet,会继承HttpServlet
```java

import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;



@WebServlet("/demo1")
public class ServletDemo1 extends HttpServlet {

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) {
        System.out.println("get...");
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp)  {
        System.out.println("Post...");
    }
}

```
## Servlet urlPattern配置
1.一个Servlet,可以配置多个urlPattern
```java
@WebServlet(urlPatterns = {"/demo1","/demo2"})

```
```java
精确匹配：
配置路径：@WebServlet("/user/select")

目录匹配：
配置路径：@WebServlet("/user/*")

扩展名匹配：
配置路径：@WebServlet("*.do")

任意匹配：
配置路径：
@WebServlet("/")
@WebServlet("/*")
```
## XML配置方式编写Servlet
Servlet从3.0版本后开始支持使用注解配置，3.0版本前只支持XML配置文件的配置方式
```xml
<servlet>
	<servlet-name>demo5</servlet-name>
	<servlet-class>com.itheima.web.servlet.ServletDemo5</servlet-class>
</servlet>
<servlet-mapping>
	<servlet-name>demo5</servlet-name>
	<url-pattern>/demo5</url-pattern>
</servlet-mapping>
```
# Request(请求)&Response(响应)
```text
Request:获取请求数据
Response:设置响应数据
```
## request继承体系
```text
ServletRequest
Java提供的请求对象根接口

HttpServletRequest
Java提供的对Http协议封装的请求对象接口

RequestFacade
Tomcat定义的实现类

Tomcat需要解析请求数据，封装为request对象，
并且创建request>对象传递到service方法中
```
## <div id="Catalog">Request获取请求数据<div>
```java
请求数据分为3部分：
1.请求行：
GET /request-demo/req1?username=zhangsan HTTP/1.1
String getMethod():获取请求方式：GET
String getContextPath():获取虚拟目录（项目访问路径）：request-demo
String Buffer getRequestURL():获取URL(统一资源定位符)：http:/localhost:8080/request-demo/req1
String getRequestURI():获取URI(统一资源标识符)：/request-demo/req1
String getQueryString():获取请求参数(GET方式)：username:=zhangsan&password=123

2.请求头：
User-Agent:Mozilla/5.0 Chrome/91.0.4472.106
String getHeader(String name):根据请求头名称，获取值

3.请求体：
username=superbaby&password=123
ServletInputStream getlnputStream():获取字节输入流
BufferedReader getReader():获取字符输入流
```
##  Request通用方式获取请求参数
```java
//获取请求方式
String method = this.getMethod();
//判断
if ("GET".equals(method)){
	//GET方式获取请求参数
	params=this.getQuerystring();
}
else if ("POST".equals(method)){
	//P0ST方式炎取请求参数
	BufferedReader reader this.getReader()
	params=reader.readLine();
}

Map<String,String[]> getParameterMap():获取所有参数Map集合
String[] getParameterValues(String name):根据名称获取参数值（数组）
String getParameter(String name):根据名称获取参数值（单个值）
```
## Request请求参数中文乱码处理
```java
请求参数如果存在中文数据，则会乱码
解决方案：

POST:设置输入流的编码
req.setCharacterEncoding("UTF-8");

通用方式(GET/POST):先编码，再解码
new String(username.getBytes("ISO-8859-1"),"UTF-8");

URL编码
1.将字符串按照编码方式转为二进制
2.每个字节转为2个16进制数并在前边加上%
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/4c24206e1bca4d21b3cee7163ab6166d.png)
> Tomcat8.0之后，已将GET请求乱码问题解决，设置默认的解码方式为UTF-8

```java
URL编码实现方式：
编码：
URLEncoder.encode(str,"utf-8");
解码：
URLDecoder.decode(s,"ISO-8859-1");
```
## 请求转发
请求转发(forward)：一种在服务器内部的资源跳转方式
```java
实现方式：
req.getRequestDispatcher("资源B路径").forward(req,resp);

请求转发资源间共享数据：使用Request对象
void setAttribute(String name,Object o):存储数据到request域中
Object getAttribute(String name):根据key,获取值
void removeAttribute(String name):根据key,删除该键值对
```
```
请求转发特点：
浏览器地址栏路径不发生变化
只能转发到当前服务器的内部资源
一次请求，可以在转发的资源间使用request共享数据
```
## Response设置响应数据功能介绍
```java
响应数据分为3部分：
1.响应行：
HTTP/1.12000K
void setStatus(int sc)：设置响应状态码

2.响应头：
Content-Type:text/html
void setHeader(String name,String value):设置响应头键值对

3.响应体：
<html><head>head><body></body></html>
PrintWriter getWriter():获取字符输出流
ServletOutputStream getOutputStream():获取字节输出流
```
## Response完成重定向
重定向(Redirect):一种资源跳转方式
```java
我处理不了找别人去处理：状态码302
那个人的位置是xxx:响应头location:xxx

实现方式：
资源B
resp.setStatus(302);
resp.setHeader("location'",“资源B的路径")；
resp.sendRedirect("资源B的路径")；

重定向特点：
浏览器地址栏路径发生变化
可以重定向到任意位置的资源（服务器内部、外部均可）
两次请求，不能在多个资源使用request共享数据
```
[虚拟目录](#Catalog)
```java
路径问题

明确路径谁使用？
浏览器使用：需要加虚拟目录（项目访问路径）
服务瑞使用：不需要加虚拟目录

练习：
<a href='路径' >	加虚拟目录
<form action:='路径'>	加虚拟目录
req.getRequestDispatcher("路径"）	不加虚拟目录
resp.sendRedirect("路径")	加虚拟目录
```
## Response响应字符数据
```java
使用：
1.通过Response对象获取字符输出流
PrintWriter writer=resp.getWriter();

2.写数据
writer.write("aaa");

●注意：
该流不需要关闭，随着响应结束，response对象销毁，由服务器关闭
中文数据乱码：原因通过Response获取的字符输出流默认编码：IS0-8859-1
resp.setContentType("text/html;charset=utf-8");
```
## Response响应字节数据
```java
使用：
1.通过Response对象获取字符输出流
ServletOutputStream outputStream resp.getOutputStream();
2.写数据
outputStream.write(字节数据);

。IOUtils.工具类使用
1.导入坐标
<dependency>
	<groupld>commons-io</groupld>
	<artifactld>commons-io</artifactld>
	<version>2.6</version>
</dependency>
2.使用
1 DUtils.copy(输入流，输出流);
```
# JSP (该技术已过时 但仍需了解)
概念：Java Server Pages,Java服务端页面
一种动态的网页技术，其中既可以定义HTML、JS、CSS等静态内容，还可以定义Jva代码的动态内容

JSP = HTML + Java
## JSP快速入门
1.导入JSP坐标
```xml
<dependency>
	<groupld>javax.servlet.jsp</groupld>
	<artifactld>jsp-api</artifactld>
	<version>2.2</version>
	<scope>provided</scope>
</dependency>
```
2.创建JSP文件

3.编写HTML标签和Java代码
```html
<body>
	<h1>hello jsp~</h1>
	<% System.out.printf("jsp hello~");%>
</body>
```
## JSP原理
概念：Java Server Pages,Java服务端页面
JSP=HTML+Java,用于简化开发的
JSP本质上就是一个Servlet
## JSP脚本
JSP脚本用于在JSP页面内定义Java代码
●JSP脚本分类：
1.<%...%>:内容会直接放到jspService()方法之中
2.<%=...%>:内容会放到out.print()中，作为out.print()的参数
3.<%!...%>:内容会放到jspService()方法之外，被类直接包含
## JSP缺点
由于SP页面内，既可以定义HTML标签，又可以定义Jva代码，造成了以下问题：
```text
1.书写麻烦：特别是复杂的页面
2.阅读麻烦
3.复杂度高：运行需要依赖于各种环境，JRE,JSP容器，JavaEE.…
4.占内存和磁盘：JSP会自动生成.java和.class文件占磁盘，运行的是.class文件占内存
5.调试困难：出错后，需要找到自动生成的.java文件进行调试
6.不利于团队协作：前端人员不会Java,后端人员不精HTML
```
## EL表达式
Expression Language表达式语言，用于简化JSP页面内的)ava代码
主要功能：获取数据
语法：${expression}
$(brands)：获取域中存储的key为brands的数据
JavaWeb中的四大域对象：
```
	1.page:当前页面有效
	2.request:当前请求有效
	3.session:当前会话有效
	4.application:当前应用有效
```
表达式获取数据，会依次从这4个域中寻找，直到找到为止
## JSTL标签
JSTL快速入门
1.导入坐标
```xml
<dependency>
<groupld>jstl</groupld>
<artifactld>jstl</artifactld>
<version>1.2</version>
</dependency>
<dependency>
<groupld>taglibs</groupld>
<artifactld>standard</artifactld>
<version>1.1.2</version>
</dependency>
```
2.在SP页面上引入JSTL标签库
```jsp
<%@ taglib prefix="c"uri="http://java.sun.com/jsp/jstl/core"%>
```
3.使用
><c:if test="true">
>if判断
>
> <c:forEach>
> 相当于for循环
items:被遍历的容器
var:遍历产生的临时变是
varStatus:遍历状态对象
# Cookie基本使用
Cookie:客户端会话技术，将数据保存到客户端，以后每次请求都携带Cookie数据进行访问
```java
Cookie基本使用
1.创建Cookie对象，设置数据
Cookie cookie new Cookie("key","value");
2.发送Cookie到客户端：使用response对象
response.addCookie(cookie);
3.获取客户端携带的所有Cookie,使用request对象
Cookie[] cookies=request.getCookies();
4.遍历数组，获取每一个Cookie对象：for
5.使用Cookie对象方法获取数据
cookie.getName();
cookie.getValue();
```
## Cookie原理
Cookie的实现是基于HTTP协议的
响应头：set-cookie
请求头：cookie
## Cookie使用细节
```java
Cookie存活时间
默认情况下，Cookie存储在浏览器内存中，当浏览器关闭，内存释放，则Cookie被销毁
setMaxAge(int seconds):设置Cookie存活时间
1.正数：将Cookie写入浏览器所在电脑的硬盘，持久化存储。到时间自动删除
2.负数：默认值，Cookie:在当前浏览器内存中，当浏览器关闭，则Cookie被销毁
3.零：删除对应Cookie

Cookie不能直接存储中文
如需要存储，则需要进行转码：URL编码
```
# Session原理
Session,是基于Cookie实现的
![在这里插入图片描述](https://img-blog.csdnimg.cn/351b62c8347d4d9480e7a2edd4082280.png)
## Session使用细节
```java
Session钝化、活化：
服务器重启后，Session中的数据是否还在？
钝化：在服务器正常关闭后，Tomcat:会自动将Session数据写入硬盘的文件中
活化：再次启动服务器后，从文件中加载数据到Session中

Seesion销毁：

默认情况下，无操作，30分钟自动销毁
--web.xml--
<session-config>
	<session-timeout>30</session-timeout>
</session-config>
--	--

调用Session对象的invalidate(O方法
```
# Filter
概念：Filter表示过滤器，是JavaWeb三大组件(Servlet、Filter、Listener)之一。
过滤器可以把对资源的请求拦截下来，从而实现一些特殊的功能。
过滤器一般完成一些通用的操作，比如：权限控制、统一编码处理、敏感字符处理等等…
## Filter快速入门
```java
1.定义类，实现Filter接口，并重写其所有方法
	public class FilterDemo implements Filter{
	public void init(FilterConfig filterConfig)
	public void doFilter(ServletRequest request...)
	public void destroy()
}
2.配置Filter拦截资源的路径：在类上定义@WebFilter注解
	@WebFilter("/*")
	public cLass FilterDemo implements Filter
3.在doFilter方法中输出一句话，并放行
	public void doFilter(ServletRequest request,Ser...){
		System.out.println("filter被执行了.，，");
		//放行
		chain.doFilter(request,response);
		System.out.println("filter被执行后逻辑");
}
```
## Filter执行流程
1.放行后访问对应资源，资源访问完成后，还会回到Filter中吗？会
2.如果回到Filter中，是重头执行还是执行放行后的逻辑呢？放行后逻辑
## Filter拦截路径配置
Filter可以根据需求，配置不同的拦截资源路径
@WebFilter("/\*")
public class FilterDemo
```text
拦截具体的资源：/index.jsp:只有访问index,jsp时才会被拦截。
目录拦截：user/*:访问/user下的所有资源，都会被拦截
后缀名拦截：*jsp:访问后缀名为jsp的资源，都会被拦截
拦截所有：*：访问所有资源，都会被拦截
```
## 过滤器链
一个Web应用，可以配置多个过滤器，
这多个过滤器称为过滤器链
```xml
通过 web.xml 配置的 Filter 过滤器，执行顺序由 <filter-mapping> 标签的配置顺序决定。
<filter-mapping> 靠前，则 Filter 先执行，靠后则后执行。
通过修改 <filter-mapping> 的顺序便可以修改 Filter 的执行顺序。

通过 @WebFilter 注解配置的 Filter 过滤器，无法进行排序，若需要对 Filter 过滤器进行排序，建议使用web.xml 进行配置。
```
# Listener
```text
概念：Listener表示监听器，是JavaWeb三大组件(Servlet、Filter、Listener)之一。
监听器可以监听就是在application,session,request三个对象创建、销毁或者往其中添加修改删除
属性时自动执行代码的功能组件
Listener2分类：JavaWeb中提供了8个监听器
```
|监听器分类  | 监听器名称 |作用 |
| --| -- | --|
| ServletContext监听 |ServletContextListener  | 用于对ServletContext对象进行监听（创建、销毁） |  
|  | ServletContextAttributeListener | 对ServletContext对象中属性的监听（增删改属性） |
|Session监听  |HttpSessionListener  |对Session对象的整体状态的监听（创建、销毁）  |  
|  |HttpSessionAttributeListener  |对Session对象中的属性监听（增删改属性）  |  
|  | HttpSessionBindingListener | 监听对象于Session的绑定和解除 |  
|  | HttpSessionActivationListener |对Session数据的钝化和活化的监听  |  
 |Request监听  |ServletRequestAttributeListener  |  对Request对象中属性的监听（增删改属性）|
|  | ServletRequestListener | 对Request对象进行监听（创建、销毁） |  
























# XML
这里可以学一下[Maven](https://blog.csdn.net/fanlangke/article/details/126723063)的依赖管理(pom.xml)
# JSON
JSON基础语法
```json
定义：
var 变量名= {
	"key1":value1,
	"key2":value2,
	...
}
示例：
var json = {"name":"zhangsan",
	"age":23,
	"addr":["北京","上海","西安门"]
；
获取数据：
变量名.key
json.name
```
```
value的数据类型为：
数字（整数或浮点数）
字符串（在双引号中）
逻辑值(true或false)
数组（在方括号中）
对象（在花括号中）
null
```
## JSON数据和Java对象转换
Fastjson是阿里巴巴提供的一个Java语言编写的高性能功能完善的JSON库，是目前Java语言中最快的JSON库，可以实现Java对象和JSON字符串的相互转换。
使用：
1.导入坐标
```xml
<dependency>
	<groupld>com.alibaba</groupld>
	<artifactld>fastjson</artifactld>
	<version>1.2.62</version>
</dependency>
```
2.Java对象转SON
```java
String jsonStr = JSON.toJSONString(obj);
```
3.JSON字符串转)ava对象
响应
```java
User user = JSON.parseObject(jsonStr,User.class);
```
