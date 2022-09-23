---
title: java第一章
author: yuri2078
avatar: 'https://cdn.jsdelivr.net/gh/yuri2078/images/img/custom/avatar.jpg'
authorLink: 'https://2078.site'
authorAbout: 一般过路人
authorDesc: 一般过路人
categories: java
comments: true
description: 我的爱宛如孤岛之花，不为人知的绽放，不为人知的凋零！
photos: 'https://cdn.jsdelivr.net/gh/yuri2078/images/headPictures/10.png'
date: 2021-11-30 11:11:11.149
updated: 2021-12-23 20:04:36.934
tags:
keywords:
---

首先打印第一个Java代码

    ```java
    public class hello
    {
        public static void main(String[] args)
        {
            System.out.println("hello java");
        }
    }

    ```
public class hello
一个公开定义的类 起名为hello

public 表示公开的
class 表示定义一个类
hello 表示 一个名为hello 的类名
{    }  里面的内容为类体

注意 类体里面禁止编写Java语句除了声明变量

       public static void main(String[] args)
一个公开的静态主方法。这是一个主方法是程序的执行入口

public 表示公开的
static 表示静态的
void   表示空
main   表示方法名
sring[] args 是一个mian方法的形式参数表列
args 这个可以随便写，别的不行。
{   }  里面的东西称之为  方法体   具体语句称之为Java语句。

注意 ：Java语句以 分号 ; 结尾，且必须是半角分号

System.out.println("hello java"); 这段代码的作用是向控制台输出一段字符串

一个Java源程序可以有多个class，但只能有一个public class ，并且名字与文件名对应。 源程序可以没有public class
