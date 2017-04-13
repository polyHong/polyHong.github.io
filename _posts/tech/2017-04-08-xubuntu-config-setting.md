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

##### **2. 其他小技巧**

- 让字体更清晰
    1. `$ xfce4-appearance-settings`
    2. 点击`Font`-->(勾选)Enable anti-aliasing --> Hinting; `Full`, Sub-pixel order; `RGB`(依个人喜好)
- 避免视窗移动到边缘时切换下一个workspace
    1. `$ xfwm4-settings`
    2. 点击Advanced --> Wrap workspaces when reaching the screen edge: (取消勾选) With a dragged window
- 将Panel移动到屏幕最上方或最下方
    1. 滑鼠游标指到Panel空白处按右键，点选Panel --> Panel Preferences
    2. 取消勾选Lock Panel
    3. 滑鼠游标移至Panel最左边按住左键不放，将Panel拖拽到屏幕最上方或最下方
    4. 勾选Lock Panel固定Panel位置
- 改用Whisker Menu
    1. `$ sudo apt-get install xfce4-whiskermenu-plugin`
    2. 于Panel空白处按右键，点选Panel --> Panel Preferences --> Items
    3. 移除Applications Menu，加入Whisker Menu
- 取消所有Panel空出完整桌面
    1. `$ pkill xfce4-panel`
    2. `$ xfce4-session-logout`
    3. 勾选“Save session for future logins”然后登出/重新启动/开机
    4. 随时可按Alt+F2或Alt+F3呼叫App Finder





