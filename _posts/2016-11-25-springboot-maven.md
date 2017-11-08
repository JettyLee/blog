---
layout: post
title:  "学习笔记之Maven"
date:   2016-11-25 13:32:01 +0800
categories: 学习笔记
tag: Maven
---

* content
{:toc}


# 《Spring Boot实战》

## Maven

----------

### maven 的pom.xml

#### 1.dependencies元素
```bash
<dependencies></dependencies>
上面元素包含多个项目依赖需要使用的<dependency></dependency>
```
#### 2.dependency元素
```bash
<dependency>内部通过groupId、artifactId以及version 确定唯一的依赖，有人称这三个为坐标</dependency>
        <groupId>groupId:组织的唯一标识</groupId>
        <artifactId>项目的唯一标识</artifactId>
        <version>项目的版本</version>
</dependency>

<dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-webmvc</artifactId>
        <version>4.1.5.RELEASSE</version>
</dependency>
```
### 变量定义
>变量定义：<properties></properties>可以定义变量在dependency中引用，代码如下：
```bash
<properties>
    <spring-framework.version>4.1.5.RELEASSE</spring-framework.version>
</properties>

<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-webmvc</artifactId>
    <version>${spring-framework.version}</version>
</dependency>
```
### 编译插件

>Maven提供了编译插件，可在编译插件中涉及Java的编译级别，代码如下。

```bash
<build>
    <plugins>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>2.3.2</version>
        <configuration>
            <source>1.7</source>
            <target>1.7</target>
        </configuration>
    </plugins>
</build>
```
 
### Maven中心库没有需要的JAR处理

>如安装Oracle驱动到本地库：

```bash
>mvn install:install-file -DgroupId=com.oracle  -DartifactId=ojdbc14 -Dversion=10.2.0.2.0 -Dpackaging=jar  -Dfile=D:\ojdbc14.jar
```
 
 
 
 
 
 

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help