---
layout: post
title:  "maven学习笔记"
date:   2016-11-25 13:32:01 +0800
categories: 学习笔记
tag: maven
---

* content
{:toc}


## 《Spring Boot实战》中Maven

----------
### maven 的pom.xml

#### 1.dependencies元素

<dependencies></dependencies>,此元素包含多个项目依赖需要使用的<dependency></dependency>

#### 2.dependency元素

<dependency></dependency>内部通过groupId、artifactId以及version 确定唯一的依赖，有人称这三个为坐标。
<br/>groupId:组织的唯一标识
<br/>artifactId:项目的唯一标识
<br/>version:项目的版本
例如
>"<"dependency>
<br/> "<"groupId>org.springframework</groupId>
<br/> "<"artifactId>spring-webmvc</artifactId>
<br/> "<"version>4.1.5.RELEASSE</version>

### 变量定义

变量定义：<properties></properties>可以定义变量在dependency中引用，代码如下：

>"<"properties>
	<br/>"<"spring-framework.version>4.1.5.RELEASSE</spring-framework.version>
<br/>"<"/properties>

>"<"dependency>
<br/> "<"groupId>org.springframework</groupId>
<br/> "<"artifactId>spring-webmvc</artifactId>
<br/> "<"version>${spring-framework.version}</version>

### 编译插件

Maven提供了编译插件，可在编译插件中涉及Java的编译级别，代码如下。

>"<"build>
<br/> "<"plugins>
<br/> "<"groupId>org.apache.maven.plugins</groupId>
<br/> "<"artifactId>maven-compiler-plugin</artifactId>
<br/> "<"version>2.3.2</version>
<br/> "<"configuration>
<br/> "<"source>1.7</source>
<br/> "<"target>1.7</target>
<br/> "<"/configuration>
<br/> "<"/plugins>
<br/> "<"/build>
 
### Maven中心库没有需要的JAR处理
如安装Oracle驱动到本地库：
>mvn install:install-file -DgroupId=com.oracle "-DartifactId=ojdbc14" 
<br/>"-Dversion=10.2.0.2.0" "-Dpackaging=jar" "-Dfile=D:\ojdbc14.jar"
 
 
 
 
 
 
 

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help