---
layout: post
title:  "北京石基昆仑大连研发部-面试总结"
date:   2017-03-22 22:31:01 +0800
categories: 面试
tag: 北京石基昆仑大连研发部
---

* content
{:toc}



通知的1点面试，结果记成了3点，很尴尬。
去了我选了一套java面试题。
#####	选择6道：

###### 抽象类

``` bash
A.子类若没有实现抽象方法，则为抽象类，若实现抽象方法则为常规类
B.抽象类中可以存在非抽象方法
C.abstract 不能修饰构造器
D.abstract 和 final不能同时使用
```

###### 字符串比较

```
String string="123";
String string2="12"+"3";
String string3=new String("123");
String string4=new String("12")+new String("3");
System.out.println(string == string2);//true
System.out.println(string == string3);//false
System.out.println(string == string4);//false
System.out.println(string.equals(string2));//true
System.out.println(string.equals(string3));//true
System.out.println(string.equals(string4));//true
System.out.println(string2 == string3);//false
System.out.println(string2 == string4);//false
System.out.println(string2.equals(string3));//true
System.out.println(string2.equals(string4));//true
System.out.println(string3 == string4);//false
System.out.println(string3.equals(string4));//true
```
			

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
