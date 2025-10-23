---
layout: post
title: Mac/Linux 系统安装 CLI 工具
category: 技术
tags: AI, Claude Code, Codex, Gemini, CLI
keywords: AI, Claude Code, Codex, Gemini, CLI
description: install kinds of CLI tools on the platforms of Mac and Linux.
---

## 系统要求

- 操作系统：macOS 10.15+，Ubuntu 20.04+/Debian 10+
- 硬件要求：4GB+ RAM
- 软件要求：[Node.js 18+](https://nodejs.org/en/download)
- 网络要求：需要连接互联网以进行身份验证和人工智能处理
- Shell：在 Bash、Zsh 或 Fish 中效果最佳

## 1. Claude Code

用 Aihubmix 为 Claude Code 提供强劲动力，彻底告别连接不稳定和额度难买的烦恼。Aihubmix 的转发服务基于官方渠道，合规安全，无需担心账号风险或隐性限制。

### 第一步：终端运行

```bash
npm install -g @anthropic-ai/claude-code
```

### 第二步：环境变量配置

到 Aihubmix[「Keys」页面](https://aihubmix.com/token) 生成密钥，在系统环境变量中填入这个密钥和转发地址。

比如在 ~/.zshrc 中添加：

```bash
export ANTHROPIC_API_KEY="sk-***"
export ANTHROPIC_BASE_URL="https://aihubmix.com"
```

### 第三步：使配置生效

添加配置之后，终端执行 source ~/.zshrc，回车即可。

### 第四步：终端启动

定位到目标项目目录，比如

```bash
cd ~/Desktop/my-project
```

输入 claude 启动，即可使用。

### 初始化配置

#### 授权

如弹出授权页面，点击跳转到 Claude 官网进行确认，授权成功后，返回终端继续。认证不需要付费账号，随便注册有一个免费的 claude 账号就行。

如果想绕过验证，直接使用 Aihubmix 的转发，只需要在用户名目录下的 `.claude.json` 中增加一行配置：

```bash
"hasCompletedOnboarding": true, 
```

### 启动

启动后，Claude Code 会显示当前配置信息，包括 API Key 和 API Base URL。 需要确认的地方，选择 Yes 回车确认，即可完成所有设置。

比如：Claude 检测到系统环境变量有自定义 KEY，选 Yes

```bash
Detected a custom API key in your environment

ANTHROPIC_API_KEY: sk-***
Do you want to use this API key?

> 1. Yes
2. No(recommended)

Enter to confirm .Esc to cancel
```

#### 切换模型

使用 Claude Code 命令：

```bash
/model [model id] 
```

默认模型为 `Sonnet 4`，可以用效果更好的 `Opus 4`：

```bash
/model opus
```

或者，换成其他 claude 模型：

```bash
/model claude-3-7-sonnet-20250219
```

```bash
/model claude-3-5-sonnet-20241022
```

#### Kimi K2 支持

启动 Claude Code 之后，只需要运行指令

```bash
/model moonshotai/kimi-k2-instruct
```

## 2. Gemini Cli

用 Aihubmix 为 Gemini CLI 提供强劲动力，享受稳定高效的 Gemini 模型服务。

### 第一步：终端运行

```bash
npm install -g @google/gemini-cli
```

### 第二步：环境变量配置

在系统环境变量中填入 Aihubmix 密钥和转发地址，密钥可以在 Aihubmix 「Keys」页面 生成。

比如在 `~/.zshrc` 中添加：

```bash
export GOOGLE_GEMINI_BASE_URL="https://aihubmix.com/gemini"
export GEMINI_API_KEY="sk-***"
```

### 第三步：使配置生效

添加配置之后，终端执行 `source ~/.zshrc`，回车即可。

### 第四步：终端启动

终端输入

```bash
gemini
```

### 初始化配置

#### 选择接入方式

启动之后输入 `/auth`，回车，选择 `Gemini API Key (AI Studio)`

```bash
○ Login with Google
● Gemini API Key (AI Studio)
○ vertex AI
```

> 可以随时用 `/auth` 命令来切换授权方式。

#### 启动成功

完成以上初始化即可正常使用。


## 3. OpenAI Codex CLI 

通过 AiHubMix 在命令行中支持 OpenAI Codex 调用。

AiHubMix 提供了与 OpenAI Codex CLI 的无缝集成，让你可以在命令行环境中利用先进的 AI 编程助手。通过简单的配置步骤，即可在终端中直接使用自然语言执行各种编程和系统操作任务。

### 第一步：终端运行

```bash 
npm install -g @openai/codex
```

### 第二步：环境变量配置

打开你的 Shell 配置文件（例如 `.zshrc` 或 `.bashrc`），添加以下环境变量：
```bash 
export OPENAI_BASE_URL="https://aihubmix.com/v1"
export OPENAI_API_KEY="sk-***" # 替换为你的 AiHubMix API 密钥
```

> 这里的 `OPENAI_API_KEY` 应该使用 AiHubMix 的密钥，变量名保持为 `OPENAI_API_KEY` 是为了兼容 OpenAI 原生客户端。


### 第三步：使配置生效

在终端中执行以下命令，使环境变量生效：
```bash 
source ~/.zshrc  # 如果使用 zsh
# 或
source ~/.bashrc  # 如果使用 bash
```

### 第四步：终端启动

定位到你的项目目录，然后运行 `codex` 命令：
```bash 
cd /你的项目路径
codex
```

#### 使用自然语言执行任务

现在可以通过自然语言向 Codex CLI 输入指令，例如：
```bash 
# 示例输入
讲解一下 AnimatedText
```


### 高级配置

> - 默认模型为 `codex-mini-latest`，一个专为编码任务微调过的 `o4-mini`，可以在 `~/.codex/config.json`修改
> - 目前仅支持 OpenAI 家的模型，模型列表可在 Responses API 文档 中查看
> - 你可以通过编辑 `~/.codex/instructions.md` 文件来自定义系统提示词，定制 AI 助手的行为


### 使用命令参考

#### 帮助命令

```bash 
codex -h
```

#### 完整命令选项

```bash 
Usage
  $ codex [options] <prompt>

Options
  -h, --help                 显示帮助信息并退出
  -m, --model <model>        指定使用的模型 (默认: codex-mini-latest)
  -i, --image <path>         包含图像输入的文件路径
  -v, --view <rollout>       查看之前保存的会话记录
  -q, --quiet                非交互模式，仅打印助手的最终输出
  -a, --approval-mode <mode> 覆盖审批策略: 'suggest', 'auto-edit', 或 'full-auto'

  --auto-edit                自动批准文件编辑；仍会提示确认命令
  --full-auto                自动批准沙箱环境中的编辑和命令

  --no-project-doc           不自动包含仓库中的 'codex.md' 文件
  --project-doc <file>       包含指定的 Markdown 文件作为上下文
  --full-stdout              不截断命令输出的 stdout/stderr

危险选项
  --dangerously-auto-approve-everything
                             跳过所有确认提示并直接执行命令（无沙箱保护）
                             仅用于临时本地测试环境

实验性选项
  -f, --full-context         以"完整上下文"模式启动，将整个仓库加载到上下文中
                             并在一次操作中应用批量编辑
                             仅兼容 --model 参数

示例
  $ codex "编写并运行一个打印 ASCII 艺术的 Python 程序"
  $ codex -q "修复构建问题"
```


## 4. Continue CLI 

Continue CLI 是一个开源的、模块化的命令行编码助手。它提供了一个经过实战检验的代理循环，让你只需将模型、规则和工具接入即可使用。

### 第一步：终端运行

```bash 
# Install
npm i -g @continuedev/cli
```

### 第二步：环境变量配置
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

## 5. Qwen Code 

利用 Aihubmix 平台的任何大语言模型为 Qwen Code 提供支持。

### 第一步：终端运行
```bash 
npm install -g @qwen-code/qwen-code
qwen --version
```

### 第二步：环境变量配置

在系统环境变量中填入 Aihubmix 密钥和转发地址，密钥可以在 Aihubmix 「Keys」页面 生成。

比如在 `~/.zshrc` 中添加：
```bash 
export OPENAI_API_KEY="your_aihubmix_key"
export OPENAI_BASE_URL="https://aihubmix.com/v1"
export OPENAI_MODEL="your_model"
```

> 对于 Mac 用户，你可以在用户名目录通过快捷键 ⌘ + ⇧ + . 显示隐藏的 .zshrc 文件，用系统的「文本编辑」APP 打开并添加上述内容。


### 第三步：使配置生效
添加配置之后，终端执行 `source ~/.zshrc`，回车即可。

### 第四步：启动并使用

终端输入
```bash 
qwen
```

启动之后输入 `/about` 确认配置，回车，可以看到当前的版本信息和选择的大模型。