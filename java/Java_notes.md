# Java版本

java 8，11，17是长期支持（LTS）版本

# Java重要特点

1. Java语言是面向对象的(oop)
2. Java语言是健壮的。Java的强类型机制、异常处理、垃圾的自动收集等是Java程序健壮性的重要保证
3. Java语言是跨平台性的。[即：一个编译好的.class文件可以在多个系统(linux,windows,mac)下运行，这种特性
   称为跨平台]
4. Java语言是解释型的[了解]
   解释性语言：javascript,PHP,java编译性语言：c/c++
   区别是：解释性语言，编译后的代码，不能直接被机器执行，需要解释器来执行，编译性语言，
   编译后的代码，可以直接被机器执行，c/c++

# Java的开发工具

1. editplus、notepad++
2. Sublime Text
3. IDEA
4. eclipse

ps：我用的是IDEA

# JVM,JDK,JRE

### JVM基本介绍

1. JVM是一个虚拟的计算机，具有指令集井便用不同的字储区域。负责执行指令，管理数据、内存、寄存器，包含在JDK中
2. 对于不同的平台，有不同的虚拟机。
3. Java虚拟机机制屏蔽了底层运行平台的差别，实现了"一次编译，到处运行"

### JDK基本介绍

1. JDK的全称(Java Development Kit Java开发工具包)
   JDK=JRE+java的开发工具[java,javac,javadoc,javap等]
2. JDK是提供给Java开发人员使用的，其中包含了java的开发工具，也包括了JRE,所以安装了JDK,就不用在单独安装JRE了。



### JRE基本介绍

1. JRE(Java Runtime EnvironmentJava运行环境)JRE=JVM+Java的核心类库[类]

2. 包括Java虚拟机VM Java Virtual Machine)和Java程序所需的核心类库等，如果想要运行一个开发好的java程序，计算机中只需要安装JRE即可。

### JDK、JRE和JVM的包含关系

1.JDK=JRE+开发工具集（例如Javac,java编译工具等）
2.JRE=JVM+Java SE标准类库(Java核心类库)
3.如果只想运行开发好的.class.文件只需要JRE

# java开发细节

1. Java源文件以java为扩展名。源文件的基本组成部分是类(class),如本类中的Hello类。
2. Java应用程序的执行入口是main()方法。它有固定的书写格式：
   public static void main(String[] args){...}
3. Java语言严格区分大小写。
4. Java方法由一条条语句构成，每个语句以";”结束。
5. 大括号都是成对出现的，缺一不可。[习惯，先写{}再写代码]
6. 一个源文件中最多只能有一个public类。其它类的个数不限。
7. 如果源文件包含一个public类，则文件名必须按该类名命名！
8. 一个源文件中最多只能有一个public类。其它类的个数不限，也可以将main方法写在非public类中，然后指定运行非public类，这样入口方法就是非public的main方法

# Java常用的转义字符

1)\t:一个制表位，实现对齐的功能（tab键）
2)\n:换行符
3)\\\:一个\
4)\\":一个”
5)\\':一个'
6)\r:一个回车

## \r、\n、以及\r\n的区别(了解)

\r ：将当前位置移到本行开头。又叫回车，对应键盘上的return键
\n：将当前位置移到下一行开头。又叫换行，newline。

这时候可能就有人陷入了思考中，在文本中回车不就相当于换行了吗？换行不就相当于到了下一行了吗？其实按道理说这样理解是没有问题的，但是在不同的操作系统中，换行是由不同的方式来表示的。

Linux中\n表示回车并换行；
Windows中\r\n表示回车并换行。
Mac中\r表示回车并换行。

# java注释

1. 快捷键ctrl+/
2. //
3. /*   ...       */

## java文档注释

Javadoc 工具可以识别文档注释中的一些特殊标签，这些标签一般以`@`开头，后跟一个指定的名字，有的也以`{@`开头，以`}`结束。

```java
/**
 *  @author fanlangke
 *  @version 1.0
 */

public class hello{
        public static void main(String[] args){

        }
}

```



```bash
javadoc -author -version -encoding UTF-8 hello.java
javadoc -d 保存位置 -author -version -encoding UTF-8 hello.java
```

# java代码规范

```text
1.类、方法的注释，要以javadoc的方式来写。
2.非Java Doc的注释，往往是给代码的维护者看的，着重告述读者为什么这样写，
如何修改，注意什么问题等
3.使用tab操作，实现缩进，默认整体向右边移动，时候用shift+tab整体向左移
4.运算符和=两边习惯性各加一个空格。比如：2 + 4 * 5 + 345 - 89
5.源文件使用utf-8编码
6.行宽度不要超过80字符
7.代码编写次行风格和行尾风格
行尾风格,推荐
int main(){
	return 0;
}
次行风格
int main()
{
	return 0;
}
```

# dos命令

Disk Operating System磁盘操作系统

```bash
#相关的知识补充：相对路径，绝对路径
#常用的dos命令
#1.查看当前目录是有什么内容dir
dir Desktop
#2.切换到其他盘下：盘符号cd:change directory
#案例演示：切换到c盘
cd /D c:
#3.切换到当前盘的其他目录下（使用相对路径和绝对路径演示），…表示上一级目录
案例演示：cd desktop
#4.切换到上一级：
案例演示：cd ..
#5.切换到根目录：cd \
案例演示：cd \
#6.查看指定的目录下所有的子级目录
tree
#7.清屏
cls
#8.退出DOS
exit
#9.说明：因为小伙伴后面使用DOS非常少，所以对下面的几个指令，老韩给大家演示下，
大家了解即可(md[创建目录]，rd[删除目录]，copy[拷贝文件]，del[删除文件]，echo[输入内容到文件]，type,move[剪切])
```

# instanceof

| instanceof | 用于判断对象的运行类型是否为XX类型或XX类型的子类型 | "hsp" instanceof  String | true |
| ---------- | -------------------------------------------------- | ------------------------ | ---- |

# 键盘输入输出

```java
import java.util.Scanner;
public class hello{
        public static void main(String[] args){
                Scanner myScanner=new Scanner(System.in);
                String myname=myScanner.next();
                System.out.println(myname);
        }
}

```

# 面向对象(OOP)

```java
class Cat {
    String name;
    int age;
    String color;
}
```



![image-20220701125142871](Java_notes.assets/image-20220701125142871.png)

# 方法重载(OverLoad)

##### 基本介绍

java中允许同一个类中，多个同名方法的存在，但要求形参列表不一致！
比如：System.out.printIn();out是PrintStream类型

##### 重载的好处

1)减轻了起名的麻烦
2)减轻了记名的麻烦

# 可变参数

java允许将同一个类中多个同名同功能但参数个数不同的方法，封装成一个方法。
就可以通过可变参数实现

下面结果输出15

```java
import java.util.Scanner;
public class hello{
        public static void main(String[] args){
                Method m=new Method();
                System.out.println(m.sum(1,2,3,4,5));
        }
}
class Method{
        public int sum(int ...arr) {
                int a = 0;
                for (int i = 0; i < arr.length; i++) {
                        a += arr[i];
                }
                return a;
        }
}
```

# 构造方法/构造器

1. 看一个需求
   我们来看一个需求：前面我们在创建人类的对象时，是先把一个对象创建好后，再给
   他的年龄和姓名属性赋值，如果现在我要求，在创建人类的对象时，就直接指定这个
   对像的年龄和姓名，该怎么做？这时就可以使用构造器。

2. 基本语法
   ```java
   [修饰符]  方法名 （形参列表）{
   	方法体;
   }
   ```

   1)构造器的修饰符可以默认
   2)构造器没有返回值
   3)方法名和类名字必须一样
   4)参数列表和成员方法一样的规则
   5)构造器的调用系统完成

   ```java
   import java.util.Scanner;
   public class hello{
           public static void main(String[] args){
                   Person p=new Person("fanlangke",18);
                   System.out.println(p.name+p.age);
           }
   }
   class Person{
           String name;
           int age;
           //构造器
           public Person(String pName,int pAge){
                   name=pName;
                   age=pAge;
           }
   }
   ```

   ```text
   输出
   fanlangke18
   ```


# this

   简单的说，哪个对象调用，this就代表哪个对象

      1. this关键字可以用来访问本类的属性、方法、构造器
      2. ths用于区分当前类的属性和局部变量
      3. 访问成员方法的语法：this.方法名（参数列表）：
      4. 访问构造器语法：this(参数列表)：注意只能在构造器中使用（即只能在构造器中访问另外一个构造器，必须放在第一条语句)
      5. this不能在类定义的外部使用，只能在类定义的方法中使用。

# IDEA常用快捷键

1)删除当前行，默认是ctrl+Y自己配置ctrl+d
2)复制当前行，自己配置ctrl+alt+向下光标
3)补全代码alt+/
4)添加注释和取消注释ctrl+/【第一次是添加注释，第二次是取消注释】
5)导入该行需要的类先配置auto import,然后使用alt+enter即可
6)快速格式化代码ctrl+alt+L
7)快速运行程序自己定义alt+R
8)生成构造器等alt+insert[提高开发效率]
9)查看一个类的层级关系ctrl+H[学习继承后，非常有用]
10)将光标放在一个方法上，输入ctrl+B,可以定位到方法[学继承后，非常有用]
11)自动的分配变量名，通过在后面加.var[老师最喜欢的]
12)还有很多其它的快捷键.
13)ctrl+alt+T

# 包

##### 包的命名

只能包含数字、字母、下划线、小圆点，但不能用数字开头，不能是关键字或保留字

##### 命名规范

一般是小写字母+小圆点

一般是com.公司名.项目名.业务模块名

##### 常用的包

一个包下，包含很多的类，java中常用的包有：
```text
java.lang.*
/lang包是基本包，默认引入，不需要再引入.
java.util.*
/util包，系统提供的工具包，工具类，使用Scanner
java.net.*
/网络包，网络开发
java.awt.*
/是做java的界面开发，GUI
```

##### 包引入

```text
注意事项和使用细节
1.package的作用是声明当前类所在的包，
需要放在的最上面而一个类中最多只有一句package
2.import指令位置放在package的下面，在类定义前面，可以有多句且没有顺序要求。
```

# 访问修饰符

1. 公开级别：用public修饰，对外公开
2. 受保护级别：用protected修饰，对子类和同一个包中的类公开
3. 默认级别没有修饰符号，向同一个包的类公开.
4. 私有级别：用private修饰，只有类本身可以访问，不对外公开.
5. ![image-20220702115655299](Java_notes.assets/image-20220702115655299.png)

# 封装

##### 封装的实现步骤

```text
1)将属性进行私有化【不能直接修改属性】

2)提供一个公共的set方法，用于对属性判断并赋值
public void setXxx(类型参数名){
	//加入数据验证的业务逻辑
	属性=参数名;
}

3)提供一个公共的get方法，用于获取属性的值
public XX getXxx(){//权限判断
	return XX;
}
```



# 继承

```java
//让Pupil 继承 Student类
public class Pupil extends Students{
        public void testing(){
                System.out.println("小学生");
        }
}
```

##### 细节

1. 子类继承了所有的属性和方法，但是私有属性和方法不能在子类直接访问，要通过公共的方法去访问
2. 子类必须调用父类的构造器，完成父类的初始化
3. 当创建子类对象时，不管使用子类的哪个构造器，默认情况下总会去调用父类的无参构造器，如果父类没有提供无参构造器，则必须在子类的构造器中用super去指定使用父类的哪个构造器完成对父类的初始化工作，否则，编译不会通过
4. 如果希望指定去调用父类的某个构造器，则显式的调用一下
5. super在使用时，需要放在构造器第一行
6. super())和this()都只能放在构造器第一行，因此这两个方法不能共存在一个构造器
7. java所有类都是Object类的子类
8. 父类构造器的调用不限于直接父类！将一直往上追溯直到Object类（顶级父类）
9. 子类最多只能继承一个父类



![image-20220702124432278](Java_notes.assets/image-20220702124432278.png)

## super

1.访问父类的属性，但不能访问父类的private属性[案例]
super.属性名；
2.访问父类的方法，不能访问父类的private方法
super.方法名（参数列表）：
3.访问父类的构造器（这点前面用过）：
super(参数列表);只能放在构造器的第一句，只能出现一句！

# 方法重写（override）

简单的说：方法覆盖（重写）就是子类有一个方法，和父类的某个方
法的名称、返回类型、参数一样，那么我们就说子类的这个方法
覆盖了父类的那个方法

# 多态

1.方法的多态PloyMethod.java
重写和重载就体现多态

2.对象的多态（核心，因难，重点）
老韩重要的几句话（记住）：
(1)一个对象的编译类型和运行类型可以不一致
(2)编译类型在定义对象时，就确定了，不能改变
(3)运行类型是可以变化的.
(4)编译类型看定义时=号的左边，
运行类型看=号的右边

```java
Animal animal=new Dog();
【animal编译类型是Animal,运行类型Dog】
animal=new Cat();
【animal的运行类型变成了Cat,编译类型仍然是Animal】
```

```java
public void feed(Animal animal,Bone bone){
        System.out.println("主人"+name+"给"+animal.getName()+"吃"+food.getName());
}
```

## 向上/向下转型

运行类型和编译类型

## 动态绑定机制

当调用对象方法的时候，该方法会和该对象的内存地址/运行类型绑定

当调用对象属性时，没有动态绑定机制，哪里声明，那里使用

# object

1. equals:是object类中的方法，只判断引用类型。String类对equals方法进行了重写，用来比较指向的字符串对象所存储的字符串是否相等。其他的一些类诸如Double，Date，Integer等，都对equals方法进行了重写用来比较指向的对象所存储的内容是否相等。
1. “java”中使用“if”语句判断字符串是否相等的方法是：可以使用**“==”或者“equals”方法**，两者都可以比较字符串是否相等，但是不同的是，“==”比较的是两个字符串的地址是否相等，“equals”方法比较的是字符串对象的内容是否相同。
2. hashcode()
3. toString()
4. finalize()

# 类变量

```text
1.什么时候需要用类变量
当我们需要让某个类的所有对象都共享一个变量时，就可以考虑使用类变量（静态变量：比如：定义学生类，统计所有学生共交多少钱Student(name,static fee)
2.类变量与实例变量（普通属性）区别
类变量是该类的所有对象共享的，而实例变量是每个对象独享的。
3.加上static称为类变量或静态变量，否则称为实例变量/普通变量/非静态变量
4.类变量可以通过类名.类变量名或者对象名.类变量名来访问，但java设计者推荐
我们使用类名类变量名方式访问。【前提是满足访问修饰符的访问权限和范围】
```

# main

# 代码块

普通代码块

静态代码块

构造方法（构造器）的最前面其实隐含了super()和调用普通代码块

# 单例设计模式

饿汉式

懒汉式

# final

![image-20220724092327351](Java_notes.assets/image-20220724092327351.png)

![image-20220724093918551](Java_notes.assets/image-20220724093918551.png)

![image-20220724093936322](Java_notes.assets/image-20220724093936322.png)

# 抽象类

![image-20220724094557728](Java_notes.assets/image-20220724094557728.png)

![image-20220724094709739](Java_notes.assets/image-20220724094709739.png)

![image-20220724095617893](Java_notes.assets/image-20220724095617893.png)

![image-20220724095806643](Java_notes.assets/image-20220724095806643.png)

![image-20220724100254509](Java_notes.assets/image-20220724100254509.png)

# 接口

![image-20220724141711821](Java_notes.assets/image-20220724141711821.png)

![image-20220724142646470](Java_notes.assets/image-20220724142646470.png)

![image-20220724143709716](Java_notes.assets/image-20220724143709716.png)

![image-20220724144431387](Java_notes.assets/image-20220724144431387.png)

# 内部类

![image-20220724151550520](Java_notes.assets/image-20220724151550520.png)

![image-20220724151920723](Java_notes.assets/image-20220724151920723.png)

![image-20220725083957687](Java_notes.assets/image-20220725083957687.png)

![image-20220725084615187](Java_notes.assets/image-20220725084615187.png)

![image-20220725085452477](Java_notes.assets/image-20220725085452477.png)

![image-20220725090059962](Java_notes.assets/image-20220725090059962.png)

![image-20220725090307729](Java_notes.assets/image-20220725090307729.png)

![image-20220725090530548](Java_notes.assets/image-20220725090530548.png)

![image-20220725091034450](Java_notes.assets/image-20220725091034450.png)

![image-20220725091101791](Java_notes.assets/image-20220725091101791.png)

![image-20220725091303668](Java_notes.assets/image-20220725091303668.png)

![image-20220725091344834](Java_notes.assets/image-20220725091344834.png)

![image-20220725091519900](Java_notes.assets/image-20220725091519900.png)

![image-20220725091553729](Java_notes.assets/image-20220725091553729.png)

![image-20220725091809372](Java_notes.assets/image-20220725091809372.png)

# 枚举

![image-20220725094724031](Java_notes.assets/image-20220725094724031.png)

![image-20220725110908786](Java_notes.assets/image-20220725110908786.png)

![image-20220725111731600](Java_notes.assets/image-20220725111731600.png)

![image-20220725112022334](Java_notes.assets/image-20220725112022334.png)

![image-20220725112539945](Java_notes.assets/image-20220725112539945.png)

![image-20220725112750898](Java_notes.assets/image-20220725112750898.png)

# 注解

![image-20220725113035857](Java_notes.assets/image-20220725113035857.png)

![image-20220725113214431](Java_notes.assets/image-20220725113214431.png)

![image-20220725114235634](Java_notes.assets/image-20220725114235634.png)

# 异常

![image-20220725120526348](Java_notes.assets/image-20220725120526348.png)

![image-20220725122110244](Java_notes.assets/image-20220725122110244.png)

![image-20220725122851696](Java_notes.assets/image-20220725122851696.png)

![image-20220725122955864](Java_notes.assets/image-20220725122955864.png)

![image-20220725123852576](Java_notes.assets/image-20220725123852576.png)

![image-20220725124051731](Java_notes.assets/image-20220725124051731.png)

![image-20220725124515761](Java_notes.assets/image-20220725124515761.png)

![image-20220725124638625](Java_notes.assets/image-20220725124638625.png)

![image-20220725124813865](Java_notes.assets/image-20220725124813865.png)

![image-20220725124955550](Java_notes.assets/image-20220725124955550.png)

![image-20220725125620742](Java_notes.assets/image-20220725125620742.png)

![image-20220725125638714](Java_notes.assets/image-20220725125638714.png)

![image-20220725125938501](Java_notes.assets/image-20220725125938501.png)

# 包装类

![image-20220725162756356](Java_notes.assets/image-20220725162756356.png)

![image-20220725162935613](Java_notes.assets/image-20220725162935613.png)

## String类

![image-20220725164415678](Java_notes.assets/image-20220725164415678.png)

![image-20220725164757998](Java_notes.assets/image-20220725164757998.png)

![image-20220725165227686](Java_notes.assets/image-20220725165227686.png)

![image-20220725165646275](Java_notes.assets/image-20220725165646275.png)

![image-20220725170405990](Java_notes.assets/image-20220725170405990.png)

![image-20220725170514991](Java_notes.assets/image-20220725170514991.png)

## stringbuffer

![image-20220726082425715](Java_notes.assets/image-20220726082425715.png)

![image-20220726082634367](Java_notes.assets/image-20220726082634367.png)

![image-20220726082836875](Java_notes.assets/image-20220726082836875.png)

![image-20220726082938900](Java_notes.assets/image-20220726082938900.png)

## stringbuilder

![image-20220726083237976](Java_notes.assets/image-20220726083237976.png)

## math类

![image-20220726083954665](Java_notes.assets/image-20220726083954665.png)

## arrays类

![image-20220726084749138](Java_notes.assets/image-20220726084749138.png)

![image-20220726085729679](Java_notes.assets/image-20220726085729679.png)

## system类

![image-20220726090039122](Java_notes.assets/image-20220726090039122.png)

## bigInteger和bigDecimal

![image-20220726090439843](Java_notes.assets/image-20220726090439843.png)

## Date类

![image-20220726090504077](Java_notes.assets/image-20220726090504077.png)

## calendar

![image-20220726090932403](Java_notes.assets/image-20220726090932403.png)

![image-20220726091018252](Java_notes.assets/image-20220726091018252.png)

## 第三代日期类

![image-20220726091157490](Java_notes.assets/image-20220726091157490.png)

![image-20220726091306356](Java_notes.assets/image-20220726091306356.png)

![image-20220726091352315](Java_notes.assets/image-20220726091352315.png)

# 集合（容器）

![image-20220726155656950](Java_notes.assets/image-20220726155656950.png)

## collection常用方法

![image-20220726161404541](Java_notes.assets/image-20220726161404541.png)

## 迭代器遍历

![image-20220726162929183](Java_notes.assets/image-20220726162929183.png)

## 集合增强for

![image-20220726163038604](Java_notes.assets/image-20220726163038604.png)

## List

![image-20220726182128471](Java_notes.assets/image-20220726182128471.png)

![image-20220726182114269](Java_notes.assets/image-20220726182114269.png)

### ArrayList

![image-20220727071928964](Java_notes.assets/image-20220727071928964.png)

![image-20220727072020495](Java_notes.assets/image-20220727072020495.png)

### Vector

![image-20220727072250864](Java_notes.assets/image-20220727072250864.png)

![image-20220727072313753](Java_notes.assets/image-20220727072313753.png)

### LinkedList

![image-20220727072445500](Java_notes.assets/image-20220727072445500.png)

![image-20220727072459443](Java_notes.assets/image-20220727072459443.png)

![image-20220727072656119](Java_notes.assets/image-20220727072656119.png)

## Set

![image-20220727073311478](Java_notes.assets/image-20220727073311478.png)

![image-20220727073322345](Java_notes.assets/image-20220727073322345.png)

![image-20220727073727233](Java_notes.assets/image-20220727073727233.png)

### HashSet

![image-20220727074016825](Java_notes.assets/image-20220727074016825.png)

![image-20220727074358354](Java_notes.assets/image-20220727074358354.png)

#### LinkedHashSet

![image-20220727074941182](Java_notes.assets/image-20220727074941182.png)

## Map

![image-20220727075255701](Java_notes.assets/image-20220727075255701.png)

![image-20220727075452023](Java_notes.assets/image-20220727075452023.png)

![image-20220727075526812](Java_notes.assets/image-20220727075526812.png)

![image-20220727075659878](Java_notes.assets/image-20220727075659878.png)

### HashMap

![image-20220727075842385](Java_notes.assets/image-20220727075842385.png)

### HashTable

![image-20220727075934576](Java_notes.assets/image-20220727075934576.png)

### properties

![image-20220727080138382](Java_notes.assets/image-20220727080138382.png)

## 集合选型

![image-20220727080227707](Java_notes.assets/image-20220727080227707.png)

## collection工具类

![image-20220727080741182](Java_notes.assets/image-20220727080741182.png)

![image-20220727080804790](Java_notes.assets/image-20220727080804790.png)

# 泛型

![image-20220727083007676](Java_notes.assets/image-20220727083007676.png)

![image-20220727083145261](Java_notes.assets/image-20220727083145261.png)

### 自定义泛型

![image-20220727083355801](Java_notes.assets/image-20220727083355801.png)

![image-20220727083934822](Java_notes.assets/image-20220727083934822.png)

![image-20220727084707591](Java_notes.assets/image-20220727084707591.png)

![image-20220727084955216](Java_notes.assets/image-20220727084955216.png)

# java绘图

![image-20220727123132242](Java_notes.assets/image-20220727123132242.png)

![image-20220727123204802](Java_notes.assets/image-20220727123204802.png)

# 线程

![image-20220727143246167](Java_notes.assets/image-20220727143246167.png)

![image-20220727143800205](Java_notes.assets/image-20220727143800205.png)

![image-20220727143841946](Java_notes.assets/image-20220727143841946.png)

## 创建线程

![image-20220727183406051](Java_notes.assets/image-20220727183406051.png)

![image-20220728074805825](Java_notes.assets/image-20220728074805825.png)

## 终止线程

![image-20220728080819546](Java_notes.assets/image-20220728080819546.png)

## 线程方法

![image-20220728080930166](Java_notes.assets/image-20220728080930166.png)

## 插队线程

![image-20220728081813259](Java_notes.assets/image-20220728081813259.png)

## 守护线程

![image-20220728082501190](Java_notes.assets/image-20220728082501190.png)

## 线程状态

![image-20220728084049650](Java_notes.assets/image-20220728084049650.png)

## 线程同步

![image-20220728084201340](Java_notes.assets/image-20220728084201340.png)

![image-20220728084656245](Java_notes.assets/image-20220728084656245.png)

# 锁

## 互斥锁

![image-20220728090533135](Java_notes.assets/image-20220728090533135.png)

![image-20220728090501061](Java_notes.assets/image-20220728090501061.png)

## 死锁

![image-20220728090800693](Java_notes.assets/image-20220728090800693.png)

## 释放锁

![image-20220728091024149](Java_notes.assets/image-20220728091024149.png)

![image-20220728091124320](Java_notes.assets/image-20220728091124320.png)

# IO流

## 创建文件

![image-20220729092831077](Java_notes.assets/image-20220729092831077.png)

## 获取文件

![image-20220729093253755](Java_notes.assets/image-20220729093253755.png)

![image-20220729093315781](Java_notes.assets/image-20220729093315781.png)

## 文件删除

![image-20220729093536552](Java_notes.assets/image-20220729093536552.png)

![image-20220729093608432](Java_notes.assets/image-20220729093608432.png)

## IO流原理

### 概况

![image-20220729094412621](Java_notes.assets/image-20220729094412621.png)





### 节点流

#### FileInputStream

![image-20220730084058674](Java_notes.assets/image-20220730084058674.png)

#### FileOutputStream

![image-20220730092432840](Java_notes.assets/image-20220730092432840.png)

#### FileReader和FileWriter

![image-20220730092830046](Java_notes.assets/image-20220730092830046.png)

![image-20220730093057528](Java_notes.assets/image-20220730093057528.png)

#### FileReader

![image-20220730093158647](Java_notes.assets/image-20220730093158647.png)

#### FileWriter

![image-20220730093243168](Java_notes.assets/image-20220730093243168.png)

### 节点流和处理流

![image-20220730094923480](Java_notes.assets/image-20220730094923480.png)

#### BufferedReader和BufferedWriter

![image-20220730095614232](Java_notes.assets/image-20220730095614232.png)

![image-20220730095650692](Java_notes.assets/image-20220730095650692.png)

![image-20220730095742221](Java_notes.assets/image-20220730095742221.png)

![image-20220730100110104](Java_notes.assets/image-20220730100110104.png)

#### BufferedInputStream和BufferedOutputStream

![image-20220730100324844](Java_notes.assets/image-20220730100324844.png)

### 对象流

![image-20220730100704089](Java_notes.assets/image-20220730100704089.png)

![image-20220730100727553](Java_notes.assets/image-20220730100727553.png)

![image-20220730100807583](Java_notes.assets/image-20220730100807583.png)

![image-20220730100939642](Java_notes.assets/image-20220730100939642.png)

![image-20220730101031223](Java_notes.assets/image-20220730101031223.png)

### 标准输入输出流

![image-20220730142851903](Java_notes.assets/image-20220730142851903.png)

### 转换流

#### InputStreamReader和OutputStreamWriter

![image-20220730143347980](Java_notes.assets/image-20220730143347980.png)

![image-20220730143627885](Java_notes.assets/image-20220730143627885.png)

![image-20220730143547973](Java_notes.assets/image-20220730143547973.png)

#### PrintStream和PrintWriter

![image-20220730143822901](Java_notes.assets/image-20220730143822901.png)

## properties

![image-20220730145041822](Java_notes.assets/image-20220730145041822.png)

![image-20220730145105886](Java_notes.assets/image-20220730145105886.png)

![image-20220730145240599](Java_notes.assets/image-20220730145240599.png)

# 网络编程

## 网络

![image-20220801074123909](Java_notes.assets/image-20220801074123909.png)

## ip地址

![image-20220801080341114](Java_notes.assets/image-20220801080341114.png)

![image-20220801080356649](Java_notes.assets/image-20220801080356649.png)

![image-20220801080407102](Java_notes.assets/image-20220801080407102.png)

## 域名和端口

![image-20220801081635012](Java_notes.assets/image-20220801081635012.png)

## 网络协议

![image-20220801083007383](Java_notes.assets/image-20220801083007383.png)

![image-20220801083116078](Java_notes.assets/image-20220801083116078.png)

## TCP和UDP

![image-20220801083958279](Java_notes.assets/image-20220801083958279.png)

![image-20220821140250953](Java_notes.assets/image-20220821140250953.png)

### TCP

#### 01

```text
1.编写一个服务器端，和一个客户端
2.服务器端在9999端口监听
3.客户端连接到服务器端，发送"hello,,server",然后退出
4.服务器端接收到客户端发送的信息，输出，并退出
```

```java
package com.lqx.socket;

import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import java.net.ServerSocket;
import java.net.Socket;

public class tcp01server {
    public static void main(String[] args) throws IOException {
        ServerSocket serverSocket = new ServerSocket(9999);
        System.out.println("服务端在端口9999监听");
        Socket socket = serverSocket.accept();
        System.out.println("服务端socket"+socket.getClass());
        InputStream iuputStream = socket.getInputStream();
        byte[] buf = new byte[1024];
        int readlen=0;
        while ((readlen=iuputStream.read(buf))!=-1) {
            System.out.println(new String(buf,0, readlen));//根据读取到的实际长度，显示内容，

        }
        //5.关闭流和socket
        iuputStream.close();
        socket.close();
        serverSocket.close();//关闭



    }
}

```

```java
package com.lqx.socket;

import java.io.IOException;
import java.io.OutputStream;
import java.net.InetAddress;
import java.net.Socket;
import java.net.UnknownHostException;

public class tcp01client {
    public static void main(String[] args) throws IOException {
        Socket socket = new Socket(InetAddress.getLocalHost(),9999);
        OutputStream outputstream =socket.getOutputStream();
//3。通过输出流，写入数据到数据通道
        outputstream.write("hello,server".getBytes());
//4.关闭流对象和socket,必须关闭
        outputstream.close();
        socket.close();
        System.out.println("客户端退出");
    }
}

```

#### 02

```text
1.编写一个服务端，和一个客户端
2.服务器端在9999端口监听
3.客户端连接到服务端，发送"hello,server'",并接收服务器端回发的
"hello,client",再退出
4.服务器端接收到客户端发送的信息，输出，并发送"hello,,client'",再退出
```

```java
package com.lqx.socket;

import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import java.net.ServerSocket;
import java.net.Socket;

public class tcp02server {
    public static void main(String[] args) throws IOException {
        ServerSocket serverSocket = new ServerSocket(9999);
        System.out.println("服务端在端口9999监听");
        Socket socket = serverSocket.accept();
        System.out.println("服务端socket"+socket.getClass());
        InputStream iuputStream = socket.getInputStream();
        byte[] buf = new byte[1024];
        int readlen=0;
        while ((readlen=iuputStream.read(buf))!=-1) {
            System.out.println(new String(buf,0, readlen));//根据读取到的实际长度，显示内容，

        }
        OutputStream outputstream =socket.getOutputStream();
        outputstream.write("hello,client".getBytes());
        socket.shutdownOutput();


        //5.关闭流和socket
        iuputStream.close();
        socket.close();
        serverSocket.close();//关闭
        outputstream.close();





    }
}

```

```java
package com.lqx.socket;

import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import java.net.InetAddress;
import java.net.Socket;
import java.net.UnknownHostException;

public class tcp02client {
    public static void main(String[] args) throws IOException {
        Socket socket = new Socket(InetAddress.getLocalHost(),9999);
        OutputStream outputstream =socket.getOutputStream();
//3。通过输出流，写入数据到数据通道
        outputstream.write("hello,server".getBytes());
        socket.shutdownOutput();
        InputStream iuputStream = socket.getInputStream();
        byte[] buf = new byte[1024];
        int readlen=0;
        while ((readlen=iuputStream.read(buf))!=-1) {
            System.out.println(new String(buf,0, readlen));//根据读取到的实际长度，显示内容，

        }

//4.关闭流对象和socket,必须关闭
        outputstream.close();
        socket.close();
        System.out.println("客户端退出");
    }
}

```



### UDP



## InetAddress类

![image-20220801084244321](Java_notes.assets/image-20220801084244321.png)

## socket

![image-20220801085415293](Java_notes.assets/image-20220801085415293.png)

![image-20220801085437036](Java_notes.assets/image-20220801085437036.png)

## netstat

![image-20220821135910408](Java_notes.assets/image-20220821135910408.png)



# 反射

![image-20220802084039335](Java_notes.assets/image-20220802084039335.png)

## 反射原理

![image-20220802084620254](Java_notes.assets/image-20220802084620254.png)

![image-20220802085514009](Java_notes.assets/image-20220802085514009.png)

## 反射相关类

![image-20220802090456323](Java_notes.assets/image-20220802090456323.png)

## 反射调用优化

![image-20220802090921289](Java_notes.assets/image-20220802090921289.png)

## Class类

![image-20220802091154431](Java_notes.assets/image-20220802091154431.png)

![image-20220802091828891](Java_notes.assets/image-20220802091828891.png)

## 获取class类

![image-20220802092542970](Java_notes.assets/image-20220802092542970.png)

![image-20220802092622001](Java_notes.assets/image-20220802092622001.png)

![image-20220802092723421](Java_notes.assets/image-20220802092723421.png)

##  哪些类型有class对象![image-20220802092831899](Java_notes.assets/image-20220802092831899.png)

## 类加载

![image-20220802093109809](Java_notes.assets/image-20220802093109809.png)

![image-20220802121111071](Java_notes.assets/image-20220802121111071.png)

![image-20220802123307054](Java_notes.assets/image-20220802123307054.png)



![image-20220802123318961](Java_notes.assets/image-20220802123318961.png)

![image-20220802123354662](Java_notes.assets/image-20220802123354662.png)

![image-20220802123415048](Java_notes.assets/image-20220802123415048.png)

![image-20220802123217441](Java_notes.assets/image-20220802123217441.png)

## 反射api

![image-20220802123505800](Java_notes.assets/image-20220802123505800.png)

![image-20220802123525396](Java_notes.assets/image-20220802123525396.png)

![image-20220802123619401](Java_notes.assets/image-20220802123619401.png)

![image-20220802123647899](Java_notes.assets/image-20220802123647899.png)

## 反射暴破

![image-20220802123809347](Java_notes.assets/image-20220802123809347.png)

![image-20220802123831514](Java_notes.assets/image-20220802123831514.png)

![image-20220802123900462](Java_notes.assets/image-20220802123900462.png)
