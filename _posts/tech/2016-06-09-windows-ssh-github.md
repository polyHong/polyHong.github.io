---
layout: post
title: Windows下配置SSH连接GitHub
category: 技术
tags: github
keywords: SSH, GitHub
description: 
---

本文可分为两部分：  
>第一部分：在windows下通过Git for windows配置SSH Keys连接GitHub;  
>第二部分：在GitHub上创建仓库，在本地创建项目，然后将本地项目通过SSH提交到GitHub仓库中。

# Git for windows配置SSH访问GitHub
***
## 检查本机是否有ssh key设置
`$ cd ~/.ssh` 或 `cd .ssh`  
如果没有则提示： 
>No such file or directory

如果有则进入~/.ssh路径下(ls查看当前路径文件, rm *删除所有文件)  

## 使用Git Bash生成新的ssh key.  
`$ cd ~   #保证当前路径在"~"下`











