---
layout: post
title:  "win10搭建docker环境"
date:   2017-03-12 21:14:01 +0800
categories: 环境搭建
tag: docker
---

* content
{:toc}
##### 1.确认WIN10系统开启Hyper-V,如何开启<a href="http://jingyan.baidu.com/article/86fae346c9311e3c49121aa9.html">看这里</a>

------

##### 2.下载安装docker(ps:我安装的stable版) <a href="https://www.docker.com/community-edition#/download">点这里</a>
#####  验证安装  cmd  docker info
##### 3.下载安装docker-toolbox(ps:主要想要用kitematic可视化管理docker) <a href="https://www.docker.com/products/docker-toolbox">点这里</a>
依次安装就可以用了
##### 启动一个nginx容器
>docker run -d -p 81:80 --name webserver nginx	
<br/>
>浏览器地址框，输入http://localhost:81/ 即可验证

ps: 唉，这么简单，我电脑重装了5次-------------------旧书害人

​	

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
