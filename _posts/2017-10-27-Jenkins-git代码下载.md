---
layout:     post
title:      Jenkins构建Git仓库的代码
subtitle:   Jenkins简介
date:       2017-10-27
author:     drawing818
header-img: /img/jenkins.jpg
catalog: true
tags:
    - devops
    - CI
    - CD
    - Git
---

要使用Jenkins对代码进行构建，首先就要把代码从代码仓下载到构建机器上。

常用的代码仓有[SVN](http://subversion.apache.org/)库 和 [Git](https://git-scm.com/)库，代然还有其它类型的仓库！

其实SVN和Git是2种不同的版本控制系统！

由于越来越多的项目组和开发人员逐渐从SVN切换到了Git上面，我们这里就说说Jenkins构建的时候如何从Git仓库下载代码！

由于Jenkins有齐全的插件，当然从git仓库下载代码也会有对应的插件[Git Plugin](https://wiki.jenkins.io/display/JENKINS/Git+Plugin)。

但是当仓库中的代码量比较大的时候，在使用的时候发现插件下载代码就会花费很长的时间，并且有可能会下载失败。

为此，我们可能就需要自己去写脚本，通过执行Git命令去完成代码下载！


