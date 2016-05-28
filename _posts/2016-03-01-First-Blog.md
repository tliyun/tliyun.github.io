---
layout: post
title:  "使用Jekyll+GitHub Page搭建博客!"
date:   2016-03-01
---


> 早就想搭建自己的博客，但一直都没去做，这几天在朋友的建议和帮助之下，尝试了使用Jekyll和GitHub Page搭建博客，本来以为网上都有教程做起来会比较容易，但是自己真正动手才发现看到的教程都不太完整，也遇到了很多问题。搭建完成之后也就想着把自己的经验发出来，希望这篇文章对想使用此工具搭建博客的人有帮助。

### 一、注册GitHub，并搭建Page
* 打开[https://github.com/](https://github.com/)，注册一个Github账号，设置一个自己喜欢的用户名。
* 注册需要验证邮箱，完成之后点击+New repository创建一个仓库，仓库名为username.github.io（这里的username是账号的用户名）。
* 创建好之后，点击settings，再点击Launch automatic page generator生成页面，编辑好内容，点击continue to layouts,选择一个自己喜欢的模板，点击Publish page发布页面。
* 接下来就可以在使用username.github.io访问自己的域名了，在浏览器中输入username.github.io即可访问自己的页面。

### 二、安装本地Git
* 打开[http://http://git-scm.com/download/](http://http://git-scm.com/download/)，选择对应的版本进行下载。
* 参考[http://jingyan.baidu.com/article/90895e0fb3495f64ed6b0b50.html](http://jingyan.baidu.com/article/90895e0fb3495f64ed6b0b50.html)进行安装。
 
### 三、安装本地GitHub
* 在浏览器中搜索github for windows,打开github网站，下载安装包。
* 参考[http://jingyan.baidu.com/article/6b97984d9bd6ed1ca2b0bf07.html](http://jingyan.baidu.com/article/6b97984d9bd6ed1ca2b0bf07.html)进行安装。
* 安装之后，在git bash或者cmd中输入git --version，如果能正确打印出git版本信息，则说明安装成功。
 
### 四、安装Jekyll
* 安装Ruby。打开[http://rubyinstaller.org/downloads/](http://rubyinstaller.org/downloads/)，下载对应的版本。点击安装，记住在选择安装路径之后，勾上下面的第二项“Add Ruby executables to your PATH。安装完成后，若cmd输入ruby -v和gem -v能正确打印版本信息，则说明安装成功。
* 安装Ruby DevKit。打开[http://rubyinstaller.org/downloads/](http://rubyinstaller.org/downloads/)，下载对应的版本。点击下载的exe程序，解压到一个目录，例如D:\DevKit。打开D:\DevKit目录，在最上面的路径栏中输入cmd，打开之后执行ruby dk.rb init命令。在执行执行ruby dk.rb install命令。
* 安装Jekyll。在cmd输入gem install jekyll，执行之后如果没报错则正常安装了。
* 以上步骤可参考[http://blog.sina.com.cn/s/blog_6c969b4a0102vo55.html](http://blog.sina.com.cn/s/blog_6c969b4a0102vo55.html)。

### 五、安装MarkDown编辑器

* MarkDown工具可根据个人习惯选择，我使用的是MarkdownPad，下载地址[http://markdownpad.com/](http://markdownpad.com/)，安装完即可编写博客。
* MarkDown教程可参考[http://sspai.com/25137](http://sspai.com/25137)。
 
### 六、发布博客

* 完成了以上的操作之后，我们可以使用MarkDown写一篇简单的博客并发布，其操作流程如下：
* 自己选定一个工作目录，在最上面的路径栏中输入cmd，打开之后输入命令jekyll new name（name自己确定），会发现该目录中生成了一个name文件夹，输入命令cd name进入，输入ls可以看到里面包含若干文件。这里先介绍一下jekyll的目录结构：

    1、 文件夹_layouts：用于存放模板的文件夹。

    2、 文件夹_posts：用于存放博客文章的文件夹。

    3、 文件夹css：存放博客所用css的文件夹,比如主题文件以及高亮文件都是放在此处的。

    4、 .gitignore：可以删掉，后面会将项目添加到git项目，所以这个不需要了。

    5、 _coinfig.yml：jekyll的配置文件，里面可以定义相当多的配置参数，具体配置参数可以参照其官网。

    6、 index.html：项目的首页。

    7、 _includes:用于存放一些固定的HTML代码段，文件为.html格式，可以在模板中通过liquid标签引入，常用来在各个模板中复用如 导航条、标签栏、侧边栏之类的在每个页面上都一样不变的内容，需要注意的是，这个代码段也可以是未被编译的，也就是说也可以使用liquid标签放在这些代码段中。

    通过修改配置文件_coinfig.yml以及post和layouts就可以实现主要blog的建立和修改。

* 再继续在命令提示符窗口中输入jekyll build，回车之后再输入jekyll serve，没有出错的话，现在可以在浏览器中输入[http://localhost:4000](http://localhost:4000)进行本地预览了。

* 接下来通过github将本地库的改动提交到网上。

   按Ctrl+c退出，按照以下部署命令进行：

   >git init  //创建新的git库
   
   >git add .
  
   >git commit -m "initial commit"  
    //提交所有的修改到本地的git仓库，双引号中写自己的注释
    
   >git remote add origin https://github.com/username/username.github.io.git  
    //username使用自己的用户名

   >git push -u origin master  
    //上传到github的master分支中，需要输入用户名和密码，若github中已经存在内容则会产生冲突

  进入HelloBlog/_posts目录下，手动创建新的markdown文件，其命名格式为在文件开头复制如下代码：

   1、 ---  

   2、 layout: post  

   3、 title:  "这里填写文章标题"  

   4、 date:   2016-03-01 11:43:12 +0800  

   5、 ---  
    //1和5都是三条短划线，保留


* 文件编辑完成之后，执行如下命令完成部署

  依次输入：

   >git add .

   >git commit -m "new blog"

   >git push

* 在浏览器中输入username.github.io就可以访问到自己的博客了
