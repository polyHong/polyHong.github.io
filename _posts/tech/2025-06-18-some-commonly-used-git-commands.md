---
layout: post
title: 一些常用的 Git 命令
category: 技术
tags: github, git, repository
keywords: github, git command
description: some commonly used Git commands.
---

## 一、初始化与克隆

```bash
git init    # 初始化本地仓库 
git clone <仓库地址>    #克隆远程仓库到本地 
```

## 二、提交代码三连击

```bash
git add .   #添加所有改动到暂存区 
git add <文件名>    #将指定文件添加到暂存区 
git commit -m "描述"    #提交代码并写明描述 
git push origin main    #推送到远程分支 
```

## 三、查看状态与历史

```bash
git status  #查看状态(哪些被修改,未提交等) 
git log     #查看提交记录 
git log --oneline   #简洁查看提交历史 
git diff    #查看代码差异 
git diff --cached   #查看暂存区与上一次提交的差异
```

## 四、分支管理操作

```bash
git branch  #查看本地分支
git checkout dev       #切换分支
git checkout -b dev    #创建并切换分支
git merge<分支名>       #合并 dev 分支到当前分支
```

## 五、远程仓库交互

```bash
git remote -v   #查看远程仓库
git remote add origin <地址>    #添加远程仓库
git pull    #拉取最新代码合并到当前分支
git push origin <分支名>    #推送本地提交到远程分支
```

## 六、撤销与恢复操作(慎用!)

```bash
git reset <文件名>   #取消暂存某个文件
git reset --hard    #丢弃所有未提交的更改
git stash       #临时保存修改
git stash pop   #恢复之前保存的修改
```
