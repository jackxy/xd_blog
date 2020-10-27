---
title: 编程语言面试题之新版javase字符串相关构建类
date: 2020-10-27 18:48:09
tags:
---
**简介：常用字符串相关构建类的使用好区别**

- 考点：是否有举一反三的思维，常用类的掌握情况

- 难度【***】

- 问：String、StringBuffer与StringBuilder的区别？分别在哪些场景下使用

- 答案： 

  ```
  三者都是final， 不允许被继承
  在本质都是char[]字符数组实现
  String、StringBuffer与StringBuilder中，String是不可变对象，另外两个是可变的
  ```

  ```
  StringBuilder 效率更快，因为它不需要加锁，不具备多线程安全
  
  StringBuffer里面操作方法用synchronized ，效率相对更低,是线程安全的；
  
  使用场景：
  	操作少量的数据用String，但是常改变内容且操作数据多情况下最好不要用 String ，因为每次生成中间对象性能会降低
  
  	单线程下操作大量的字符串用StringBuilder，虽然线程不安全但是不影响
  
  	多线程下操作大量的字符串，且需要保证线程安全 则用StringBuffer
  ```

  
