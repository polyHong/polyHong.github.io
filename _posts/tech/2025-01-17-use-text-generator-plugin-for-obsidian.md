---
layout: post
title: 使用Text Generator插件打造你的Obsidian AI
category: 技术
tags: Obsidian AI, Text Generator
keywords: Obsidian, AI, Text Generator
description:
---


作为一名Obsidian用户，我一直羡慕Notion AI那样将大型语言模型的强大能力与笔记软件紧密结合的功能。这种整合不仅极大地提升了知识管理的效率，还能在创作与整理信息时带来巨大的助力。Text Generator插件的出现，让我长期以来渴望在Obsidian中实现的愿望变得触手可及，使我能在熟悉的环境中直接利用大语言模型的强大力量。令人意外的是，Obsidian社区中关于此插件的讨论并不多。因此，我决定写下这篇文章，期望以此抛砖引玉，激发更多关于在Obsidian里应用大模型的灵感和实践。

## 如何在Obsidian中使用Text Generator插件？

### 1\. 安装插件

首先，用户需要在Obsidian的插件市场中找到Text Generator插件，并完成安装。

#### 步骤

1. 打开Obsidian
2. 进入设置
3. 选择“插件市场”
4. 搜索并找到Text Generator插件
5. 点击“安装”

### 2\. 配置插件

插件安装完成后，需进行必要的配置才能正常使用。

#### 选择LLM模型

Text Generator插件支持多种大型语言模型。用户可配置模板保存路径。模板包含一整套处理流程，包括输入获取、提示词（Prompt）设计和输出方式。默认模板保存路径为`textgenerator/prompts`，可按个人习惯调整。

#### 配置模版

Text Generator提供模板管理工具，可通过它安装一系列预设模板。我建议初次尝试时安装官方默认模板库。通过快捷键 Command + P（Windows为 Ctrl + P）调出控制面板，输入“Text Generator”，在弹出的选项中选择“Text Generator: Template Packages Manager”。此处有多个示例模板库，建议安装“Default Prompts”和“Experimental Package”作为参考范例。模板文件将安装在之前配置的“模板保存路径”下，比如我配置的是“Extras/textgenerator/prompts”，则模板文件夹即位于此处。

### 3\. 使用示范

以下是我常用的两个场景，供大家借鉴，希望引发更多关于Obsidian中集成大模型的思路。

#### 用法1：改写文本

改写或润色文本是我最常用的场景之一。借助大模型的能力，我能改进自己的文字，修正不妥之处和冗余表达。官方默认库中有一份名为`rewrite`的模板提供类似功能，但默认为英文，我们可以直接调整该模板内容。

将正文更改为以下内容：

```markdown
作为中文写作改进助理，请对所提供文本进行拼写、语法、清晰度、简洁性及整体可读性的提升，同时拆分长句，减少重复，并给出改进建议。请仅返回修改后的文本版本，避免任何解释。

===

{{tg_selection}}

***

{{output}}
```

然后选中需要改写的文字，打开控制面板，输入“Text Generator”，选择“Text Generator: Templates: Generate & Insert”，找到名为“rewrite”的模板，即可让大模型重写文本。

#### 用法2：总结多个文件生成周报

除常规用法外，结合JavaScript代码还能实现更多功能。这里示范一个总结每日笔记中运动记录并生成Markdown表格的例子。首先需在Text Generator设置中开启执行JavaScript脚本的权限。进入Text Generator设置，在“Template Settings”中启用“Allow scripts”。

我会在`weekly`文件夹下创建多篇以日期命名的笔记，每篇笔记包含“运动记录”和“工作日记”两个部分。每周末，我希望汇总该周运动时间，并以表格形式输出。

这里涉及两个模板：一个（weeklySummary）用于预处理，读取符合条件的记录；另一个（summaizeWeeklyRecords）用于调用大语言模型处理文本。

模板中可加入如下代码，读取符合格式的文件，提取标题为“运动记录”的内容，汇聚所有符合要求的内容，并交给模型处理。

```javascript
{{#script}}
  let activeFile = app.workspace.getActiveFile();
  let currentDirPath = activeFile.parent.path;
  let filesInDir = app.vault.getFiles();
  let regex = /^\d{4}-\d{2}-\d{2}.md$/; // 读取符合 4个数字-2个数字-2个数字.md 的文件
  let filteredMarkdownFiles = filesInDir.filter(file => 
        file.path.startsWith(currentDirPath) &&
        regex.test(file.name) // Test if the file name matches the pattern
    );

  const contentArray = [];
  let weeklySummary = '';

  for (const file of filteredMarkdownFiles){
    notice("read from " + file.path);
    const sectionCache = app.metadataCache.getFileCache(file);
    const headingCache = sectionCache.headings?.filter(h => {
        return h.heading === "运动记录"
    })    
    if(headingCache?.length > 0) {
        const headingRange = {
            start: headingCache[0].position.start.offset,
            end: headingCache[0].position.end.offset,
        };
        const heading = headingCache[0].heading;
        const content = await read(file.path);

        if(!content) continue;
        const headingInRange = content.slice(headingRange.start, headingRange.end);
        const contentInNextRange = content.slice(headingRange.end);

        const level = headingInRange.match(/#{1,6}/)[0].length;
        const nextHeadingRegex = new RegExp(\`(^|\\n)#{1,${level}}\\s\`);

        const position = contentInNextRange.match(nextHeadingRegex);

        let contentRange;
        let positionEnd;

        if(position) {
            positionEnd = headingRange.end + position?.index;
            contentRange = content.slice(headingRange.end, positionEnd);
        }else {
            contentRange = content.slice(headingRange.end);
        }
        weeklySummary += file.name + ': ' + '\n\n';
        weeklySummary += contentRange+ '\n\n';
    }    
  }

    this.weeklyRecords = await run("default/summaizeWeeklyRecords", {selection: weeklySummary })
{{/script}}
```

第二个模板用于撰写提示词：

```markdown
请帮我提取文本中的运动记录，并以"日期"，"运动项目"，"总计时间"的维度输出为markdown格式的表格

{{selection}}

***

{{output}}
```

最后，选中需要生成周报的笔记，打开控制面板，输入“Text Generator”，选择“Text Generator: Templates: Generate & Insert”，找到名为“weeklySummary”的模板，即可生成周报。

## 总结

### 使用Text Generator的优势

**高度集成** ：紧密结合Obsidian，使用户可在熟悉环境中享受AI辅助

**定制化程度高** ：支持根据需求调整模型与模板，实现个性化内容生成。

### 需改进之处

**配置复杂** ：对部分用户而言，Text Generator插件配置较为繁琐，需一定学习与实践。

**学习成本** ：用户需投入时间掌握配置和使用技巧，方能高效利用。

Text Generator插件为Obsidian用户带来了强大工具，便于融合各类大型语言模型。尽管存在一定学习成本，但其提供的定制化方案与扩展能力，毋庸置疑使它成为值得尝试的选择。
