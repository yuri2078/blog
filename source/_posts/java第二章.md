---
title: java第二章
author: yuri2078
avatar: 'https://cdn.jsdelivr.net/gh/yuri2078/images/img/custom/avatar.jpg'
authorLink: 'https://2078.site'
authorAbout: 一般过路人
authorDesc: 一般过路人
categories: java
comments: true
description: 我的爱宛如孤岛之花，不为人知的绽放，不为人知的凋零！
photos: 'https://cdn.jsdelivr.net/gh/yuri2078/images/headPictures/9.png'
date: 2021-12-01 19:35:33.566
updated: 2021-12-23 20:04:26.323
tags:
keywords:
---

Java标识符命名规则 ：

1. 只能由 数字，字母下划线，美元符号 构成
2.且不能以数字开头 严格区分大小写
3.关键字   不能作为标识符

命名规范可以不进行遵守，但是会降低代码可阅读性
    1. 命名应该具有可读性比如 username password
    2. 遵循驼峰法命名方式 比如 UserService
    3. 类名，接口名 首字母大写，后面每个单词首字母大写
    4. 变量名，方法名 首字母小写后面每个首字母大写
    5. 常量名全部大写

Java中的数据类型
10，20 这是整数型字面值
3.14   这是浮点型字面值
true false 这是布尔型字面值
"hello" 这是字符串型字面值 必须使用双引号括起来
'a' 这是字符型字面值 必须使用单引号括起来

打印输出各种类型的值

    ```java
    public class hello
    {
        public static void main(String[] args)
        {
            System.out.println("hello java");
            System.out.println('a');
            System.out.println(true);
            System.out.println(false);
            System.out.println(3.14);
            System.out.println(1000);
        }
    }

    ```

Java中的变量

数据类型 数据名； 如 int i；也可以直接赋值 如 int i = 1；

    ```java
    public class hello
    {
        public static void main(String[] args)
        {
            int i = 666; //定义整形变量i
            System.out.println(i); //输出整变量i
        }
    }
    ```
Java变量的作用域

总结 只在当前大括号之内有效

    ```java
    public class hello
    {
        static int  k = 555;
        public static void main(String[] args)
        {
            int i = 666; //定义整形变量i
            System.out.println(i); //输出整变量i
            System.out.println(k);
        }

        public static void miku(String[] args)
        {
            System.out.println("hello two ");
            System.out.println(k);
        }
    }
    ```

那么在for循环中会发生什么呢？

    ```java
    public class hello
    {
        public static void main(String[] args)
        {
            for(int i = 0;i < 10; i++)
            {
                System.out.println(i);
            }
            //System.out.println(i);
        }

    }
    ```
我们发现当我们把这个注释的语句放出来时，编译会报错，告诉我们找不到这个变量，也就是说在执行完for循环后，变量就找不到了。
因为这个i变量的作用域时整个for循环，循环结束就会释放i

局部变量： 在方法体内声明的变量 比如在mian方法中定义的变量
成员标量： 在方法体外声明的变量 比如在类体中定义的变量

在不同的作用域中变量名时可以相同的。但在同一个作用域中变量名不能相同。
就近原则 ： 优先访问局部变量，没有才访问成员变量

    ```java
    public class hello
    {
        static int i = 0;
        //这是成员变量
        public static void main(String[] args)
        {
            int x = 666;
            //这是局部变量
            System.out.println(x);
            System.out.println(i);
        }

    }
    ```
注意： 定义成员变量时一定要加static 并且系统会默认赋值为 0

Java中的数据类型

1、 引用数据型  比如 接口 类 数组 …………
2、 基本数据类型
(1) :  整数型 byte short int long
(2) :  浮点数型 float double
(3) :  布尔型 boolean
(4) :  字符型 char
字符串不属于基本数据类型，属于引用数据类型
占用空间的大小 单位 ： 字节范围

    ```java
    byte        1 -128 —— 127
    short       2 -32768 —— 32767
    int         4 -2^31 —— 2^31-1
    long        8 -2^63 —— 2^63-1
    float       4 3.402823e+38 ~ 1.401298e-45
    double      8 1.797693e+308~ 4.9000000e-324
    boolean     1 true 和 false
    char        2 可以时一个字母或者一个  中文汉字
    ```

整型  
1.在处理数据的时候默认当整型处理，所以long = 2^30 这是会报错的，因为他已经超过了int的最大长度了。Java把他放int型处理。
2.把int型变量给long型没问题，但是把long型变量给int型就会出现问题。因为大容量不能直接赋值给小容量。
3.强制类型转化可能会损失精度。所以运行时谨慎使用。强制转换原理 ：将前面4字节的内容砍掉，所以当原来的内容超过4字节时，使用强制转换可能会出现问题。强制类型转换符号  （int）变量名。大容量向小容量赋值必须使用强制类型转换。
4.如果整数没有超出byte short int  的范围，那么可以直接赋值给他们。如果超过他们的范围就必须使用强制类型转换。

浮点型
比如当出现 5.1这种类型数据的时候，默认是把他当作double
类型处理，所以   float f = 5.1 这句话是错的，因为5.1是大容量字面值，而float是小容量字面值，所以需要加强制类型转换。也可以加 f
1、  float f = (float)5.1
2、  float f = 5.1f

Java中的输入输出语句

输入 ： 一般使用Scanner

使用方法 先导入util包，在配和System.in使用

    ```java
    import java.util.Scanner;
    //引入util 包 Scanner 在util包里
    public class test 
    {
        public static void main(String[] args) 
        {
            java.util.Scanner input = new Scanner(System.in);
            // input 为用来存储输入的值的变量名
            // System.in 配和 Scanner 使用
            System.out.printf("请输入一个数 ： ");
            int x = input.nextInt(); //将用户输入的整形的值给x
            System.out.printf("%d", x); //打印输出x的值
            input.close(); //释放用于输入的内存
        }
    }
    ```
第二种，开开始不导入util包的情况下使用

    ```java
    public class test 
    {
        public static void main(String[] args) 
        {
            java.util.Scanner input = new java.util.Scanner(System.in);
            // input 为用来存储输入的值的变量名
            // System.in 配和 Scanner 使用
            System.out.printf("请输入一个数 ： ");
            int x = input.nextInt(); //将用户输入的整形的值给x
            System.out.printf("%d", x); //打印输出x的值
            input.close(); //释放用于输入的内存
        }
    }
    ```
注意 在使用完输入的语句之后，记得释放输入的内存。防止浪费

前面定义的语句基本是固定写法，除了用来存储输入数据的变量名。

后面用来接收变量数据的写法各种数据都不相同

String next() 读取输入的下一个单词（以空格为分隔符)
int nextInt() 读取下一个int类型数字
double nextDouble() 读取下一个浮点数或者整数（整数会转换为浮点数）
boolean hasNext() 检测输入中是否还有其他单词
boolean hasNextInt() 检测输入中是否有整数
boolean hasNextDouble() 检测是否还有整数或者浮点数
