---
title: 编程语言面试题之新版javase集合框架List基础篇
date: 2020-10-27 18:49:31
tags:
---
**简介：java集合框架里面List常见基础面试题**

- 考查点：list的基础知识点掌握情况，对应的实现的区别，线程安全、使用场景
- 难度【***】
- 说下Vector和ArrayList、LinkedList联系和区别？分别的使用场景
- 答案：
  - 线程安全
    - ArrayList：底层是数组实现，线程不安全，查询和修改非常快，但是增加和删除慢
    - LinkedList:  底层是双向链表，线程不安全，查询和修改速度慢，但是增加和删除速度快
    - Vector: 底层是数组实现，线程安全的，操作的时候使用synchronized进行加锁
  - 使用场景
    - Vector已经很少用了
    - 增加和删除场景多则用LinkedList
    - 查询和修改多则用ArrayList