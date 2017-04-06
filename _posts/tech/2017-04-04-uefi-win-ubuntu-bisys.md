---
layout: post
title: UEFI启动的Win10安装Xubuntu16.04双系统
category: 技术
tags: Ubuntu
keywords: Ubuntu, Linux, UEFI
description: 
---

### 知识普及
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


### 安装过程
下面安装过程步骤详细解析。    

#### **第一步：数据备份**    
但凡可能带来抹空磁盘后果或者风险的操作过程，请首先做好数据备份。所以开始之前，务必做好
**数据备份，数据备份，数据备份**。重要的事情说三遍！     

#### **第二步：创建磁盘分区**     
##### **1. `Win+X`，选择`磁盘管理`：**
<center>
![disk-manager](/public/img/tech/bisys/disk_manager.png)
</center>



