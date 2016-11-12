---
layout: post
title:  "How to use Jekyll!"
date:   2016-11-12 11:13:01 +0800
categories: jekyll
tag: jekyll
---

* content
{:toc}


构建jekyll博客
1.到jekyll模板网站下载自己喜欢的模板
		http://jekyllthemes.org/
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
4.更新文件时需要的<b>git</b> 命令 

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
