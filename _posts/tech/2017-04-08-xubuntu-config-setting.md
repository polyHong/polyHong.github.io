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


#### **二、解决Ubuntu与Windows双系统时间不同步**  

##### 为什么Ubuntu和Windows双系统会有时间差
之所以Windows与Ubuntu双系统之间有时间差，是因为这两个系统使用了不同的
方式来识别硬件时钟（Hardware Clock）。Ubuntu 将硬件时钟当作 UTC 时间，而
Windows将硬件时钟当作本地时间（Local time）。由于时间的处理方式不同，
Windows不管重启多少次都识别Local time，时间都不会改变。而当我们从
Ubuntu重启到Windows时，硬件时钟已经被Ubuntu认为UTC方式，而Windows
再将其强制转换成Local time，这就造成了时间差。

##### 如何解决Ubuntu和Windows双系统时间不同步(以下办法选其一)

1. 在Ubuntu中解决
    - Ubuntu 16.04+  
```
$ timedatectl set-local-rtc 1
```
    - Ubuntu 15.10及更早版本，将`/etc/default/rcS`文件中的`UTC=yes`改为`UTC=no`   
```
$ sudo sed -i 's/UTC=yes/UTC=no' /etc/default/rcS
```
    - 以上是在Ubuntu系统中操作，还可以在Windows中更改相关设置
2. 在Windows中解决
    - 下载[windowstimefixutc.reg](http://www.linuxandubuntu.com/uploads/2/1/1/5/21152474/windowstimefixutc.reg)
    - 管理员身份运行命令行工具  

```
sc config w32time start=disabled
```

#### **三、Fcitx拼音输入法**  
- **Fcitx**: 它是Linux世界开源的输入法框架，提供Google PinYin、
ShuangPin、SunPinYin、Wubi、ZhengMa、Hong Kong和TaiWan繁体等输入法。
- **搜狗拼音**：搜狗出品面向Linux的输入法。

##### **安装Fcitx：**

```shell
$ sudo apt-get install fcitx fcitx-googlepinyin fcitx-table-wbpy fcitx-pinyin fcitx-sunpinyin
```

##### **在语言设置里选择Fcitx：**
<center>
![language-support](/public/img/tech/xconfig/language_support.png)
</center>

##### **重启系统；配置Fcitx：**
<center>
![language-support](/public/img/tech/xconfig/fcitx_config.png)
</center>

##### **Ctrl+空格**或**Ctrl+Shift**切换输入法
<center>
![language-support](/public/img/tech/xconfig/input_method_shift.png)
</center>

<center>
![language-support](/public/img/tech/xconfig/input_method_test1.png)
</center>

<center>
![language-support](/public/img/tech/xconfig/input_method_test2.png)
</center>

#### **四、安装Windows字体**

##### **1. Ubuntu 16.04安装Windows字体**
安装ttf-mscorefonts-installer    

```shell
$ sudo apt-get update
$ sudo apt-get install ttf-mscorefonts-installer
```
接受协议，开始安装：
<center>
![language-support](/public/img/tech/xconfig/ttf_mscorefonts_installer.png)
</center>

<center>
![language-support](/public/img/tech/xconfig/ttf_mscorefonts_installer2.png)
</center>
注：用Tab键来选择。    


更新字体缓存：     

```shell
$ sudo fc-cache -f -v
```

##### **2. 另一种方法**
拷贝已有Windows系统字体。

在Linux创建一个目录用来存放Windows字体：    

```shell
$ sudo mkdir /usr/share/fonts/WindowsFonts
```
Windows的字体文件目录位于C盘的`Windows/Fonts`，把字体文件拷贝到
`/usr/share/fonts/WindowsFonts`目录。

更改字体文件的权限：     

```shell
$ sudo chmod 755 /usr/share/fonts/WindowsFonts/*
```

更新字体缓存：     

```shell
$ sudo fc-cache
```


##### **测试**
打开LibreOffice，查看字体：
<center>
![language-support](/public/img/tech/xconfig/win_fonts_test_lib_office.png)
</center>









