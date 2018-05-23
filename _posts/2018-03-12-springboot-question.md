---
layout: post
title:  "学习SpringBoot总结"
date:   2018-03-12 16:24:01 +0800
categories: 学习笔记
tag: SpringBoot
---

* content
{:toc}


>SpringBoot2新鲜出炉，重新整合一遍SpringBoot，准备开始熟悉各种特性

##### 1.开始动手
>从<a herf="http://start.spring.io">http://start.spring.io</a> &nbsp;&nbsp; 入手开始，如下图所示。添加了一个web 属性，点击下载。用idea打开、导入、运行。

<img src="../../../../styles/images/springboot-lean/springboot-start.png" />

##### 2.由于经常接触web项目，所以新建一个Controller 测试
``` bash
package cn.jettylee.springboot.demo.controller.api;

import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class TestController {

    @RequestMapping("hello")
    public String hello(){
        return "hello";
    }
}
```


[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
