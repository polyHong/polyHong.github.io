---
layout: post
title: Windows 系统安装 CLI 工具
category: 技术
tags: AI, Claude Code, Codex, Gemini
keywords: AI, Claude Code, Codex, Gemini
description: install kinds of CLI tools on the platforms of Windows.
---


## 系统要求

- 操作系统：Windows 10/11 64 位系统
- 硬件要求：8GB+ RAM
- 软件要求：[Node.js 18+](https://nodejs.org/en/download)、[Git for Windows](https://git-scm.com/install/windows)、VS Code 最新版
- 网络要求：需要连接互联网以进行身份验证和人工智能处理
- Shell：Windows Shell 或 Windows CMD

## 1. Claude Code

### 第一步：终端安装

打开PowerShell或CMD窗口，执行以下命令安装：
```bash
npm install -g @anthropic-ai/claude-code
```

验证安装
```bash 
claude --version
```

### 第二步：配置环境变量

#### Git Bash 路径配置

1. 右键"此电脑" → “属性” → “高级系统设置”
2. 点击"环境变量" → 在系统变量中添加：

    - 变量名：`CLAUDE_CODE_GIT_BASH_PATH`
    - 变量值：`C:\\Program Files\\Git\\bin\\bash.exe` （根据实际安装路径调整）

> `系统属性`面板也可以通过`Win + R`运行`sysdm.cpl` 来打开。


#### 配置环境变量（国内访问）

注册第三方中转账户，获取API额度，这里以 Aihubmix 为例。

设置环境变量：

- 变量名：ANTHROPIC_BASE_URL
- 变量值：https://aihubmix.com
- 变量名：ANTHROPIC_API_KEY
- 变量值：sk-***


### 第三步：终端启动
定位到目标项目目录，比如 `cd ~/Desktop/my-project`。输入 `claude` 启动，即可使用。


### 授权

如弹出授权页面，点击跳转到 Claude 官网进行确认，授权成功后，返回终端继续。认证不需要付费账号，随便注册有一个免费的 claude 账号就行。

如果想绕过验证，直接使用 Aihubmix 的转发，只需要在用户名目录下的 `.claude.json` 中增加一行配置：
```bash 
"hasCompletedOnboarding": true,
```

### VS Code 集成配置

1. 打开VSCode → 扩展商店搜索"claude code"
2. 安装官方插件

## 2. Gemini CLI

### 第一步：终端安装

打开PowerShell或CMD窗口，执行以下命：
```bash 
npm install -g @google/gemini-cli
```

验证安装
```bash 
gemini --version
```


### 第二步：配置环境变量

#### Git Bash 路径配置

1. 右键"此电脑" → “属性” → “高级系统设置”
2. 点击"环境变量" → 在系统变量中添加：

    - 变量名：`GOOGLE_GEMINI_GIT_BASH_PATH`
    - 变量值：`C:\\Program Files\\Git\\bin\\bash.exe` （根据实际安装路径调整）

> `系统属性`面板也可以通过`Win + R`运行`sysdm.cpl` 来打开。


#### 配置环境变量（国内访问）

注册第三方中转账户，获取API额度，这里以 Aihubmix 为例。

设置环境变量：

- 变量名：GOOGLE_GEMINI_BASE_URL
- 变量值：https://aihubmix.com/gemini
- 变量名：GEMINI_API_KEY
- 变量值：sk-***

### 第三步：终端启动

定位到目标项目目录，比如 `cd ~/Desktop/my-project`。输入 `gemini` 启动，即可使用。


### VS Code 集成配置

1. 打开VSCode → 扩展商店搜索"gemini"
2. 安装官方插件


## 3. OpenAI Codex CLI

### 第一步：终端安装

打开PowerShell或CMD窗口，执行以下命：
```bash 
npm install -g @openai/codex
```

验证安装
```bash 
codex --version
```

### 第二步：环境变量配置（国内访问）

注册第三方中转账户，获取API额度，这里以 Aihubmix 为例。

1. 配置 `auth.json` 文件
编辑 `C:\\Users\\用户名\\.codex\\auth.json` 文件，若无，则在该目录下新建 `auth.json`，内容如下：
```bash 
{
  "OPENAI_API_KEY": "你的API_KEY"
}
```

2. 配置 `config.toml` 文件

编辑 `C:\\Users\\Hong\\.codex\\config.toml` 文件，若无，则在该目录下新建文件 `config.toml`，内容如下：
```bash 
model_provider = "yourapi"
model = "gpt-5-codex"
model_reasoning_effort = "high"
disable_response_storage = true
preferred_auth_method = "apikey"

[model_providers.yourapi]
name = "yourapi"
base_url = "https://aihubmix.com/v1"
wire_api = "responses"
```

### 第三步：终端启动

安装完成后，您可以在任何项目目录中开始使用 Codex：
```bash 
# 导航到您的项目
$ cd your-project-folder

# 启动 Codex
$ codex
```

### VS Code 集成配置

1. 打开VSCode → 扩展商店搜索"codex"
2. 安装官方插件"Codex-Plugin"和"Codex - OpenAI's coding agent"


## 4. Continue CLI

### 第一步：终端安装

打开PowerShell或CMD窗口，执行以下命：
```bash
# Install
npm install -g @continuedev/cli
```

验证安装
```bash 
cn --version
```

### 第二步：配置环境变量

`cn` 使用与 Continue 完全相同的配置文件 `config.yaml`。也就是说，你可以登录 Continue Hub，或者直接使用你现有的本地配置。

要在不同配置之间切换，你可以在 `cn` 中使用 `/config` 斜杠命令，或者在启动时加上 `--config` 标志。例如：
```bash 
cn --config continuedev/default-agent
```
或
```bash 
cn --config ~/.continue/config.yaml
```

### 第三步：终端启动

```bash 
# Interactive mode
cn

# Headless mode
cn -p "Generate a conventional commit name for the current git changes"
```
