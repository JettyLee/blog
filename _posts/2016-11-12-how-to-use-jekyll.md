---
layout: post
title:  "使用Jekyll构建博客并使用!"
date:   2016-11-12 11:13:01 +0800
categories: jekyll
tag: jekyll
---

* content
{:toc}


1.到jekyll模板网站下载自己喜欢的模板
		<a href="http://jekyllthemes.org/" >http://jekyllthemes.org</a>
<br/>
2.在github上创建repository
<br/>
3.利用<b>git</b>命令在下载好的文件夹完成博客初始化
		
		//git初始化
		$ git init
		
		//创建一个没有父节点的分支gh-pages。因为github规定，只有该分支中的页面，才会生成网页文件
		$ git checkout --orphan gh-pages
		
		//所有内容加入本地git库
		$ git add .
　　	$ git commit -m "first post"

		//username是github上的username repository是你刚创建的repository
　		$ git remote add origin https://github.com/username/repository.git
　　	
		//提交到固定分支
		$ git push origin gh-pages

<br/>
4.编写属于你的文章
在/_posts目录下新建一个文件，可以创建文件夹并在文件夹中添加文件，方便维护。
在新建文件中粘贴如下信息，并修改以下的titile,date,categories,tag的相关信息，添加* content {:toc}为目录相关信息，在进行正文书写前需要在目录和正文之间输入至少2行空行。
然后按照正常的Markdown语法书写正文。
<br/>
---
layout: post
#标题配置
title:  标题
#时间配置
date:   2016-08-27 01:08:00 +0800
#大类配置
categories: document
#小类配置
tag: 教程
---

* content
{:toc}


我是正文。我是正文。我是正文。我是正文。我是正文。我是正文。
<br/>
5.更新文件时需要的<b>git</b> 命令 

		$ git add .
		
		$ git commit -m "message"  注：message 写提交的提示信息
		
		$ git pull origin gh-pages //更新版本
		
		$ git push origin gh-pages //提交版本
		
		输入账号
		输入密码
		
		即可实现文件更新上传




[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
