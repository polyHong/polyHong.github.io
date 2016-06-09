layout: post
title: Windows下配置SSH连接GitHub
category: 技术
tags: Blog
keywords: SSH, GitHub
description: 
---



>结合网络经验，记录实际操作过程，方便以后配置新机器。本文可分为两部分：  
>第一部分：在windows下通过Git for windows配置SSH Keys连接GitHub;  
>第二部分：在GitHub上创建仓库，在本地创建项目，然后将本地项目通过SSH提交到GitHub仓库中。

## Git for windows配置SSH访问GitHub
***
## 检查本机是否有ssh key设置
`$ cd ~/.ssh` 或 `cd .ssh`  
如果没有则提示： 
>No such file or directory

如果有则进入~/.ssh路径下(ls查看当前路径文件, rm *删除所有文件)  

## 使用Git Bash生成新的ssh key.  
`$ cd ~   #保证当前路径在"~"下`







## 将本地项目通过SSH push到GitHub
***
## 在github上创建一个示例仓库， 如：test ssh key  

## 复制test ssh key的ssh路径  

## 本地创建项目  
### (1) 创建目录  
`$ mkdir test`  
`$ cd test`  
### (2) 初始化  
`git init`  
### (3) 创建hello.md文件  
`$ echo "this is a test of test ssh key" > hello.md`  
### (4) 提交到本地  
若出现如上warning提示则重新提交一次即可  
`$ git add .`  
`$ git commit -m "add hell.md"   #提交记录说明`  
### (5) 提交到github  
`$ git remote add origin 'the path of the test ssh key'`  
`$ git push -u origin master`  

## 刷新test ssh key仓库， 查看hello.md.

