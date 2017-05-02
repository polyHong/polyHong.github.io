---
layout: post
title: Xubuntu 16.04安装和卸载搜狗拼音输入法
category: 技术
tags: Ubuntu
keywords: Ubuntu, Linux, xfce4
description: 
---


#### **一、安装搜狗拼音输入法**   

##### **1. 添加`fcitx`的PPA**   
代码如下:   

```shell
sudo add-apt-repository ppa:fcitx-team/nightly
```


##### **2. 刷新软件源, 安装依赖软件**
刷新软件源代码如下:    

```shell
sudo apt-get update
```

刷新完成之后, 安装`im-config`:     

```shell
sudo apt-get install im-config
```

继续安装搜狗输入法依赖的`fcitx`一系列文件, 命令如下:    

```shell
sudo apt-get -f install
```

##### **3. 下载并安装搜狗输入法**

- 到搜狗官网下载搜狗拼音输入法, 选择系统对应的软件包下载.   
- 下载完成后, 进入安装包文件所在目录, 用如下命令进行安装:   

```shell
sudo dpkg -i sogoupinyin_2.1.0086_amd64.deb
```

**注意:**文件名根据下载的安装包而定, 可使用`Tab`键自动补全.  

- 安装完成后, 使用如下命令启用搜狗输入法, 完成之后重启系统, 即可点击输入汉字.   

```shell
sudo im-config -s fcitx -z default
```



#### **二、卸载搜狗拼音输入法**  

##### **1. 首先使用如下命令查看安装的搜狗拼音输入法**   

```shell
sudo dpkg -l so*
```

然后先卸载搜狗拼音输入法:   

```shell
sudo apt-get purge sogoupinyin
```

##### **2. 卸载`fcitx`**    

```shell
sudo apt-get purge fcitx
```


##### **3. 彻底卸载`fcitx`及其相关配置**    

```shell
sudo apt-get autoremove
```


##### **4. 最后注销或者重启系统, 如果注销按钮不能使用, 可以使用命令**   

```shell
sudo pkill Xorg
```

再次登录系统, 可以看到搜狗输入法已经被卸载干净.

