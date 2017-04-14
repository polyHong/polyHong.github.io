---
layout: post
title: Xubuntu下TexLive，Matlab和f.lux的安装
category: 技术
tags: [Ubuntu,LaTex,TexLive,Matlab]
keywords: Ubuntu, Linux
description: 
---

为方便将来查阅，记录下Ubuntu里TexLive和Matlab这两个软件的安装过程。

#### **1. TexLive的在线安装**
最新的安装包已经在Ubuntu 16.10的官方仓库中。    
**1) 打开终端(`Ctrl+Alt+T`)，运行如下命令添加PPA：**    

```shell
$ sudo add-apt-repository ppa:jonathonf/texlive
```

**2) 升级软件源并安装：**    

```shell
$ sudo apt-get update
$ sudo apt-get install texlive-full
```

你可能也想安装一个文本编辑器，比如Kile, Texmaker, JLatexEditor等。

```shell
$ sudo apt-get update
$ sudo apt-get install texworks
```


#### **2. Matlab 2016a的光盘安装**

##### **1) 下载Matlab**    

首先自然需要下载一个Linux版本的Matlab及其破解文件，Matlab2016a大概10GB左右。


##### **2) 挂载ISO文件**    

在终端执行以下命令，会将ISO文件挂载到Ubuntu，出现图形界面开始安装。

```shell
$ sudo mkdir /media/matlab   #也可以直接挂在到/tmp，这个取决于个人偏好
$ sudo mount -o loop [path]Matlab2016a.iso /media/matlab
$ cd /media/matlab
$ sudo ./install
```

##### **3) 注册选项**   
安装过程会出现注册激活的选项，选择“install manually without using the internet”，
序列号在Crack目录下的Readme.txt里。相应地还要选择Crack目录下.lic文件作为license。
这一步和Windows下的安装没有区别。


##### **4) 激活破解**    
进入Matlab安装目录下的bin目录并新建子目录licenses：    

```shell
$ cd [安装目录]/R2016a/bin
$ sudo mkdir licenses
$ sudo chmod 777  licenses
```
将破解文件Crack目录下的     

- Matlab_R2016a_glnxa64.lic   
- libmwservices.so    
- libcufft.so.7.5.18    

分别拷贝至上述新建的目录"licenses"和"./bin/glnxa64"下面:    

```shell
$ sudo cp Matlab_r2016a_glnxa64.lic [安装目录]/R2016a/bin/licenses
$ sudo cp libmwservices.so [安装目录]/R2016a/bin/glnxa64
$ sudo cp libcufft.so.7.5.18 [安装目录]/R2016a/bin/glnxa64
```

##### **5) 快捷方式**     
安装Matlab支持包:    

```shell
$ sudo apt-get install matlab-support
```

至此，Matlab安装工作就完成了。可以进入安装目录下的bin目录终端尝试键入
`./matlab`或`sudo ./matlab`.


##### **6) 可能的问题及解决办法**     
按照上面的步骤安装完Matlab，最后Matlab也可能无法正常启动。这可能有两方面的原因，
一方面可能是权限的问题，这个问题解决起来相对比较简单，只要赋予相应目录足够权限即可。
另一方面可能是安装文件里的一个库文件冲突。解决办法是将安装目录下的文件名修改一下。
即：将"[安装目录]/R2016a/sys/os/glnxa64/libstdc++.so.6"改为"[安装目录]/R2016a/sys/os/glnxa64/libstdc++.so.6.old".
命令为：    

```shell
$ sudo mv [安装目录]/R2016a/sys/os/glnxa64/libstdc++.so.6 [安装目录]/R2016a/sys/os/glnxa64/libstdc++.so.6.old
```

当然如果前5步完成以后，Matlab可以正常启动，那么第6步自然就是多余的了。

#### **3. f.lux indicator的安装**
f.lux是一个可以过滤电脑屏幕蓝光的软件。自动同步时间，根据时间不同，自动调整
屏幕的蓝光输出量，保护眼睛。


##### **1) Ubuntu/Debian手动安装：**

```shell
# Install dependencies
$ sudo apt-get install git python-appindicator python-xdg python-pexpect python-gconf python-gtk2 python-glade2 libxxf86vm1

# Download xflux-gui
$ cd /tmp
$ git clone "https://github.com/xflux-gui/xflux-gui.git"
$ cd xflux-gui
$ python download-xflux.py

# EITHER install globally
$ sudo python setup.py install
# EXCLUSIVE OR, install in your home directory. The binary installs
# into ~/.local/bin, so be sure to add that to you PATH if installing locally.
$ python setup.py install --user

# Run flux
fluxgui
```

##### **2) Ubuntu/Debian手动卸载：**
如果flux是手动安装的话，可以通过`setup.py`来卸载。该文件可以给出安装文件的位置，
这是我们只需要删除所有安装文件即可。     

```shell
# EITHER uninstall globally
$ sudo python setup.py install --record installed.txt
$ sudo xargs rm -vr < installed.txt

# EXCLUSIVE OR uinstall in your home directory
$ python setup.oy install --user --record installed.txt
$ xargs rm -vr < installed.txt
```

