---
layout: post
title:  "
Sublime Text3 中安装 Emmet"
date:   2016-03-03 
--- 


### 一、下载Sublime Text3，并安装
下载地址[http://www.sublimetext.com/3](http://www.sublimetext.com/3)，安装到某一文件夹。

### 二、安装emmet
1、 打开Sublime Text,使用Control+~或 View > Show Console 进入命令行。

2、 复制以下代码到命令行：

    import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())

3、 敲回车，等待一会儿，重启Sublime Text，菜单栏 Preferences -> Package Control，选择Install Control,再输入emmet，选择之后回车，等待一会儿再次重启即可。

4、 在Sublime Text中输入！，使用Ctrl+E，若自动补全了代码，则安装成功。

