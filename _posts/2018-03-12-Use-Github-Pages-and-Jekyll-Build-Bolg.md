﻿tags:Github_Pages, Jekyll, Blog

Also published in https://soandcandy.us
CC 4.0 BY-SA
----

## 利用Github Pages和Jekyll搭建个人博客 ##

* TOC
{:toc}

### Git & Github ###

Git是一种分布式版本控制系统，由Linux操作系统创建人Linus 编写，当时是用来管理Linux内核的源码。

Github是全球知名的使用Git系统的一个免费远程仓库（Repository），倡导开源理念，若要将自己的代码仓库私有则需付费。

而Github Pages是Github提供给托管项目的开发者一个更个性化展示自己项目的方法，使用GitHub Pages服务可以编写同样是托管在Github上的静态网页。

我们就是利用Github Pages服务来搭建自己的博客。

### Jekyll ###
Jekyll则是为了方便我们调试、预览博客效果的本地环境。

### 搭建过程 ###

#### 注册Github ####

这一部分不需要详细说明了。先注册[Github](https://github.com)，开启一个新的Repository，取名和你的用户名一致，如`你的用户名.github.io`，只有这样，Github才会给你的repository以jekyll结构建立模板。

在设定处，可以选择模板。

在[Jekyll的wiki项目](https://github.com/jekyll/jekyll/wiki/sites)有很多参考模板。你可以查看源码，FORK一份，直接改成自己的用户名来使用。

当然，涉及很多项目都要相应修改。需要仔细阅读每个文档。

##### 开启博客 #####

你也可以先发表一个test文章，使你的博客生效，公布出来。你就可以通过`https://你的用户名.github.io`访问了。

如果你有独立域名，也可以绑定上述地址，具体自行咨询管理商或者Google吧。

现在，你的博客就已经搭建起来。

#### Git clone 本地化####

使用Windows系统的同学就直接使用Github Desktop来管理吧，十分方便。在Windows下还用`Git CMD`就真的无法言说了，何必呢？

简单说说Linux下（以Ubuntu为例）如何管理博客。

其实原理很简单。就是把repository克隆到本地，在本地写作、修改，再推送差异部分到线上。而调试部分，我们使用了jekyll来预览。

1. 安装Ruby；
    ```
    sudo apt-get install ruby-full ruby-bundler
    ruby -v #查看ruby版本
    ```
    
2. 安装Jekyll；
    ```
    sudo gem install jekyll 
    gem install jekyll-paginate #可能也要sudo
    jekyll -v #查看版本
    ```
    
3. 搭建博客
    如果前面只是开启了博客，未published，这里可以Jekyll新建网站：
    ```
    jekyll new mySite
    ```
    
4. Git Clone博客
    ```
    git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
    ```
    
    当然，SSH方式是最快捷的。先建SSH密钥：`ssh-keygen -t rsa -C"{name@site.com}"`，引号间换成你的内容。生成了私钥**id_rsa**和公钥**id_rsa.pub**，然后到[Github.com](https://github.com)设定SSH密钥，把**id_rsa.pub**的内容全部粘贴到Github上。
    
    ```
    git clone git@github.com:你的用户名/你的仓库名.git
    ```
    
5. 本地写作
    文章在_posts文件夹内。文件名必须按照规范：年-月-日-单词-单词-单词.后缀。

6. 预览
前面我们安装了jekyll就可以进行预览了。进入克隆回来的仓库文件夹，运行`jekyll serve`即可在127.0.0.1:4000浏览器内预览。

7. 推送线上
使用以下命令：
    ```
    git add .       #注意这个点
    git commit -m "你要说的话"
    git push origin master
    ```
    
8. 收工

