---
layout: post
title: 斯坦福大学官方发布的润色指令及其优化
category: 科研
tags: AI Instruction
keywords: AI, Research, Polishing Instruction
description:
---

## 1 原版（斯坦福大学官方发布）

### 1.1 To enhance text clarity（提升文本清晰度）

英文：  

```html
As a non-native English speaker, kindly help me revise the following text for improved understanding and clarity.   Please check for spelling and sentence structure errors and suggest alternatives. What suggestions do you have to enhance the clarity of my text? Please identify any parts of my writing that may be difficult for a lay audience to understand.  
```

中文：  

```html
作为一名非英语母语人士，请帮我修改以下文本，以提高理解和清晰度。请检查拼写和句子结构错误，并提出替代方案。你有什么提升我文本清晰度的建议吗？请指出我写作中可能让普通读者难以理解的部分。 
```

### 1.2 To make text more compelling（使文本更具吸引力）

英文：  

```html
Please provide feedback on my writing style and how I can make it more persuasive and compelling for the grant reviewer. I’m trying to hook my reader with a strong introduction. Can you suggest a more captivating first sentence to draw them in from the start?
```

中文：  

```html
请对我的写作风格提供反馈，以及我如何能使其对资助评审者更具说服力和吸引力。我正在努力用一个强有力的引言吸引读者。你能建议一个更引人注目的开头句子来吸引他们吗？
```

### 1.3 To improve structure and flow of text（改善文本的结构和流畅性）

英文：  

```html
I want to improve the overall structure of my Specific Aims. What tips do you have to structure it more effectively? Can you recommend an effective way to organize my Significance section to highlight the innovative aspects of our approach? Please provide detailed feedback on the flow and sequence of my research strategy. 
```

中文：  

```html
我想改进我的具体目标的整体结构。你有什么更有效地构建它的技巧吗？你能推荐一种有效的方式来组织我的重要性部分，以突出我们方法的创新方面吗？请对我的研究策略的流畅性和顺序提供详细反馈。
```

## 2 PromptPilot 优化版（doubao-1.5-pro-256k）

### 2.1 To enhance text clarity（提升文本清晰度）

英文：

```html
Your task is to help a non-native English speaker revise the provided text for better understanding and clarity.
Here is the text that needs to be revised:
<text>
{{TEXT}}
</text>
When working on this text, please perform the following steps:
1. Carefully read the entire text to understand its content.
2. Check for spelling and sentence structure errors. In the <SpellingAndGrammar> tag, list all the spelling and sentence structure errors you find, along with suggestions for correction.
3. For parts of the text that could be improved for better clarity, suggest alternative expressions. Put these suggestions in the <Alternatives> tag.
4. Identify any parts of the text that may be difficult for a lay audience to understand. List these parts and explain why they might be hard to understand in the <HardToUnderstand> tag.
5. In the <FinalRevisedText> tag, present the revised text after applying all the corrections and improvements.
<SpellingAndGrammar>
[List spelling and sentence structure errors and correction suggestions here]
</SpellingAndGrammar>
<Alternatives>
[Provide alternative expressions for better clarity here]
</Alternatives>
<HardToUnderstand>
[Identify parts hard for a lay audience and explain the reasons here]
</HardToUnderstand>
<FinalRevisedText>
[Present the final revised text here]
</FinalRevisedText>
```

中文：

```html
你是一位语言专家，负责帮助非英语母语人士修改文本，以提高文本的理解度和清晰度。你的任务是仔细评估提供的文本，检查拼写和句子结构错误，并提出替代方案，同时指出写作中可能让普通读者难以理解的部分。
请仔细阅读以下需要修改的文本：
<文本>
{{TEXT}}
</文本>
在修改文本时，请遵循以下要求：
1. 检查文本中的拼写错误，并进行修正。
2. 检查句子结构，确保句子通顺、逻辑清晰。如果有不符合语法规则或表意不清的句子结构，提出改进方案。
3. 对于文本中可能让普通读者难以理解的部分，详细指出并说明原因。
4. 针对提高文本清晰度，给出具体的建议。

请在<修改后文本>标签内写下修改后的文本。
在<清晰度建议>标签内提供提高文本清晰度的建议。
在<难以理解部分>标签内指出文本中可能让普通读者难以理解的部分，并说明原因。

<修改后文本>
[在此写下修改后的文本]
</修改后文本>
<清晰度建议>
[在此提供提高文本清晰度的建议]
</清晰度建议>
<难以理解部分>
[在此指出文本中可能让普通读者难以理解的部分，并说明原因]
</难以理解部分>
```

### 2.2 To make text more compelling（使文本更具吸引力）

英文：

```html
Your task is to provide feedback on the given writing style and suggest ways to make it more persuasive and compelling for a grant reviewer. You also need to suggest a more captivating first sentence to hook the reader from the start.
First, please carefully read the following writing sample:
<WritingSample>
{{WRITING_SAMPLE}}
</WritingSample>
When providing feedback, please consider the following aspects:
1. Persuasiveness: Analyze how well the writing makes a case for the grant. Look for strong arguments, evidence, and a clear line of reasoning.
2. Compellingness: Evaluate whether the writing engages the reader's interest. Consider the use of vivid language, storytelling elements, and emotional appeal.
3. Introduction: Assess the effectiveness of the current first sentence in grabbing the reader's attention.
Based on your analysis, provide the following:
- In the <Feedback> tag, give a detailed assessment of the writing style. Point out the strengths and weaknesses, and explain how to enhance the persuasiveness and compellingness.
- In the <Suggestions> tag, offer specific suggestions for improving the writing to make it more suitable for a grant review.
- In the <NewFirstSentence> tag, suggest a new first sentence that is more captivating and draws the reader in.
Please ensure that your feedback and suggestions are clear, specific, and actionable.
<Feedback>
[Provide detailed feedback on the writing style here]
</Feedback>
<Suggestions>
[Offer specific suggestions for improvement here]
</Suggestions>
<NewFirstSentence>
[Suggest a new first sentence here]
</NewFirstSentence>
```

中文：

```html
你的任务是对提供的写作样本进行评估，给出写作风格的反馈，并且建议如何使其对资助评审者更具说服力和吸引力。同时，你需要为该写作提供一个更引人注目的开头句子。
请仔细阅读以下写作样本：
<写作样本>
{{WRITING_SAMPLE}}
</写作样本>
在评估写作风格时，请考虑以下方面：
1. 语言的清晰度和流畅性
2. 逻辑的连贯性和条理性
3. 内容的深度和相关性
4. 整体的感染力和说服力

对于写作风格的反馈，请在<反馈>标签内详细说明优点和不足之处，并提供具体的改进建议。
为了使写作对资助评审者更具吸引力和说服力，你可以从以下几个方面提出建议：
1. 突出关键信息和核心观点
2. 使用具体的数据和案例来支持观点
3. 调整语气和措辞，使其更具权威性和专业性
4. 增强情感共鸣，激发评审者的兴趣和关注

请在<改进建议>标签内详细阐述这些建议。

最后，在<开头句子>标签内提供一个更引人注目的开头句子，以吸引资助评审者的注意力。
请确保你的回答内容丰富、全面，并且严格按照上述标签要求输出。
```

### 2.3 To improve structure and flow of text（改善文本的结构和流畅性）

英文：

```html
Your task is to help improve the overall structure of a research document. You will provide tips for structuring the Specific Aims more effectively, recommend an effective way to organize the Significance section to highlight the innovative aspects, and give detailed feedback on the flow and sequence of the research strategy.
Here is the content of the Specific Aims:
<SpecificAims>
{{SPECIFIC_AIMS}}
</SpecificAims>
Here is the content of the Significance section:
<SignificanceSection>
{{SIGNIFICANCE_SECTION}}
</SignificanceSection>
Here is the content of the research strategy:
<ResearchStrategy>
{{RESEARCH_STRATEGY}}
</ResearchStrategy>
When providing feedback, please follow these steps for each part:
1. Carefully read the entire content of the part.
2. Analyze the current structure, flow, and sequence.
3. Identify areas that need improvement.
4. Formulate specific tips and suggestions.
5. Check again to ensure that all important aspects are covered.

For the Specific Aims, provide your analysis and tips in the <SpecificAimsAnalysis> tag.
<SpecificAimsAnalysis>
[Provide a detailed analysis of the Specific Aims, including what is working well and what can be improved. Then, offer specific tips for better structuring.]
</SpecificAimsAnalysis>

For the Significance section, provide your analysis and organization recommendations in the <SignificanceSectionAnalysis> tag.
<SignificanceSectionAnalysis>
[Analyze the current organization of the Significance section. Point out how to better highlight the innovative aspects. Provide specific recommendations for a more effective organization.]
</SignificanceSectionAnalysis>

For the research strategy, provide your feedback on the flow and sequence in the <ResearchStrategyAnalysis> tag.
<ResearchStrategyAnalysis>
[Analyze the flow and sequence of the research strategy. Identify any logical gaps or areas where the sequence could be improved. Offer detailed suggestions for enhancing the overall flow.]
</ResearchStrategyAnalysis>

Please ensure that your feedback is comprehensive, detailed, and based on the content provided.
```

中文：

```html
你的任务是帮助改进具体目标的整体结构，提供组织重要性部分以突出方法创新方面的有效方式，并对研究策略的流畅性和顺序提供详细反馈。
以下是具体目标：
<specific_goal>
{{SPECIFIC_GOAL}}
</specific_goal>
以下是重要性部分：
<importance_part>
{{IMPORTANCE_PART}}
</importance_part>
以下是研究策略：
<research_strategy>
{{RESEARCH_STRATEGY}}
</research_strategy>
在进行改进和反馈时，请遵循以下指南：
1. 对于具体目标的整体结构改进：
    - 仔细分析目标的各个组成部分，考虑其逻辑顺序、完整性和清晰度。
    - 提供具体的改进建议，如调整顺序、补充必要信息等。
    - 在<goal_improvement>标签内写下你的改进建议。
2. 对于重要性部分的组织：
    - 思考如何突出方法的创新方面，例如通过强调独特的视角、新颖的技术等。
    - 提供组织该部分内容的有效方式，如采用对比、案例分析等。
    - 在<importance_organization>标签内写下你的组织建议。
3. 对于研究策略的流畅性和顺序反馈：
    - 评估研究策略的步骤是否合理、连贯，是否符合研究的逻辑。
    - 指出可能存在的问题，并提供改进建议。
    - 在<strategy_feedback>标签内写下你的详细反馈。

请确保你的回答丰富、全面，能够为每个部分提供有价值的建议和反馈。
```

## 3 Prompt Optimizer 优化版（Deepseek-R1）

### 3.1 To enhance text clarity（提升文本清晰度）

英文：

```html
<optimized_prompt>
<task>Optimize English texts by non-native speakers to enhance clarity and comprehensibility.</task>

<context>
As a non-native English speaker, kindly help me revise the following text for improved understanding and clarity.   
Please check for spelling and sentence structure errors and suggest alternatives.   
What suggestions do you have to enhance the clarity of my text? Please identify any parts of my writing that may be difficult for a lay audience to understand.  
</context>

<instructions>
1. Receive the English text provided by the user.
2. Conduct a comprehensive analysis of text quality:
   - Check spelling errors word by word
   - Analyze sentence structure completeness
   - Evaluate logical coherence
   - Identify culturally specific expressions
3. Perform layered revisions:
   - Basic layer: Correct spelling and grammatical errors
   - Optimization layer: Replace complex structures with clear expressions
   - Enhancement layer: Adjust terminology to be understandable for laypersons
4. Generate an improvement suggestion report:
   - Mark problematic areas according to original paragraphs
   - Provide 2-3 alternative options for each issue
   - Explain how the modifications enhance readability
5. Specially mark professional terms:
   - Identify terms that may cause comprehension difficulties
   - Provide a simplified explanation for each term
   - Suggest alternative everyday language
</instructions>

<output_format>
Output must include:
1. Complete revised text (with marked modifications)
2. Hierarchical improvement report table:
| Original Location | Problem Type | Modification Suggestion | Reason for Modification |
3. Professional terminology annotation list:
   - Term: original word
   - Difficulty Level: low/medium/high
   - Simplification Suggestion: alternative word + example sentence
4. Overall readability score (1-10 points)
</output_format>
</optimized_prompt>
```

中文：

```html 
<optimized_prompt>
<task>为非英语母语者优化文本的清晰度和正确性</task>

<context>
作为一名非英语母语人士，请帮我修改以下文本，以提高理解和清晰度。请检查拼写和句子结构错误，并提出替代方案。你有什么提升我文本清晰度的建议吗？请指出我写作中可能让普通读者难以理解的部分。
</context>

<instructions>
1. 接收用户提供的原始文本
2. 执行文本分析：
   - 识别拼写错误并进行标注
   - 检测语法结构问题并标记
   - 评估整体逻辑连贯性
3. 生成优化方案：
   - 提供修正后的完整文本版本
   - 对关键修改点进行注释说明
   - 创建替代表达方案（不少于三种）
4. 提供专业建议：
   - 指出可能导致理解障碍的具体段落
   - 分析原文中的文化语境问题
   - 给出日常写作提升方法
5. 确保优化方案：
   - 保持原作者的表达意图
   - 符合目标读者认知水平
   - 应用学术写作规范
</instructions>

<output_format>
1. 原始文本展示（用户提供后补充）
2. 优化后文本（完整呈现）
3. 修改说明（列表形式）：
   - 拼写修正：[原词] → [修正词]
   - 结构优化：[原句] → [优化句]
   - 替代方案：[原表达] → 方案1/方案2/方案3
4. 难点分析报告：
   - 理解障碍点定位（标注段落行号）
   - 文化语境冲突说明
   - 清晰度提升建议（分点陈述）
5. 格式要求：使用Markdown排版，关键修改处高亮显示
</output_format>
</optimized_prompt>
```

### 3.2 To make text more compelling（使文本更具吸引力）

英文：

```html
<optimized_prompt>
<task>Analyze the user's writing style and provide improvement suggestions to make it more persuasive and engaging, with a particular focus on optimizing the opening sentence.</task>

<context>
Please provide feedback on my writing style and how I can make it more persuasive and compelling for the grant reviewer. I’m trying to hook my reader with a strong introduction. Can you suggest a more captivating first sentence to draw them in from the start?
</context>

<instructions>
1. Analyze the current writing style:
   - Identify the tone, word choice, and sentence structure of the text
   - Evaluate the strengths and weaknesses of the current opening sentence
2. Suggest persuasive strategies:
   - Optimize language for the reviewer's psychological characteristics
   - Suggest methods to enhance emotional impact and authority
3. Design opening sentence optimization plan:
   - Create 5 different opening sentence styles:
     - Data-driven
     - Impact-driven
     - Vision-setting
     - Challenge-based
     - Personal narrative
   - Each option includes an application scenario
4. Provide overall structure optimization suggestions:
   - Paragraph rhythm adjustment plan
   - Key information emphasis techniques
   - Integration of evidence and argument
5. Provide specific modification examples:
   - Show the original opening sentence and the optimized version side by side
   - Explain the logic behind each modification
</instructions>

<output_format>
1. Style analysis report: Compare the current writing features with the target optimization direction using a table
2. Opening sentence proposal: Display 5 complete opening sentence options, each with:
   - The optimized sentence 
   - An application scenario (20-30 words)
   - An effect analysis (30-40 words)
3. Structure optimization suggestions: Display the three sub-sections (rhythm/key information/evidence)
4. Specific modification examples: Display the original text and the optimized text side by side, with the key modifications marked in **bold**
</output_format>
</optimized_prompt>
```

中文：

```html
<optimized_prompt>
<task>提供写作风格反馈并改进引言句子以增强说服力</task>

<context>
请对我的写作风格提供反馈，以及我如何能使其对资助评审者更具说服力和吸引力。我正在努力用一个强有力的引言吸引读者。你能建议一个更引人注目的开头句子来吸引他们吗？
</context>

<instructions>
1. 分析用户提供的写作风格内容
2. 提供具体反馈，包括：
   - 识别当前风格的强项和弱点
   - 评估其对资助评审者的吸引力和说服力
   - 提出改进建议以增强整体效果
3. 建议一个新的开头句子：
   - 基于资助评审者的偏好（如专业性和情感共鸣）
   - 确保引人注目并与主题相关
4. 解释建议的合理性：
   - 说明新句子如何提升吸引力和说服力
   - 提供优化理由，避免模糊描述
5. 总结整体风格改进策略
</instructions>

<output_format>
提供一个结构化的反馈报告，包含以下部分：
- 风格分析：概述当前写作风格的优缺点
- 具体改进建议：针对说服力和吸引力的详细建议
- 新引言句子示例：提供一个完整的、优化的开头句子
- 理由解释：说明新句子的优化点和预期效果
所有输出使用中文，确保清晰易读
</output_format>
</optimized_prompt>
```

### 3.3 To improve structure and flow of text（改善文本的结构和流畅性）

英文：

```html
<optimized_prompt>
<task>Provide suggestions for improving the structure of Specific Aims, organizational strategies for the Significance section, and feedback on research strategy processes.</task>

<context>
I want to improve the overall structure of my Specific Aims. What tips do you have to structure it more effectively? Can you recommend an effective way to organize my Significance section to highlight the innovative aspects of our approach? Please provide detailed feedback on the flow and sequence of my research strategy.
</context>

<instructions>
1. Analyze user needs and clarify three core feedback directions:
   - Overall structure optimization of Specific Aims
   - Significance section's innovation presentation strategy
   - Process and Sequence Evaluation of Research Strategies
2. Provide specific suggestions for the structure of Specific Aims:
   - Evaluate the typical problems existing in the current structure.
   - Recommended logical framework (such as problem-goal-solution)
   - Suggested paragraph transition techniques
3. Design an innovative presentation plan for the Significance section:
   - Identify the core innovative elements in research
   - Constructing contrast structures highlights the limitations of existing solutions.
   - Recommended visualization methods
4. Analyze the research strategy process and propose optimizations:
   - Evaluate the rationality of the current experimental sequence
   - Recommendation for setting phased milestones
   - Optimization of risk response plan description
5. Integrate all suggestions to form a complete feedback report.
</instructions>

<output_format>
Use a sectional structured output:
## Specific Aims Improvement Suggestions
[Use bullet points to list specific suggestions, including structural framework and transition techniques.]

## Significance innovation presentation plan
[Including innovative element extraction methods, comparative structural templates, and visual presentation examples.]

## Research strategy optimization feedback
[Analyze the current process according to the timeline, providing a phase division plan and risk assessment framework.]
</output_format>
</optimized_prompt>
```

中文：

```html
<optimized_prompt>
<task>请求提供目标结构优化、内容组织改进和研究策略评估的详细建议</task>

<context>
我想改进我的具体目标的整体结构。你有什么更有效地构建它的技巧吗？你能推荐一种有效的方式来组织我的重要性部分，以突出我们方法的创新方面吗？请对我的研究策略的流畅性和顺序提供详细反馈。
</context>

<instructions>
1. 目标结构优化建议：
   - 分析当前目标结构的逻辑层次和连贯性
   - 提出金字塔原理或SCQA框架的应用方案
   - 设计目标分解的可视化结构（如树状图/流程图）
   
2. 内容组织改进方案：
   - 识别创新点的核心要素
   - 制定重要性排序的矩阵模型（创新性×影响力）
   - 创建对比展示结构（传统方法 vs 创新方法）
   - 设计渐进式揭示框架（背景→痛点→创新方案）
   
3. 研究策略评估：
   - 分析方法论链条的衔接流畅度
   - 检测逻辑断层和冗余环节
   - 评估证据支撑的时序合理性
   - 提出关键路径优化方案
   
4. 综合交付：
   - 分别生成三个改进方案的可执行模板
   - 标注各环节的创新强化触发点
   - 提供AB测试实施路线图
</instructions>

<output_format>
采用三部分结构化输出：
1. 目标结构优化方案（含可视化示意图描述）
2. 创新点突出框架（含优先级矩阵和对比模板）
3. 研究策略诊断报告（含流程图优化建议和关键路径标记）
每个部分包含：问题分析→改进方案→实施步骤→预期效果
</output_format>
</optimized_prompt>
```
