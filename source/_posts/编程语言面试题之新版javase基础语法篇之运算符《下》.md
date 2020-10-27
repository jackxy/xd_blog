---
title: 编程语言面试题之新版javase基础语法篇之运算符《下》
date: 2020-10-27 18:42:40
tags:
---
**简介：讲解异或运算在面试中的考查点和分析**

- 考点：计算机基础运算知识
- 难度【***】

* 写个方法，传递两个非0的int数值进去，实现变量交换的方式，有几种方式？

  * 方式一

    ```
     public static void swap(int a, int b){
    
            System.out.printf("a=%d, b=%d",a,b);
            a = a + b;
            b = a - b ;
            a = a - b;
            System.out.printf("\na=%d, b=%d",a,b);
        }
    ```

  * 方式二 异或运算 (一个数与另一个数异或两次是其本身， 一个数和自身异或结果是0 )

    ```
     public static void swap2(int a, int b){
    
         System.out.printf("a=%d, b=%d",a,b);
    
         a = a^b;   // a1 = a^b
         b = b^a;   // b = b^a^b
         a = a^b;   // a = a1^b = a^b^a
    
         System.out.printf("\na=%d, b=%d",a,b);
     }
     
     解释：
    	a1=a^b
    	b=b^a1=b^a^b=a
        //此时a1=a^b  b=a
    	a=a1^b=a^b^a=b
    ```
