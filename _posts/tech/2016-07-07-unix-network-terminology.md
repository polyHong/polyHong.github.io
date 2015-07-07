---
layout: post
title: UNIX/Linux网络术语
category: 技术
tags: UNIX/Linux
keywords: UNIX/Linux network terminology
description: 
---

> 引自网络. ---- Hammer Wang


<center>  
![unix-network-term](/assets/img/tech/UNIX/unix-network-terminology.jpg)
</center>  

## Portmap(端口映射)  

```
sudo apt-get install -y portmap
```  
  
- 端口映射是ONC RPC(Open Network Computing Remote Procedure)软件集合的一部分，用于实现在计算机程序之间的远程过程调用(RPC). 它被广泛应用于NFS(Network File System)和NIS(Network Information Service);  
- 端口映射可以将RPC程序的端口号转换为DARPA协议的端口号，对RPC Call而言，这是必要的  


## NIS(网络信息服务)  
  
```
sudo apt-get install -y nis
```  

- NIS(Network Information Service)提供基于服务器、客户端的目录服务，用于计算机网络上的用户名和主机名构成的分布式系统数据配置. SUN公司开发了NIS协议，并授权给了其他UNIX供应商. NIS负责维护和分发计算机网络中的目录信息，包括用户和组的信息、主机名、邮件地址和其他基于文本的表的信息;  
- NIS曾经被命名为Sun Yellow Pages, 但由于Yellow Page已经被使用了, 所以不得不改名;  
- NIS+在NIS的基础上加强了安全, 增加了层级等特性.  


## AutoFS  

```
sudo apt-get install -y autofs 
```   

- AutoFS在Linux系统上用于控制自动挂载守护进程的操作. 一般而言, AutoFS在系统启动或关闭时被调用, 并辅之以相应的参数. AutoFS通过查询配置文件/etc/auto.master, 确定系统的挂载点.  



## NFS(网络文件系统)  

- NIS(Network File System)最初由Sun公司在1984年开发, 允许客户端通过网络像访问本地文件系统一样访问远程服务器上的文件;  
- NFS像其它协议一些, 构建在ONC RPC基础之上. NFS是一个开放的标准协议, 允许任何人实现. (张志平/编译)