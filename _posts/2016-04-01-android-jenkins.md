---
layout: post
title: "Jenkins构建Android项目持续集成之Jenkins的安装篇"
description: "Jenkins构建Android项目持续集成"
category: jenkins
tags: [jenkins]
---
{% include JB/setup %}

## 工具准备
1、jenkins.war
　　可以去官网下载（http://jenkins-ci.org/）最新版本，下载地址：http://mirrors.jenkins-ci.org/war/latest/jenkins.war，如果下载不了，我在csdn上传了一份http://download.csdn.net/detail/a631855639/9335755
2、插件下载
　　这里上传了我所用到的一些插件http://download.csdn.net/detail/a631855639/9335989，有些是必须安装的，有些是可选的，下面会具体说下。
## 启动服务器
　　打开命令行，并定位到jenkins.war文件的目录下，然后执行java –jar jenkins.war(需要事先配置好JAVA开发环境)，看到如下图所示，表示启动成功。
![jenkins启动成功](http://img.blog.csdn.net/20151208103835001)

然后打开浏览器输入http://localhost:8080/，就能进入到jenkins面板界面，如下图
![jenkins面板界面](http://img.blog.csdn.net/20151208104146073)

##插件安装
在上图选择，系统管理—>管理插件—>高级
![插件安装](http://img.blog.csdn.net/20151208110939286)
如上图，将之前下载的插件，上传安装。安装过程可能会碰到如下图所示的安装失败，只要按提示，安装相应的插件即可。
![安装失败提示](http://img.blog.csdn.net/20151208111239877)

1. 必须安装的有：
git(这里使用git作为版本控制)：scm-api.hpi、git-client.hpi、git.hpi
android：port-allocator.hpi、android-emulator.hpi、analysis-core.hpi、android-lint.hpi
gradle(项目是使用Android Studio开发的)：gradle.hpi
2. 可选安装的有：
单元测试：junit.hpi
代码覆盖率：jacoco.hpi
代码查虫：findbugs.hpi
邮箱扩展：email-ext.hpi

最后重启服务器，安装的插件即可生效。

##总结
本篇，简单的讲了工具的下载、jenkins服务器启动及插件的安装。之前，我已经安装了jenkins在使用，但是在写这篇文章的时候，我又重新安装了一边，一边写一边实践一边总结。实践是检验一切真理的唯一标准，也是我们成长的唯一途径。下一篇将写这些插件的如何使用，如何配置，如何与项目相结合。