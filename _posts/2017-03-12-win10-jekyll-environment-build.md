---
layout: post
title:  "win10搭建本地jekyll博客环境"
date:   2017-03-12 20:10:01 +0800
categories: jekyll
tag: 环境搭建
---

* content
{:toc}



#### 1.下载并安装rubyinstaller  <a href="http://rubyinstaller.org/downloads/">rubyinstaller </a>（点击后出现下图）
<img src="/styles/images/win10-jekyll-environment-build/1.png"  width="757"    align="center"/>

#### 2.验证ruby 安装是否成功，打开cmd(win+R 输入CMD),打开后输入
```
ruby -v
```
(出现下图则安装成功)
<img src="/styles/images/win10-jekyll-environment-build/2.png"  width="757"    align="center"/>

#### 3.下载DevKit（点击上方rubyinstaller在页面下面即可下载），解压完成后找到文件夹（点击文件夹后，按住shift+右键，选择从此处
打开命令窗口），输入

```
ruby dk .rb init
```
再输入
```
ruby dk .rb install
```
<img src="/styles/images/win10-jekyll-environment-build/3.png"  width="757"    align="center"/>

#### 4.安装jekyll 在当前命令窗口输入命令 
```
gem install jekyll
```

#### 5.验证jekyll安装是否成功，cmd输入命令 
```
jekyll --version
```

##### ps:电脑被我玩坏了，重新配置了一遍环境，就简单的记录了一下…
#### 若git 没有设置username和email ,输入 (引号中是值)进行配置
```
git config --global user.name "username"
git config --global user.email "email"
```



			

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
