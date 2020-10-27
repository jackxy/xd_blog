---
title: 编程语言面试题之新版JDK9基础语法篇 try-with-resource
date: 2020-10-27 18:46:43
tags:
---
**简介：新特性考察  try-with-resource 知识点**

- 考点：编程基础和是否有学习新知识特性
- 难度【** **】
- 有了解新版的JDK处理IO流吗？编写下基础代码, 从一个txt文本里面，拷贝里面的内容到另外一个txt文本里面

```
JDK7之后的写法，JDK9⼜进⾏了改良，但是变化不⼤，记住下⾯的写法即可
需要关闭的资源只要实现了java.lang.AutoCloseable，就可以⾃动被关闭
try()⾥⾯可以定义多个资源，它们的关闭顺序是最后在try()定义的资源先关闭
```

```
 try (
FileInputStream fis = new FileInputStream("/Users/xdclass/Desktop/test.txt");
BufferedInputStream bis = new BufferedInputStream(fis);
FileOutputStream fos = new FileOutputStream("/Users/xdclass/Desktop/copy.txt");
BufferedOutputStream bos = new BufferedOutputStream(fos);
 	  ) {
            int size;
            byte[] buf = new byte[1024];
            while ((size = bis.read(buf)) != -1) {
                bos.write(buf, 0, size);
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
```

