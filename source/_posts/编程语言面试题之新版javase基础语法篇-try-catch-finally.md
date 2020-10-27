---
title: 编程语言面试题之新版javase基础语法篇 try-catch-finally
date: 2020-10-27 18:43:05
tags:
---
**简介：try-catch-finally异常处理模块的返回值问题**

* 考点：编码规范和执行逻辑
* 难度【***】

- 下面代码 的try-catch-finally语句，try里面有个return, finally里面也有个return，结果会返回什么？为什么

```
public static int test1() {
        int a = 1;
        try {
            System.out.println(a / 0);
            a = 2;
        } catch (ArithmeticException e) {
            a = 3;
            return a; 

        } finally {
            a = 4;
        }
        return a;

    }

    public static int test2() {
        int a = 1;
        try {
            System.out.println(a / 0);
            a = 2;
        } catch (ArithmeticException e) {
            a = 3;
            return a;

        } finally {
            a = 4; 
            return a;
        }


    }
```



```
答案：	
	在执行try、catch中的return之前一定会执行finally中的代码（如果finally存在），如果finally中有return语句，就会直接执行finally中的return方法，所以finally中的return语句一定会被执行的

	执行流程：finally执行前的代码里面有包含return，则会先确定return返回值，然后再执行finally的代码，最后再执行return
```

```
小滴课堂 PS: 工作中项目如果这样写，猜会不会被打，不要这样写！！！
```
