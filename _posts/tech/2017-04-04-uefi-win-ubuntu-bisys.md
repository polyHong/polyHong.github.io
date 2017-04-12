---
layout: post
title: UEFI启动的Win10安装Xubuntu16.04双系统
category: 技术
tags: Ubuntu
keywords: Ubuntu, Linux, UEFI
description: 
---

### **知识普及**
因为硬件发展迅速，传统式(Legacy)BIOS成为进步的包袱，现在已发展出最新的UEFI(Unified
Extensible Firmware Interface)可扩展固件接口，对于第三方的开发，前者基本上做不到，除非
参与BIOS的设计，但是还要收到ROM的大小限制，而后者就便利多了。相比传统的BIOS来说，未来
将是一个"没有特定BIOS"的电脑时代。用的是UEFI引导。         

#### GRUB
GNU GRUB (GRand Unified Bootloader简称``GRUB'')是一个来自GNU项目的多操作系统启动
程序。GRUB是多启动规范的实现，它允许用户可以在计算机内同时拥有多个操作系统，并在
计算机启动时选择希望运行的操作系统。GRUB可用于选择操作系统分区上的不同内核，也可
用于向这些内核传递启动参数。         

#### UEFI
新型UEFI，全程"统一的可扩展固件接口" (Unified Extensible Firmware Interface), 是
一种所谓的"固件"，负责在开机时做硬件启动和检测等工作，并且担任操作系统控制硬件时
的中介角色。         

#### Xubuntu
Xubuntu(发音为ZOO-bun-too)是一个Ubuntu Linux的官方派生版，它基于桌面环境Xfce. Xubuntu
主要面向就是电脑的用户和追求更快捷的桌面环境的用户。它主要基于GTK+的程序。Ubuntu使用
Unity桌面环境。Xubuntu使用适于旧式计算机的Xfce桌面环境(占用更少的系统资源)。Xubuntu使用
和Ubuntu相同的更新源，能够使用绝大部分Ubuntu下的软件(仅有用户界面的细微差别)。      


### **安装过程**
下面安装过程步骤详细解析。    

#### **第一步：数据备份**    
但凡可能带来抹空磁盘后果或者风险的操作过程，请首先做好数据备份。所以开始之前，务必做好
**数据备份，数据备份，数据备份**。重要的事情说三遍！     

#### **第二步：创建磁盘分区**     
##### **1. `Win+X`，选择`磁盘管理`：**
<center>
![disk-manager](/public/img/tech/bisys/disk_manager.png)
</center>


#### **2. 选择待压缩磁盘和空间：**
选择剩余空间较大的可分磁盘，右键并选择`压缩卷`，磁盘空间大小的选择视实际
情况而定，我分出了120G左右的空间。
<center>
![disk-split-1](/public/img/tech/bisys/disk_split_space1.png)
</center>


#### **3. 分出Ubuntu安装的磁盘空间：**
点击“压缩”之后，磁盘尾部会出现黑色的120G“未分配空间”。
<center>
![disk-split-2](/public/img/tech/bisys/disk_split_space2.png)
</center>

到这里，磁盘分区过程完成。     


### **第三步：制作Xubuntu的启动U盘**    
#### **1. 备份待写入的U盘**     

#### **2. 进入UltraISO，打开文件：**
<center>
![ultriso-gui](/public/img/tech/bisys/ultrISO_gui.png)
</center>


#### **3. 启动->写入硬盘映像：**
<center>
![ultraiso-write](/public/img/tech/bisys/ultraISO_write.png)
</center>


#### **4. 按默认值写入：**
<center>
![ultraISO-default-para](/public/img/tech/bisys/ultraISO_default_para.png)
</center>


#### **5. 完成写入：**
<center>
![ultraiso-finished](/public/img/tech/bisys/ultraISO_finished.png)
</center>


### **第四步：设置Bios**  
重新启动机器，进入到BIOS SETUP后(大多数笔记本是按F12, F11, F10或者F2，不同品牌的
电脑会稍微有些区别，可以多试几次)。关闭secure boot, secure boot一定要关闭。
设置设置USB启动为首选启动项，制作好的U盘是支持UEFI引导的。最后保存并退出。   
<center>
![secure-boot-1](/public/img/tech/bisys/secure_boot_close1.jpg)
</center>

<center>
![secure-boot-1](/public/img/tech/bisys/secure_boot_close2.jpg)
</center>


### **第五步：从U盘安装Xubuntu**
到此，万事俱备，只欠最后的“东风”了。插上U盘，根据机器找到进入Boot的快捷键。
以下图片来自网络，仅用作示意，并非安装XUbuntu的图片。    

#### **1. 找到U盘镜像，选择并启动**
<center>
![boot-from-usb](/public/img/tech/bisys/boot_from_usb.jpg)
</center>

从U盘启动后，进入一个选择界面。第一个选项是进入U盘Linux Live，直接在U盘里面
体验Linux而不安装。第二个选项是安装Linux，第三个忘了。如果选择第二个的话，则
直接进入安装Linux的图形界面。   


我选择第一个选项，进入Linux Live  
<center>
![linux-live](/public/img/tech/bisys/linux_live.jpg)
</center>

点击桌面上的安装Ubuntu，确保安装过程中已经连接上网络，用于安装更新和一些必要
的媒体设备。当然这个步骤也可以待安装完成以后再进行，但是此时进行可以节省安装后
的配置时间。
<center>
![install-ubuntu](/public/img/tech/bisys/install_ubuntu_desktop.jpg)
</center>

选择语言
<center>
![language-choice](/public/img/tech/bisys/language_choice.jpg)
</center>

选择是否安装更新和多媒体软件
<center>
![beginning-install](/public/img/tech/bisys/beginning_install.jpg)
</center>

#### **2. 为空闲磁盘分区**
这步是重点，选择其他选项，自己来创建挂载点(挂载点就是分区的意思).  

在这一步会看到我们之前分配的为使用磁盘空间，我们要为这块空闲磁盘分区，
为了方便理解接下来的操作，我们先来简单介绍一下安装过程涉及到的几个主要
的Linux分区：

- `/`：存储系统文件，建议10GB-15GB;  
- `swap`：交换分区，即Linux系统的虚拟内存，建议是物理内存的2倍；  
- `/home`：home目录，存放、图片及下载等文件的空间，建议最后分配所有剩下的空间；   
- `/boot`：包含系统内核和系统启动所需要的文件，实现双系统的关键所在，建议大一点比如2GB
左右。一开始我分配了200M，后来在更新的过程中总是提示无法完成更新，因为boot空间不够，
后来又重新装了一遍才解决这个问题。
<center>
![other-choice-install](/public/img/tech/bisys/other_choice_install.jpg)
</center>

选定空闲磁盘，点击+，首先分配16G空间给/分区，选择“主分区”、“空间起始位置”、
Ext4和“挂载点/”：
<center>
![add-disk](/public/img/tech/bisys/add_disk_primary.jpg)
</center>

注：实际上，一块硬盘最多容纳4个主分区，或3个主分区外加1个扩展分区，在选择分区类型时，
可能会出现“安装系统时空闲分区不可用”状况，为了解决问题，下面一律选择“逻辑分区”。


重复创建步骤，分配16G空间给swap分区，选择“逻辑分区”(主分区已满)、
“空间起始位置”、用于“交换空间”：
<center>
![add-disk](/public/img/tech/bisys/add_disk_swap.jpg)
</center>

接着分配2GB空间给/boot分区，选择“逻辑分区”(主分区已满)、“空间起始位置”、
“Ext4”和“挂载点/boot”：
<center>
![add-disk](/public/img/tech/bisys/add_disk_boot.jpg)
</center>

最后将所有剩余空间分配给/home分区，选择“逻辑分区”(主分区已满)、“空间起
始位置”、“Ext4”和“挂载点/home”：
<center>
![add-disk](/public/img/tech/bisys/add_disk_home.jpg)
</center>
选择/boot对应的盘符作为“安装启动引导器的设备”，务必保证一致：
<center>
![add-disk](/public/img/tech/bisys/boot_start.jpg)
</center>

将改动写入磁盘，去喝杯咖啡：
<center>
![add-disk](/public/img/tech/bisys/write_to_disk.jpg)
</center>

咖啡喝完，刚好进入最后的设置：
<center>
![add-disk](/public/img/tech/bisys/time_zone_setting.jpg)
</center>

<center>
![add-disk](/public/img/tech/bisys/keyboard_choice.jpg)
</center>

<center>
![add-disk](/public/img/tech/bisys/user_info.jpg)
</center>
填完必要信息，点击“继续”，等待系统安装完成，再重启就大功告成了。

重启的时候会进入grub2引导界面，让你选择Ubuntu还是windows boot management.
