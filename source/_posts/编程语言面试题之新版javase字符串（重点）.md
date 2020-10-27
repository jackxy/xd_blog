---
title: 编程语言面试题之新版javase字符串（重点）
date: 2020-10-27 18:47:45
tags:
---
**简介：常用字符串的考查点**

* 难度【***】

* 问题1:  String str = new String("xdclass.net"); 创建了几个对象？

  ```
  答案：
  
  创建一个对象：常量池存在，则直接new一个对象；
  
  创建两个对象：常量池不存在，则在常量池创建一个对象，也在堆里面创建一个对象
  ```


* 问题2: 下面是比较什么？输出结果是什么？为什么是这样的结果
  String str1= new String("xdclass.net");
  String str2= "xdclass.net";
  String str3= "xdclass.net";
  System.out.println(str1 == str2) //false
  System.out.println(str2 == str3) //true

```
答案：
比较引用的内存地址是否一样
第一个是false： new 创建新的对象会开辟新的空间，所以地址不一样
第二个是true：都是从常量池里面获取，"xdclass.net" 存在于常量池中
```

* 问题3： 写出下面代码的各个结果？如果需要两个都为true，应该怎么修改`

```
String s1 = "xdclass";

String s2 = s1 + ".net";  //变量 + 常量 = 来自堆

String s3 = "xdclass" + ".net";  //常量 + 常量 = 来自常亮池

System.out.println(s2 == "xdclass.net"); 

System.out.println(s3 == "xdclass.net");
```

```
答案
第一条语句打印的结果为false， s2 = s1 + ".net",   //变量+常量=堆
构建了一个新的string对象，并将对象引用赋予s2变量，常量池中的地址不一样，但是值一样。


第二条语句打印的结果为true，javac编译可以对【字符串常量】直接相加的表达式进行优化，不用等到运行期再去进行加法运算处理，而是直接将其编译成一个这些常量相连的结果.

如果需要第一个输出为true，只需要把变量改为常量即可 fianl String s1 = "xdclass";
不管是new String("XXX")和直接常量赋值, 都会在字符串常量池创建.只是new String("XXX")方式会在堆中创建一个对象去指向常量池的对象, 普通的常量赋值是直接赋值给变量
```


