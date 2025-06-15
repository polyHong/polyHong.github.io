---
layout: post
title: GitHub 私有仓库以及 git 的使用
category: 技术
tags: github, git, repository
keywords: github, git command
description: github private repository and the use of git.
---

## GitHub 和 git 的目的

因为要保存一个项目的代码以及中间版本，每次在 py 文件的 title 上增加注释总会忘记。有这方面的需求的小伙伴就可以尝试一下GitHub来保存，毕竟GitHub的私有仓库已经免费了。

> 不过我对 GitHub 私有仓库的安全性一直存在疑惑，不过又不是大佬，哈哈哈，如果有解疑的小伙伴也可评论。

## GitHub 私有库的建立

GitHub 的私有库是在被微软收购之后才有的活动，个人用户可以建立免费的私有仓库。

![](https://picx.zhimg.com/v2-d4398cf34d38782b10820678a2dd6cd3_1440w.jpg)

建立私有仓库

可以按照提示一步步进行，只要确认是 private 就可以了。

## git 的配置

首先你需要让你的git本地仓库知道你的基本信息：

```bash
配置用户名：
git config --global user.name "your name";
配置用户邮箱：
git config --global user.email "youremail@github.com";
```

## git 与 GitHub 私有仓库建立联系

首先我们要明白 git 本地仓库与 github 私有仓库的关系。其实 git 的话就是在本地建立个文件夹来保存相应的文件。而 GitHub 远程仓库就是将本地仓库上传到GitHub的服务器中。

### 生成 ssh-key

```bash
ssh-keygen -t rsa -b 4096 -C "youremail@github.com"
```

然后，系统会让你选择保存文件的路径，你也可以直接回车就可以了。系统将生成 [id\_rsa.pub](https://zhida.zhihu.com/search?content_id=198219686&content_type=Article&match_order=1&q=id_rsa.pub&zhida_source=entity) 文件。

![](https://pica.zhimg.com/v2-0f28056a1889e36bebeafe59a8d51cca_1440w.jpg)

我们将 id\_rsa.pub 中的 ssh code 复制到 GitHub -> 头像 -> setting -> SSH and PGP Keys 中。

![](https://picx.zhimg.com/v2-fa046b9a0d94afe81534794ef720d56b_1440w.jpg)

setting

![](https://pica.zhimg.com/v2-36bd5ed80f6edb8c148c6b3a4dae2ac8_1440w.jpg)

new ssh keys

这样我们就建立了 git 与 GitHub 之间的链接，需要注意的是，GitHub 已经不支持用户名和密码的验证方式。

### 本地仓库的建立

在当前项目文件夹建立git 本地仓库

```bash
git init
```

这样在本地就建立了一个.git 隐藏文件夹

### 建立本地仓库与远程仓库的链接

我们使用远程仓库的ssh链接将git仓库与远程仓库建立联系

```bash
git remote add "name" "yourproject.git"
```
![](https://picx.zhimg.com/v2-41363bdfc8f4f68ee30f3d1cfd4b6603_1440w.jpg)

### git 的基本操作

将所有文件提交到暂存区

```bash
git add .
git add <file1> <file2> ...
git add [dir]
```

将暂存区中的文件提交到本地仓库中

```bash
git commit -m "commit_info"
```

将本地仓库的文件提交到远程仓库中

```bash
git push "name" branch
```