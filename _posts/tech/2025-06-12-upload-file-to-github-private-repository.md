---
layout: post
title: 如何上传代码到GitHub私有仓库
category: 技术
tags: git, Github
keywords: private repository
description: how to upload files to Github private repository
---


## 方法一：使用bash command上传代码

要上传代码到GitHub私有仓库，需要按照以下步骤进行操作：

1\. 创建一个GitHub账号：如果还没有GitHub账号，首先需要去GitHub官网注册一个账号，并完成账号验证。

2\. 创建一个私有仓库：登录GitHub账号后，点击右上角的加号按钮，选择“New repository”来创建一个新仓库。在仓库设置页面中，将仓库类型设置为“私人”，然后填写仓库名称和描述，最后点击“Create repository”按钮即可成功创建一个私有仓库。

3\. 在本地计算机上安装并配置Git：从Git官方网站下载Git并安装在本地计算机上。然后，在命令行中输入以下命令来配置你的身份信息：

```bash
git config –global user.name “Your Name”  
git config –global user.email “your.email@example.com”  
```

4\. 在本地创建一个Git仓库：在代码的根目录下，右键点击选择“Git Bash Here”，然后在弹出的命令行界面中输入以下命令来初始化一个新的Git仓库：

```bash
mkdir my_project  
cd my_project  
git init 
```

5\. 将代码添加到本地仓库：将你的代码文件复制到刚创建的代码仓库中，使用以下命令将代码添加到本地Git仓库中：

```bash
git add . 
```

该命令中的“.”表示添加当前目录下所有文件到仓库，如果只想添加某个特定文件，可以将“.”替换为文件名。

6\. 提交代码到本地仓库：使用以下命令将代码提交到本地Git仓库：

```bash
git commit -m “提交说明” 
```

该命令中的“提交说明”是对本次提交的简要描述，可以根据实际情况进行修改。

7\. 添加远程仓库：使用以下命令将本地仓库与GitHub上的远程仓库进行关联：

```bash
git remote add origin git@github.com:yourusername/yourrepository.git
```

注意将 \`yourusername\` 替换为你的GitHub用户名，将 \`yourrepository\` 替换为你的私有仓库名称。或

```bash
git remote add origin 远程仓库URL  
```

其中的“远程仓库URL”是在第2步中创建的私有仓库的URL。

8\. 将本地代码推送到GitHub仓库：使用以下命令将本地代码推送到GitHub私有仓库：

```bash
git push -u origin master  
```

该命令中的“origin”是远程仓库的别名，“master”是本地分支的名称，将代码推送到远程仓库的master分支上，\`-u\` 选项可以将本地分支与远程分支关联起来。

9\. 输入GitHub账号密码：在命令行界面中输入GitHub账号和密码进行身份验证。

10\. 完成代码上传：等待命令执行完毕，即可完成代码上传到GitHub私有仓库。

注意：在进行上述操作之前，确保已经在本地完成了相应的代码编写和测试，并且已经将需要上传的文件放置在了正确的目录下。此外，如果你的私有仓库使用了SSH密钥来进行访问控制，那么在配置Git时，你需要将你的公钥添加到你的GitHub账号中。这样，你才能在提交代码时使用SSH协议进行身份验证。

## 方法二：使用GitHub Desktop上传代码  

以下是步骤：
a. 在GitHub Desktop中选择“File”（文件） -> “Add Local Repository”（添加本地仓库）。

b. 选择项目所在的本地文件夹，并命名该仓库。  

c. 点击“Publish repository”（发布仓库）按钮，选择要上传到的GitHub账号和仓库。  

d. 点击“Publish Repository”（发布仓库）按钮，GitHub Desktop会自动将本地仓库的代码上传到GitHub私有仓库。


以上两种方法任选一种，即可将代码成功上传到GitHub私有仓库。上传完成后，就可以通过Git进行代码的版本控制和协同开发。