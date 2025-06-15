---
layout: post
title: SSH连接GitHub
category: 技术
tags: [Git,GitHub,SSH]
keywords: SSH, GitHub
description: 
---

本文可分为三部分：  
>第一部分：通过Gits配置SSH Keys连接GitHub;  
>第二部分：在GitHub上创建仓库，在本地创建项目，然后将本地项目通过SSH提交到GitHub仓库中。  
>第三部分：在使用ssh或git命令时可能碰到的一些问题，及其解决办法。

# Part I: Git配置SSH访问GitHub

## Step1. 检查本机是否有ssh key设置

```bash
$ cd ~/.ssh
```

或 

```bash
cd .ssh
```

如果没有则提示： 

```bash
No such file or directory
```

如果有则进入~/.ssh路径下(ls查看当前路径文件, rm *删除所有文件)  

## Step2. 使用Git Bash生成新的ssh key   

```bash
$ cd ~         #保证当前路径在"~"下
$ ssh-keygen -t rsa -C "your email addr"
```

```bash
Generating public/private rsa key pair.  
Enter file in which to save the key (/c/Users/xxxx_000/.ssh/id_rsa):   #不填直接回车  
Enter passphrase (empty for no passphrase):   #输入密码（可以为空）  
Enter same passphrase again:   #再次确认密码（可以为空）  
Your identification has been saved in /c/Users/xxxx_000/.ssh/id_rsa.   #生成的密钥  
Your public key has been saved in /c/Users/xxxx_000/.ssh/id_rsa.pub.  #生成的公钥  
The key fingerprint is:  
e3:51:33:xx:xx:xx:xx:xxx:61:28:83:e2:81 xxxxxx@yy.com  
```

本机已完成ssh key设置，其存放路径为：`c:/Users/xxxx_000/.ssh/` 下。注释：可生成ssh key自定义名称的密钥，默认id_rsa。 

```bash
$ ssh-keygen -t rsa -C "邮箱地址" -f ~/.ssh/github_blog_keys #生成ssh key的名称为github_blog_keys
```

慎用容易出现其它异常。

## Step3. 添加ssh key到GitHub  

1. 登陆到GitHub系统： 点击右上角账号头像的 "▼"→Settings→SSH kyes→Add SSH key.
2. 复制id_rsa.pub的公钥内容：  
	1) 进入c:/Users/xxxx_000/.ssh/目录下，打开id_rsa.pub文件，全选复制公钥内容;  
	2) Title自定义，将公钥粘贴到GitHub中Add an SSH key的key输入框，最后“Add Key”.

## Step4. 配置账户

```bash
$ git config --global user.name “your_username”  #设置用户名`
$ git config --global user.email “your_registered_github_Email”  #设置邮箱地址(建议用注册github的邮箱)
``` 

## Step5. 测试ssh keys是否设置成功

```bash
$ ssh -T git@github.com
The authenticity of host 'github.com (192.30.252.129)' can't be established.  
RSA key fingerprint is 16:27:xx:xx:xx:xx:xx:4d:eb:df:a6:48.  
Are you sure you want to continue connecting (yes/no)? yes #确认你是否继续联系，输入yes  
Warning: Permanently added 'github.com,192.30.252.129' (RSA) to the list of known hosts.  
Enter passphrase for key '/c/Users/xxxx_000/.ssh/id_rsa':  #生成ssh kye是密码为空则无此项，若设置有密码则有此项且，输入生成ssh key时设置的密码即可。
Hi xxx! You've successfully authenticated, but GitHub does not provide shell access. #出现词句话，说明设置成功。
```

# Part II: 将本地项目通过SSH push到GitHub

第一步、在github上创建一个示例仓库， 如：test ssh key  

第二部、复制test ssh key的ssh路径  

第三步、本地创建项目  

1.创建目录  

```bash
$ mkdir test
$ cd test
```

2.初始化

```bash
git init
```  

3.创建hello.md文件  

```bash
$ echo "this is a test of test ssh key" > hello.md
```

4.提交到本地  

```bash
$ git add .
$ git commit -m "add hell.md"   #提交记录说明
``` 

5.提交到Github

```bash
$ git remote add origin 'the path of the test ssh key'
$ git push -u origin master
```

6.刷新test ssh key仓库， 查看hello.md.


# Part III：报错处理

## 一、git clone Windows报错：fatal: unable to checkout working tree

```bash
$ git clone https://gitlab.com/padavan-ng/padavan-ng.git
Cloning into 'padavan-ng'...
remote: Enumerating objects: 119768, done.
remote: Total 119768 (delta 0), reused 0 (delta 0), pack-reused 119768
Receiving objects: 100% (119768/119768), 352.30 MiB | 3.24 MiB/s, done.
Resolving deltas: 100% (31642/31642), done.
error: invalid path 'trunk/user/ipset/ipset-6.x/tests/bitmap:ip.t'
fatal: unable to checkout working tree
warning: Clone succeeded, but checkout failed.
You can inspect what was checked out with 'git status'
and retry with 'git restore --source=HEAD :/'
```

文件名含有冒号：，  憨憨Windows不支持，需要对git作如下配置：

```bash
# 忽略路径中的转义字符
git config --global core.protectNTFS false
# 禁用换行符转换
git config --global core.autocrlf false
# 中文文件名，乱码问题。设为false的话，就不会对0x80以上的字符进行quot
git config --global core.quotepath false
```
## 二、Github 无法 ping 通

a) 明确问题：先是验证SSH公钥失败。

```bash
$ ssh -T git@github.com
ssh: Could not resolve hostname github.com: Name or service not known
```

再是 `ping github` 不成功，发现是和 `github.com` IP主机连接不同的问题。

```bash
$ ping github.com
Ping request could not find host github.com. Please check the name and try again.
```

b) 分析问题：`ping` 其他网站正常，只有 `github` 不通，可能是域名解析错误，也就是DNS的问题。

c) 解决问题：方法很简单，修改DNS服务器。修改 `hosts` 文件，`hosts` 文件地址在

```bash
C:\Windows\System32\drivers\etc
```

只要文本格式打开 `hosts`，最后添加：

```bash
140.82.113.3    github.com
```

**需要注意 `github` 的IP地址可能会变。**
Github网站真实IP地址要在 [ipaddress.com](https://www.ipaddress.com/website/www.github.com) 查询，确定无误再添加进 `hosts`. 

## 三、ssh报错：ssh: Could not resolve hostname github.com

a) 问题：设置GitHub账户的过程一切正常，但尝试将仓库推送到GitHub时，出现问题。显示的错误信息如下：

```bash
ssh: Could not resolve hostname github.com: Name or service not known
fatal: The remote end hung up unexpectedly.
```

b) 解决办法：刷新DNS、更换DNS服务器或重启网络。在 Windows 的终端中，使用以下命令：

```bash
ipconfig /flushdns
```

在 MacOS 上，使用以下命令：

```bash
dscacheutil -flushcache
```

在 Linux 系统，使用以下命令：

```bash
service nscd restart
```

## 四、git pull encounters kex_exchange_identification

当使用 `git pull` 从 `Github` 拉取代码时，遇到了以下错误：

```bash
kex_exchange_identification: Connection closed by remote host
Connection closed by 20.205.243.166 port 22
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

解决办法：创建/修改 `~/.ssh/config` 文件，添加以下代码：

```bash
Host github.com
    HostName ssh.github.com
    User git
    Port 443
```


## 相关链接：
1. [GitHub](https://github.com/);
2. [为Github账户设置SSH key](http://zuyunfei.com/2013/04/10/setup-github-ssh-key/)
3. [Git for windows](https://git-for-windows.github.io/)











