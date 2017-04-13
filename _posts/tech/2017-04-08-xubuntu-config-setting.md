---
layout: post
title: Xubuntu使用配置 
category: 技术
tags: Ubuntu
keywords: Ubuntu, Linux, xfce4
description: 
---

上一篇文章详述了Thinkpad中Win10和Xubuntu双系统的安装过程。安装完Xubuntu，接下来自然是
用它来完成日常工作。然而Xubuntu只是Xfce4桌面和Ubuntu内核的组合，很多工作中需要的工具
默认都是没有安装的。为了能更顺手和舒服地使用Xubuntu，我们还需要对它做一些必要的配置。

#### **一、Xfce桌面调校**   

##### **1. 安装并套用Numix布景主题**   

```shell
$ sudo add-apt-repository ppa:numix/ppa
$ sudo apt-get update
$ sudo apt-get install numix-gtk-theme
$ xfconf-query -c xsettings -p /Net/ThemeName -s "Numix Daily"
$ xfconf-query -c xfwm4 -p /general/theme -s "Numix Daily"
```





