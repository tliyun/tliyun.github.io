---
layout: post
title:  "Sublime Text3 中安装 Emmet"
date:   2016-03-03 
--- 

>最近在开始学习前端，目前使用的开发工具是Sublime Text3，这个工具中可以使用很多插件，使我们的前端开发更加高效便捷。这篇文章简单将介绍一下Emmet插件的安装，Emmet插件使用一句指令就能迅速生成了一大片 HTML 代码。

#### 一、下载Sublime Text3，并安装
下载地址[http://www.sublimetext.com/3](http://www.sublimetext.com/3)，安装到某一文件夹。

#### 二、安装emmet
1、 打开Sublime Text,使用Control+~或 View > Show Console 进入命令行。  
2、 复制以下代码到命令行：

   >import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())

3、 敲回车，等待一会儿，重启Sublime Text，菜单栏 Preferences -> Package Control，选择Install Control,再输入emmet，选择之后回车，等待一会儿即可。  
4、 在Sublime Text中输入！，使用Ctrl+E，若自动补全了代码，则安装成功。

