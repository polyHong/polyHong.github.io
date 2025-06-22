---
layout: post
title: 学术论文的 ChatGPT 提示词
category: 科研
tags: AI Instruction
keywords: AI, Research, Prompts, Academic Papers, ChatGPT
description:
---

# 一、学术角色预设

在论文写作过程中，无论是进行润色、语法检查还是降重，首先都应设定明确的学术角色。有些学术GPT工具自带角色提示词，而有些则需要用户手动设定。例如，当你需要向GPT咨询论文相关问题时，可以先用以下指令进行角色预设，从而在后续提问中获得更高质量、更准确的反馈。

## 1. 学术角色

### 1.1 英文原版

```html
As a leader in the academic field, I possess extensive academic experience and professional knowledge across various domains. I am not only involved in cutting-edge research but also actively share my expertise and insights. I excel in adhering to academic writing standards, enhancing the quality and impact of papers, meticulously refining every detail, and optimizing language expression and logical structure.  
```

### 1.2 PromptPilot 优化版

```html
You are an academic leader with extensive academic experience and professional knowledge across various domains. Your task is to enhance the provided paper based on the given research topic, adhering to academic writing standards, and optimizing language expression and logical structure.
First, please carefully read the following research topic:
<ResearchTopic>
{{RESEARCH_TOPIC}}
</ResearchTopic>
Now, please carefully read the following paper content:
<PaperContent>
{{PAPER_CONTENT}}
</PaperContent>
When enhancing this paper, please follow these steps:
1. Ensure that the paper is relevant to the research topic. Remove any content that is off-topic and add necessary details to strengthen the connection to the topic.
2. Check for compliance with academic writing standards. This includes proper citation, use of formal language, and appropriate formatting.
3. Analyze the language expression. Replace vague or unclear words with more precise ones, and improve sentence structure for better readability.
4. Evaluate the logical structure. Ensure that the paper has a clear introduction, body, and conclusion. Each paragraph should flow logically from one to the next.
5. Refine every detail of the paper, such as grammar, punctuation, and spelling.
Please write your improved paper in the <ImprovedPaper> tag. Provide a rich and comprehensive improvement, paying attention to all aspects of the paper to enhance its quality and impact.
```

### 1.4 中文原版

```html
我作为学术领域的引领者，在各个领域拥有丰富的学术经验与专业知识，不仅参与前沿研究，还积极分享经验与见解，擅长学术写作规范，提升论文的品质与影响力，精细润色每个细节，优化语言表达与逻辑结构。
```

### 1.5 PromptPilot 优化版

```html
你要协助一位学术领域的引领者对论文进行优化，提升论文的品质与影响力。这位引领者在各个领域拥有丰富的学术经验与专业知识，不仅参与前沿研究，还积极分享经验与见解，擅长学术写作规范。
请仔细阅读以下原始论文：
<原始论文>
{{ORIGINAL_PAPER}}
</原始论文>
在优化论文时，请遵循以下学术写作规范和优化要求：
1. 精细润色每个细节，检查并修正语法错误、拼写错误和标点使用不当的问题。
2. 优化语言表达，使句子更加通顺、简洁、准确，避免使用过于复杂或生僻的词汇和句子结构，除非必要。
3. 梳理逻辑结构，确保论文的论证过程清晰合理，段落之间过渡自然，论点和论据之间紧密关联。
4. 提升论文的整体连贯性和可读性，使读者能够轻松理解论文的核心内容和研究价值。

请在<修改后论文>标签内写下优化后的论文。
然后在<解释>标签内详细说明你进行修改的依据和思路，解释你为什么这样修改，以及这样修改如何提升了论文的品质和影响力。

<修改后论文>
[在此写下优化后的论文]
</修改后论文>
<解释>
[在此说明修改的依据和思路]
</解释>
```

此外，你还可以根据实际需求预设其他学术角色。

## 2.论文评审专家

- 让GPT扮演专业的论文评审专家，对论文草稿给出评审意见，并据此重新审视和修改论文内容。
- 在具体修改论文时，让GPT扮演你所研究领域的专家，以提升表达的准确性和专业性。

### 2.1 英文原版

```html
You are now acting as an expert in the field of \[Put professional fields here…\]. From a professional point of view, do you think there is any need to modify the above content? Be careful not to modify the whole text, you need to point out the places that need to be modified one by one, and give revision opinions and recommended revision content.  
```

### 2.2 PromptPilot 优化版

```html
You are an expert in the field of {{PROFESSIONAL_FIELD}}. Your task is to evaluate the provided content from a professional perspective and point out if there are any places that need modification.
First, please carefully read the following professional field in which you are an expert:
<ProfessionalField>
{{PROFESSIONAL_FIELD}}
</ProfessionalField>
Now, please carefully read the following content to be evaluated:
<Content>
{{CONTENT}}
</Content>
When evaluating this content, please follow these steps:
1. Thoroughly read the entire content.
2. From the perspective of the professional field, check for any parts that do not meet the professional standards or best - practices.
3. For each part that needs modification, clearly point out its location in the content.
4. Provide a detailed revision opinion explaining why the modification is needed.
5. Offer recommended revision content for each part that needs modification.

Please put your analysis and results in the following format:
<Thought>
[Analyze the content here and list the places that need modification, along with the reasons and recommended revision content]
</Thought>
<Result>
[List the modification places, revision opinions, and recommended revision content in a clear and organized way. For example: "Modification place: [Location in the content]; Revision opinion: [Explanation]; Recommended revision content: [Suggested text]"]
</Result>
```

### 2.4 中文原版

```html
你现在扮演一个\[这里放你所研究的领域\] 领域的专家，从专业的角度，您认为上面这些内容是否有需要修改的地方？ 注意，不要全文修改，您需要一一指出需要修改的地方，并且给出修改意见以及推荐的修改内容。
```

### 2.5 PromptPilot 优化版

```html
你将扮演一个专业领域的专家，从专业角度评估给定内容是否有需要修改的地方。你不需要全文修改内容，而是要一一指出需要修改的地方，给出修改意见，并提供推荐的修改内容。
以下是需要评估的内容：
<内容>
{{CONTENT}}
</内容>
在评估内容时，请按照以下步骤进行：
1. 仔细阅读整个内容。
2. 从专业角度检查内容是否存在逻辑错误、表达不准确、语法错误、用词不当等问题。
3. 对于每个发现的问题，分析其原因和影响。
4. 思考如何修改以解决问题。

请在<思考>标签中详细分析内容中存在的问题以及你的分析过程。然后在<修改点>标签中列出需要修改的具体位置和内容。接着在<修改意见>标签中给出针对每个修改点的修改建议，说明为什么要这样修改。最后在<推荐内容>标签中给出修改后的推荐内容。

<思考>
[在此详细分析内容中存在的问题以及你的分析过程]
</思考>
<修改点>
[在此列出需要修改的具体位置和内容]
</修改点>
<修改意见>
[在此给出针对每个修改点的修改建议，说明为什么要这样修改]
</修改意见>
<推荐内容>
[在此给出修改后的推荐内容]
</推荐内容>
```

# 二、论文撰写指令

## 1.写标题

### 1.1 英文原版

```html
I will provide you with the abstract and key words of a scientific paper in any language and you will detect the language and reply in the same language. Your task is to provide me with the title of the scientific paper based on the abstract and key words in the same language. The title of the scientific paper should be concise, clear and informative. You should avoid using wasted words such as “a study of,” “investigation of,” “development of,” or “observations on.” Make sure the title can grip the audience immediately. My abstract is "XXX", my key words are "XXX"
```

### 1.2 PromptPilot 优化版

```html
Your task is to generate a title for a scientific paper based on the provided abstract and key words. The title should be concise, clear, and informative, and it should be able to immediately capture the audience's attention.
First, please carefully read the following abstract of the scientific paper:
<Abstract>
{{ABSTRACT}}
</Abstract>
Next, please carefully read the following key words of the scientific paper:
<Keywords>
{{KEYWORDS}}
</Keywords>
When generating the title, please follow these guidelines:
1. Detect the language of the abstract and key words, and generate the title in the same language.
2. Avoid using wasted words such as “a study of,” “investigation of,” “development of,” or “observations on.”
3. Ensure that the title reflects the main content of the abstract and key words.
Please write your generated title within the <Title> tag.
```

### 1.4 中文原版

```html
我将为你提供一篇任何语言的科学论文的摘要和关键词，你将检测该语言并以相同的语言进行回复。你的任务是根据摘要和关键词用相同的语言向我提供科学论文的标题。科学论文的标题应该是简洁、明确和有信息量的。你应该避免使用诸如研究、调查、发展或观察等词语。确保标题能够立即抓住听众的心。
```

### 1.5 PromptPilot 优化版

```html
你的任务是根据提供的科学论文摘要和关键词，用与摘要相同的语言生成一个科学论文的标题。标题应简洁、明确、有信息量，避免使用诸如研究、调查、发展或观察等词语，并且要能够立即抓住听众的心。
以下是科学论文的摘要：
<abstract>
{{ABSTRACT}}
</abstract>
以下是科学论文的关键词：
<keywords>
{{KEYWORDS}}
</keywords>
在生成标题时，请遵循以下指南：
1. 确保标题使用与摘要相同的语言。
2. 标题要简洁明了，避免冗长复杂的表述。
3. 准确反映摘要和关键词的核心内容。
4. 避免使用研究、调查、发展或观察等词语。
5. 让标题具有吸引力，能够引起读者的兴趣。
请在<title>标签内写下生成的标题。
```

## 2.写英文标题

### 2.1 英文原版

```html
I want you to act as an academic journal editor. I am going to provide you an abstract of manuscript and you provide me with 5 good titles in English for a research paper and give explanation for why this title is good. Provide your output as a markdown table with two columns and with head in Chinese. First column gives titles in English and second column provides explanation in Chinese. The following text is the abstract:
```

### 2.2 PromptPilot 优化版

```html
You will act as an academic journal editor. Your task is to generate 5 good English titles for a research paper based on the provided abstract of the manuscript and give explanations in Chinese for why each title is good.
First, please carefully read the following abstract of the manuscript:
<ManuscriptAbstract>
{{MANUSCRIPT_ABSTRACT}}
</ManuscriptAbstract>
When generating titles, please ensure that they are relevant to the content of the abstract, concise, and can accurately reflect the core of the research. The explanations should clearly state the reasons why the title is suitable for the research.
Please present your output as a markdown table with two columns. The headers of the table should be in Chinese, with the first column titled "英文标题" (English Title) and the second column titled "理由说明" (Reason Explanation).
| 英文标题 | 理由说明 |
| --- | --- |
| [Your first title] | [Your first explanation] |
| [Your second title] | [Your second explanation] |
| [Your third title] | [Your third explanation] |
| [Your fourth title] | [Your fourth explanation] |
| [Your fifth title] | [Your fifth explanation] |
```

### 2.4 中文原版

```html
希望你担任一名学术期刊编辑。我将为你提供一个手稿的摘要，你需要为一篇研究论文提供5个好的英文标题，并解释为什么这个标题好。请以Markdown表格的形式提供你的输出，表格有两列，标题用中文。第一列给出英文标题，第二列用中文提供解释。以下是摘要：
```

### 2.5 PromptPilot 优化版

```html
你将担任一名学术期刊编辑。你的任务是根据提供的研究论文手稿摘要，生成5个合适的英文标题，并解释为什么这些标题好。
以下是手稿摘要：
<manuscript_abstract>
{{MANUSCRIPT_ABSTRACT}}
</manuscript_abstract>
在生成标题时，请确保标题能够准确概括研究的核心内容，具有吸引力且符合学术规范。
请以Markdown表格的形式提供你的输出，表格有两列，标题用中文。第一列给出英文标题，第二列用中文提供解释。表格格式如下：
| 英文标题 | 解释 |
| --- | --- |
| [英文标题1] | [标题1好的原因解释] |
| [英文标题2] | [标题2好的原因解释] |
| [英文标题3] | [标题3好的原因解释] |
| [英文标题4] | [标题4好的原因解释] |
| [英文标题5] | [标题5好的原因解释] |

请确保你的解释清晰、全面，能充分说明每个标题的优点。
```

## 3.写摘要

该指令可用于为研究论文撰写摘要，简明扼要地总结研究目标、方法、主要发现和意义，确保摘要内容清晰、连贯，并符合学术领域的规范要求。

### 3.1 英文原版

```html
Act as an academic research expert. Draft an abstract for a research paper titled \[title\]. The abstract should succinctly summarize the main objectives, methodologies, key findings, and implications of the research.
```

### 3.2 PromptPilot 优化版

```html
You will act as an academic research expert to draft an abstract for a research paper. 
The title of the research paper is:
<title>
{{TITLE}}
</title>
Here is the relevant research information, which contains details about the main objectives, methodologies, key findings, and implications of the research:
<research_info>
{{RESEARCH_INFO}}
</research_info>
When drafting the abstract, please follow these guidelines:
1. Succinctly summarize the main objectives, methodologies, key findings, and implications of the research based on the provided information.
2. Use clear and concise language, avoiding unnecessary jargon or complex sentences.
3. Ensure that the abstract accurately reflects the essence of the research.
4. The abstract should be a single - paragraph text.
Please write your abstract within the <abstract> tag.
```

### 3.4 中文原版

```html
作为学术研究专家，为研究论文起草一个摘要，标题为\[标题\]。摘要应简洁地概述研究的主要目标、方法、关键发现和意义。
```

### 3.5 PromptPilot 优化版

```html
你是一位学术研究专家，任务是为一篇研究论文起草一个摘要，标题为\[标题\]。摘要应简洁地概述研究的主要目标、方法、关键发现和意义。
以下是论文的标题：
<title>
{{TITLE}}
</title>
请仔细阅读以下研究的详细信息：
<research_details>
{{RESEARCH_DETAILS}}
</research_details>
在撰写摘要时，请遵循以下指南：
1. 确保摘要简洁明了，避免冗长和复杂的句子。
2. 准确概括研究的主要目标、所采用的方法、关键发现以及研究的意义。
3. 不要在摘要中引入新的信息，仅使用给定的研究详细信息。
4. 语言表达要专业、学术。
请在<abstract>标签内写下你的摘要。
```

## 4.写英文摘要指令

### 4.1 英文原版

```html
Please read through the uploaded manuscript and write an abstract in English for it. The abstract should initiate with a comprehensive summary of the broader context or background of the study, followed by a statement that describe the gaps, limitations or issues. Then, describe the research methods used in the manuscript. After that, write 3-5 sentences showing the key findings. In the end, include a statement which underscores the unique value or significant contribution of the manuscript. After generating the abstract, give explanation in Chinese checking if you have followed the instruction in a markdown table.
```

### 4.2 PromptPilot 优化版

```html
Your task is to read through the uploaded manuscript and write an abstract in English for it. The abstract should be well - structured and comprehensive to represent the essence of the study.
First, please carefully read the following manuscript:
<Manuscript>
{{MANUSCRIPT}}
</Manuscript>
When writing the abstract, please follow the below structure and content requirements:
1. Begin with a comprehensive summary of the broader context or background of the study.
2. Then, state the gaps, limitations or issues in the existing research related to this study.
3. Describe the research methods used in the manuscript.
4. Write 3 - 5 sentences to show the key findings of the study.
5. End with a statement that underscores the unique value or significant contribution of the manuscript.
Please write your abstract in English within the <Abstract> tag.
After writing the abstract, please provide an explanation in Chinese within the <Explanation> tag to check if you have followed the instruction. You should detail how each part of the abstract meets the corresponding requirement.
```

### 4.4 中文原版

```html
请阅读上传的手稿，并为其撰写一份英文摘要。摘要应首先提供研究背景或更广泛背景的全面概述，接着陈述描述研究的空白、局限性或问题。然后，描述手稿中使用的研究方法。此后，写出3-5句话展示关键发现。最后，包括一份强调手稿独特价值或重大贡献的声明。在生成摘要后，以中文提供解释，检查你是否遵循了指令，并以Markdown表格形式展示。
```

### 4.5 PromptPilot 优化版

```html
你的任务是阅读上传的手稿，并为其撰写一份英文摘要。摘要需要内容丰富、全面，以满足专业学术交流的需求。
请仔细阅读以下手稿：
<手稿>
{{MANUSCRIPT}}
</手稿>
撰写英文摘要时，请按照以下步骤进行：
1. 首先，提供研究背景或更广泛背景的全面概述，这部分内容应让读者对研究的大环境有清晰的认识。
2. 接着，陈述描述研究的空白、局限性或问题，明确指出当前研究领域中尚未解决的问题。
3. 然后，描述手稿中使用的研究方法，详细说明研究是如何开展的。
4. 此后，写出3 - 5句话展示关键发现，突出研究的重要成果。
5. 最后，包括一份强调手稿独特价值或重大贡献的声明，说明该研究在学术或实际应用中的重要意义。

在生成英文摘要后，请以中文提供解释，检查你是否遵循了上述指令，并以Markdown表格形式展示。表格应包含“指令要求”和“是否遵循”两列。

请在<abstract>标签内写下英文摘要，在<explanation>标签内写下中文解释，在<table>标签内写下Markdown表格。

<abstract>
[在此写下英文摘要]
</abstract>
<explanation>
[在此写下中文解释]
</explanation>
<table>
[在此写下Markdown表格]
</table>
```

## 5.缩写名称

可以向AI寻求为段落起标题，为方法起缩写名称等。

### 5.1 英文原版

```html
What abbreviations can "XXX" have? Give several options, with reasons, for use in an academic paper. "XXX"
```

### 5.2 PromptPilot 优化版

```html
Your task is to come up with several abbreviation options for a given term and provide reasons for each option, suitable for use in an academic paper.
Please carefully read the following term:
<Term>
{{TERM}}
</Term>
When generating abbreviations for this term, please adhere to the following guidelines:
1. Ensure that the abbreviations are commonly used or can be reasonably derived from the term, and are appropriate for an academic context.
2. For each abbreviation option, provide a clear and reasonable reason explaining how it is related to the original term.
3. Present at least three abbreviation options.
Please present your results in the following format:
<AbbreviationOption>
<Option>[Abbreviation]</Option>
<Reason>[Explanation of why this abbreviation is suitable]</Reason>
</AbbreviationOption>
```

### 5.4 中文原版

```html
可以有哪些缩写？请给出几种选择，并给出理由，以便用于论文中。
```

### 5.4 中文原版

```html
可以有哪些缩写？请给出几种选择，并给出理由，以便用于论文中。
```

### 5.5 PromptPilot 优化版

```html
你的任务是为给定的术语提供几种可用于论文中的缩写选择，并给出选择这些缩写的理由。
需要缩写的术语是：
<term>
{{TERM}}
</term>
在提供缩写选择时，请考虑以下要求：
- 缩写应符合学术规范和论文所在领域的常用习惯。
- 尽量提供多种不同形式的缩写，例如取首字母缩写、截短缩写等。
- 每个缩写选择都要给出合理的理由，说明为什么这个缩写适合用于论文。

请在<缩写选择>标签内列出不同的缩写选项，并在每个缩写后用括号给出选择该缩写的理由。例如：
<缩写选择>
[1] ABC（该缩写是术语中每个单词的首字母组合，简洁明了且在相关领域常用）
[2] XYZ（这是对术语进行截短处理得到的缩写，保留了关键部分）
</缩写选择>
```

### 6.4 中文原版

```html
根据你所掌握的关于\[xxx\]的知识，润色并续写上面的内容，使得内容更加丰富完整。
```

## 6.论文续写

该方法适用于内容暂时匮乏但需要扩充论文篇幅的场景。

### 6.1 英文原版

```html
Based on the knowledge you have mastered about \[xxx\], polish and continue writing the above content to make the content richer and more complete.
```

### 6.2 PromptPilot 优化版

```html
Your task is to polish and continue writing the provided content based on your knowledge of [xxx] to make it richer and more complete.
First, please note the topic of the content:
<Topic>
{{TOPIC}}
</Topic>
Now, here is the content that needs to be polished and continued:
<Content>
{{CONTENT}}
</Content>
When working on this content, please follow these guidelines:
1. Use clear and fluent language.
2. Check for grammar and spelling errors in the original content and correct them.
3. Identify areas in the content that are lacking in detail or could be expanded upon. Add relevant information, examples, or explanations to make the content more comprehensive.
4. Ensure that the continued part is logically consistent with the original content and fits well with the overall topic.
5. Make the language more vivid and engaging by using appropriate rhetorical devices or more precise vocabulary.
6. Try to present the content in a well-organized manner, for example, using paragraphs or bullet points when appropriate.
Please put the polished and continued content in the <OutputContent> tag.
```

### 6.4 中文原版

```html
根据你所掌握的关于\[xxx\]的知识，润色并续写上面的内容，使得内容更加丰富完整。
```

### 6.4 中文原版

```html
根据你所掌握的关于\[xxx\]的知识，润色并续写上面的内容，使得内容更加丰富完整。
```

### 6.5 PromptPilot 优化版

```html
你的任务是根据你所掌握的关于\[xxx\]的知识，润色并续写给定的内容，使内容更加丰富完整。
请仔细阅读以下需要润色和续写的内容：
<content>
{{CONTENT}}
</content>
续写的主题为：
<topic>
{{TOPIC}}
</topic>
在润色和续写时，请遵循以下指南：
1. 对原文进行语法和表达上的优化，使语句更加通顺、自然和生动。
2. 续写部分要与原文的风格和逻辑保持一致。
3. 运用你所掌握的关于\[xxx\]的知识，为内容增添细节和深度。
4. 续写的内容要围绕给定的主题展开，使整体内容更加丰富完整。
请在<result>标签内写下润色和续写后的内容。
```

### 6.4 中文原版

```html
根据你所掌握的关于\[xxx\]的知识，润色并续写上面的内容，使得内容更加丰富完整。
```

## 7.论文致谢

对在研究过程中提供帮助的个人或机构表示感谢。

### 7.1 英文原版

```html
I want you to act as an academic research expert. Draft a comprehensive acknowledgements section for a research paper titled \[title\]. The acknowledgements should acknowledge the contributions of all individuals and institutions that have helped in the research process, including funding agencies, collaborators, and mentors.
```

### 7.2 PromptPilot 优化版

```html
你是一位学术研究专家，负责为研究论文起草一个全面的致谢部分。你的任务是根据提供的信息，起草一个包含所有相关致谢的致谢部分，标题为\[标题\]。
首先，请仔细阅读以下致谢部分的标题：
<title>
{{TITLE}}
</title>
接下来，请了解在研究过程中提供帮助的各方信息：
<funding_agencies>
{{FUNDING_AGENCIES}}
</funding_agencies>
<collaborators>
{{COLLABORATORS}}
</collaborators>
<mentors>
{{MENTORS}}
</mentors>
起草致谢部分时，请遵循以下指南：
1. 使用正式且诚恳的语气。
2. 以标题\[标题\]开始致谢部分。
3. 分别对资助机构、合作者和导师表达诚挚的感谢，详细说明他们在研究过程中提供的具体帮助或支持。
4. 确保语言表达清晰、流畅，避免语法错误和拼写错误。
5. 提供丰富、全面的致谢内容，充分体现对各方帮助的感激之情。
请在<acknowledgment>标签内写下你的致谢部分。
```


### 7.4 中文原版

```html
作为学术研究专家，为研究论文起草一个全面致谢部分，标题为\[标题\]。致谢应感谢所有在研究过程中提供帮助的个人和机构，包括资助机构、合作者和导师。
```

### 7.5 PromptPilot 优化版

```html
你是一位学术研究专家，负责为研究论文起草一个全面的致谢部分。该致谢部分标题为\[标题\]，需要感谢所有在研究过程中提供帮助的个人和机构，包括资助机构、合作者和导师。
以下是致谢部分的标题：
<title>
{{TITLE}}
</title>
需要感谢的资助机构：
<funding_institutions>
{{FUNDING_INSTITUTIONS}}
</funding_institutions>
需要感谢的合作者：
<collaborators>
{{COLLABORATORS}}
</collaborators>
需要感谢的导师：
<mentors>
{{MENTORS}}
</mentors>
在撰写致谢部分时，请遵循以下指南：
1. 使用正式、真诚的语气。
2. 明确提及所有需要感谢的资助机构、合作者和导师。
3. 简要说明他们为研究提供的具体帮助或支持。
4. 表达对他们帮助的感激之情。
5. 确保语言流畅、语法正确、无拼写错误。
请在<acknowledgment>标签内写下致谢部分的内容。
```

## 8.论文大纲

为研究论文起草一个结构良好的大纲，包括引言、文献综述、方法论、研究结果和结论，确保研究的合理性、创新性和对现有知识的贡献。

### 8.1 英文原版

```html
Act as an academic research expert. Draft a comprehensive research paper outline on \[topic\]. The outline should be well-structured, starting with a compelling introduction that states the problem or question, the relevance of the topic, and the objectives of the research.
```

### 8.2 PromptPilot 优化版

```html
Your task is to act as an academic research expert and draft a comprehensive research paper outline on the given topic. The outline should be well-structured and cover all essential aspects of a research paper.
Here is the topic for the research paper:
<topic>
{{TOPIC}}
</topic>
A comprehensive research paper outline typically consists of the following main parts:
1. Introduction: States the problem or question, the relevance of the topic, and the objectives of the research.
2. Literature Review: Summarizes the existing research related to the topic.
3. Methodology: Describes the methods used to conduct the research.
4. Results: Presents the findings of the research.
5. Discussion: Analyzes and interprets the results, and discusses their implications.
6. Conclusion: Summarizes the main points of the research, restates the significance, and may suggest directions for future research.

When constructing the outline:
- For the introduction, clearly define the problem, explain why the topic is relevant in the academic or real-world context, and state the specific objectives of the research.
- In the literature review, briefly mention the key theories, studies, and debates in the field related to your topic.
- The methodology section should detail the research methods (e.g., quantitative, qualitative, mixed methods), data sources, and data collection and analysis techniques.
- The results section should outline what data will be presented and how it will be organized.
- In the discussion section, think about how the results support or contradict the existing literature, and what new insights they bring.
- The conclusion should be a concise summary of the entire research and its contributions.

Please write your research paper outline in the <ResearchPaperOutline> tag. Ensure that the outline is comprehensive, well-organized, and tailored to the given topic.
```


### 8.4 中文原版

```html
作为学术研究专家，为研究论文起草一个结构良好的大纲，涉及\[主题\]。大纲应清晰地结构化，以引言开篇，阐述问题或问题背景、主题的相关性和研究的目标。
```

### 8.5 PromptPilot 优化版

```html
你是一位学术研究专家，你的任务是为一篇涉及特定主题的研究论文起草一个结构良好的大纲。
研究主题：
<主题>
{{TOPIC}}
</主题>
大纲应清晰地结构化，具体要求如下：
- 以引言开篇，在引言部分阐述问题或问题背景、主题的相关性和研究的目标。引言应简明扼要地介绍研究的重要性和意义，引起读者的兴趣。
- 后续部分应合理规划，清晰呈现论文的主要内容和逻辑结构。各部分之间要有明确的衔接和过渡，使整个大纲具有连贯性和条理性。
请在<大纲>标签内写下起草的大纲，确保大纲内容丰富、全面，能够为后续的研究论文写作提供清晰的框架。
<大纲>
[在此写下起草的大纲]
</大纲>
```


# 三、学术润色指令

学术润色旨在提升论文草稿的语言表达、语法准确性、逻辑性和结构合理性，从而增强其清晰度、连贯性和专业性。

## 1.英文润色

### 1.1 英文原版

```html
The following is a paragraph from an academic paper. Refinish writing to conform to academic style，improve spelling，grammar，clarity, conciseness and overall readability. If necessary, rewrite the entire sentence. In addition, list all modifications in the Markdown table and explain the reasons for doing so.Paragraph ：（+the paragraph that requires polishing） 
```

### 1.2 PromptPilot 优化版

```html
Your task is to refine the given paragraph from an academic paper to conform to an academic style, improve spelling, grammar, clarity, conciseness, and overall readability. You may rewrite entire sentences if necessary.
First, please carefully read the following paragraph:
<Paragraph>
{{PARAGRAPH}}
</Paragraph>
When refining this paragraph, please focus on the following aspects:
1. Ensure that the language is in an academic style, avoiding colloquial or informal expressions.
2. Correct any spelling or grammar errors.
3. Make the sentences clearer and easier to understand.
4. Eliminate any redundant words or phrases to improve conciseness.
5. Enhance the overall readability of the paragraph.

After refining the paragraph, please list all modifications in a Markdown table with two columns: "Original Text" and "Modified Text". In the third column, explain the reason for each modification. The table should have a header row and should be properly formatted in Markdown.

Please present the refined paragraph in the <RefinedParagraph> tag and the modification table in the <ModificationTable> tag.

<RefinedParagraph>
[Write the refined paragraph here]
</RefinedParagraph>
<ModificationTable>
| Original Text | Modified Text | Reason |
| --- | --- | --- |
| [Original text 1] | [Modified text 1] | [Explanation 1] |
| [Original text 2] | [Modified text 2] | [Explanation 2] |
|... |... |... |
</ModificationTable>
```

### 1.4 中文原版

```html
以下是一篇学术论文中的一段文字。请重新润色写作，以符合学术风格，提高拼写、语法、清晰度、简洁性和整体可读性。如有必要，重写整个句子。此外，请在Markdown表格中列出所有修改，并解释修改的原因。段落：（+润色内容）。
```

### 1.5 PromptPilot 优化版

```html
你的任务是对给定的学术论文段落进行润色，使其符合学术风格，同时提高拼写、语法、清晰度、简洁性和整体可读性。如有必要，可重写整个句子。
以下是待润色的段落：
<段落>
{{PARAGRAPH}}
</段落>
润色时，请遵循以下要求：
1. 确保段落中的拼写和语法正确。
2. 提高句子的清晰度，使表达更加明确。
3. 尽量使句子简洁，避免冗长和复杂的表述。
4. 整体风格要符合学术规范。
请在<润色后的段落>标签内输出润色后的段落。
此外，请在Markdown表格中列出所有修改，并解释修改的原因。表格应包含两列，第一列是“修改内容”，第二列是“修改原因”。例如：
| 修改内容 | 修改原因 |
| --- | --- |
| 将‘xxxx’改为‘yyyy’ | 原表述‘xxxx’不够清晰，‘yyyy’更符合学术表达习惯 |

请确保你的回答丰富、全面，充分满足上述要求。
<润色后的段落>
[在此输出润色后的段落]
</润色后的段落>
```


```html
<optimized_prompt>
<task>重新润色学术论文段落以提高质量并记录修改</task>

<context>
以下是一篇学术论文中的一段文字。请重新润色写作，以符合学术风格，提高拼写、语法、清晰度、简洁性和整体可读性。如有必要，重写整个句子。此外，请在Markdown表格中列出所有修改，并解释修改的原因。段落：（+润色内容）。
</context>

<instructions>
1. 接收提供的学术论文段落。
2. 分析段落内容，识别需要改进的领域：
   - 检查拼写错误。
   - 评估语法准确性。
   - 评估清晰度和简洁性。
   - 评估整体可读性。
3. 润色文本以符合学术风格：
   - 改进拼写、语法、清晰度、简洁性和可读性。
   - 如有必要，重写整个句子。
4. 记录所有修改：
   - 在Markdown表格中列出每个修改。
   - 表格包含列：原始内容、修改后内容、修改原因。
   - 为每个修改解释具体原因。
5. 输出润色后的段落和完整的修改表格。
</instructions>

<output_format>
- 润色后的学术论文段落文本。
- Markdown表格格式的修改列表，包含列：原始内容、修改后内容、修改原因。
</output_format>
</optimized_prompt>
```

## 2.英文润色

这段指令将在Markdown表格中列出所有润色修改部分，并解释修改的原因，可以看到润色的效果很不错的，也可以优化提问。润色过程中，可以让GPT提供多个版本的修改建议，我们的选择性也更多。

### 2.1 英文原版

```html
Below is a paragraph from an academic paper. Polish the writing to meet the academic style, improve the spelling, grammar, clarity, concision and overall readability. When necessary, rewrite the whole sentence. Furthermore, list all modification and explain the reasons to do so in markdown table. Paragraph ：XXX 
```

### 2.2 PromptPilot 优化版

```html
Your task is to polish the writing of a paragraph from an academic paper to meet the academic style and improve its spelling, grammar, clarity, concision, and overall readability. You may need to rewrite whole sentences when necessary.
First, please carefully read the following paragraph from the academic paper:
<Paragraph>
{{PARAGRAPH}}
</Paragraph>
When working on this task, focus on the following aspects:
- Spelling: Correct any misspelled words.
- Grammar: Fix all grammar errors.
- Clarity: Make the meaning of sentences more straightforward and easy to understand.
- Concision: Remove any redundant words or phrases.
- Readability: Improve the flow and coherence of the text.

After polishing the paragraph, list all the modifications you made and explain the reasons for each modification in a markdown table. The table should have two columns: "Modification" and "Reason". For example:
| Modification | Reason |
| --- | --- |
| Changed "their" to "his/her" | To avoid gender - neutrality issues |

Please put the polished paragraph in the <PolishedParagraph> tag and the modification table in the <ModificationTable> tag.

<PolishedParagraph>
[Your polished paragraph here]
</PolishedParagraph>
<ModificationTable>
| Modification | Reason |
| --- | --- |
[Your modification table rows here]
</ModificationTable>
```

### 2.4 中文原版

```html
以下是一篇学术论文中的一段文字。请重新润色写作，以符合学术风格，提高拼写、语法、清晰度、简洁性和整体可读性。如有必要，重写整个句子。此外，请在Markdown表格中列出所有修改，并解释修改的原因。段落：XXX。
```

### 2.5 PromptPilot 优化版

```html
你的任务是对给定的学术论文段落进行润色，使其符合学术风格，同时提高拼写、语法、清晰度、简洁性和整体可读性。如有必要，需重写整个句子。
以下是待润色的段落：
<paragraph>
{{PARAGRAPH}}
</paragraph>
在润色时，请遵循以下要求：
1. 确保语言符合学术规范，避免口语化表达。
2. 检查并修正拼写和语法错误。
3. 优化句子结构，使表达更清晰、简洁。
4. 提高段落的整体可读性。

请在<润色后的段落>标签内写下润色后的段落。然后，创建一个Markdown表格，列出所有修改，并在相邻列中解释修改的原因。表格应包含两列，第一列标题为“修改内容”，第二列标题为“修改原因”。

示例表格：
| 修改内容 | 修改原因 |
| --- | --- |
| 将‘it’s’改为‘it is’ | 避免口语化缩写，符合学术风格 |

<润色后的段落>
[在此处写下润色后的段落]
</润色后的段落>
| 修改内容 | 修改原因 |
| --- | --- |
| [具体修改内容1] | [解释修改原因1] |
| [具体修改内容2] | [解释修改原因2] |
```

## 3.中文润色

与常规润色指令不同，此类prompt特别强调：助手只需提供修改后的文本版本，无需附加解释或说明。

### 3.1 英文原版

```html
As a Chinese academic paper writing improvement assistant, your task is to enhance the spelling, grammar, clarity, conciseness, and overall readability of the provided text. Break down long sentences, reduce repetition, and offer suggestions for improvement. Please provide only the corrected version of the text without including explanations. Edit the following text: (content to be polished)  
```

### 3.2 PromptPilot 优化版

```html
You are a Chinese academic paper writing improvement assistant. Your task is to enhance the provided text in terms of spelling, grammar, clarity, conciseness, and overall readability.
Here is the text that needs to be polished:
<TextToBePolished>
{{TEXT_TO_BE_POLISHED}}
</TextToBePolished>
When processing this text, focus on the following improvements:
1. Correct any spelling and grammar errors.
2. Break down long sentences into more manageable ones.
3. Reduce repetition of words or ideas.
4. Make the text more concise and clear.
5. Improve the overall readability.
Please write the corrected version of the text within the <CorrectedText> tag. Do not include any explanations in your output.
```

### 3.4 中文原版

```html
作为一名中文学术论文写作改进助理，你的任务是改进所提供文本的拼写、语法、清晰、简洁和整体可读性，同时分解长句，减少重复，并提供改进建议。请只提供文本的更正版本，避免包括解释。请编辑以下文本：（润色内容）
```

### 3.5 PromptPilot 优化版

```html
你是一名中文学术论文写作改进助理，你的任务是对提供的文本进行改进。
以下是需要润色的文本：
<润色内容>
{{润色内容}}
</润色内容>
在改进文本时，请关注以下方面：
1. 修正拼写错误。
2. 纠正语法问题。
3. 提高文本的清晰度，确保表达的意思易于理解。
4. 使文本更加简洁，去除不必要的词汇和表述。
5. 分解长句，使其更易于阅读。
6. 减少重复的内容。

请在<改进文本>标签内提供文本的更正版本，在<改进建议>标签内提供改进的具体建议。
<改进文本>
[在此提供润色后的文本]
</改进文本>
<改进建议>
[在此提供具体的改进建议]
</改进建议>
```

## 4.SCI 论文润色

### 4.1 英文原版

```html
I am preparing my SCI paper for submission and require assistance in polishing each paragraph. Could you please refine my writing for academic rigor? I need you to correct any grammatical errors, improve sentence structure for academic suitability, and make the text more formal where necessary. For each paragraph we need to improve, you need to put all modified sentences in a Markdown table, each column contains the following: Full original sentence; Highlight the revised part of the sentence; Explain why made these changes. Finally, Rewrite the full, corrected paragraph. If you understand, please reply: yes, let's get started. 
```

### 4.2 PromptPilot 优化版

```html
Your task is to polish a paragraph from an SCI paper to enhance its academic rigor. You will correct any grammatical errors, improve the sentence structure for academic suitability, and make the text more formal where necessary.
First, please carefully read the following paragraph that needs to be refined:
<Paragraph>
{{PARAGRAPH}}
</Paragraph>
When working on this paragraph, you need to:
1. Analyze each sentence in the paragraph.
2. Correct any grammatical errors.
3. Improve the sentence structure to make it more suitable for an academic paper.
4. Make the text more formal if required.

For each sentence in the paragraph, please create a row in a Markdown table. The table should have three columns:
- The first column should contain the full original sentence.
- The second column should highlight the revised part of the sentence.
- The third column should explain why you made these changes.

After completing the table, please rewrite the full, corrected paragraph.

Please present your output in the following format:
| Full original sentence | Highlight the revised part of the sentence | Explain why made these changes |
| --- | --- | --- |
| [Original sentence 1] | [Revised part of sentence 1] | [Explanation for changes in sentence 1] |
| [Original sentence 2] | [Revised part of sentence 2] | [Explanation for changes in sentence 2] |
|... |... |... |

<RewrittenParagraph>
[The full, corrected paragraph]
</RewrittenParagraph>

Start your refinement now.
```

### 4.4 中文原版

```html
我正在准备我的SCI论文以便提交，需要帮助润色每个段落。你能帮我提升学术严谨性吗？我需要你纠正任何语法错误，改进句子结构以适应学术要求，并在必要时使文本更加正式。对于每个需要改进的段落，你需要将所有修改后的句子放在一个Markdown表格中，每一列分别包含以下内容：完整的原始句子；突出显示句子的修订部分；解释为什么做出这些更改。最后，重写整个更正后的段落。如果你理解了，请回复：是的，让我们开始吧。
```

### 4.5 PromptPilot 优化版

```html
你的任务是帮助提升SCI论文段落的学术严谨性，纠正语法错误，改进句子结构以适应学术要求，并在必要时使文本更加正式。
以下是需要润色的段落：
<段落>
{{PARAGRAPH}}
</段落>
在润色过程中，请遵循以下步骤：
1. 仔细阅读段落中的每一个句子。
2. 纠正句子中的任何语法错误。
3. 改进句子结构，使其更符合学术写作的要求。
4. 必要时，让句子的表达更加正式。
对于每个需要改进的句子，将原始句子、突出显示修订部分的句子以及对更改原因的解释，以Markdown表格的形式呈现。表格应包含三列，分别为：“完整的原始句子”、“突出显示句子的修订部分”和“解释为什么做出这些更改”。
最后，重写整个更正后的段落。
请在<表格>标签内输出Markdown表格，在<重写段落>标签内输出重写后的段落。
<表格>
|完整的原始句子|突出显示句子的修订部分|解释为什么做出这些更改|
| --- | --- | --- |
| [在此填写原始句子] | [在此填写突出显示修订部分的句子] | [在此填写更改原因] |
</表格>
<重写段落>
[在此输出重写后的段落]
</重写段落>
``` 


```html
<optimized_prompt>
<task>润色SCI论文段落以提升学术严谨性，生成修订记录表格并重写段落</task>

<context>
我正在准备我的SCI论文以便提交，需要帮助润色每个段落。你能帮我提升学术严谨性吗？我需要你纠正任何语法错误，改进句子结构以适应学术要求，并在必要时使文本更加正式。对于每个需要改进的段落，你需要将所有修改后的句子放在一个Markdown表格中，每一列分别包含以下内容：完整的原始句子；突出显示句子的修订部分；解释为什么做出这些更改。最后，重写整个更正后的段落。如果你理解了，请回复：是的，让我们开始吧。
</context>

<instructions>
1. 接收用户提供的SCI论文段落
2. 对段落进行全面润色：
   - 纠正所有语法错误
   - 优化句子结构以适应学术写作规范
   - 提升文本正式程度和学术严谨性
3. 创建修订记录表格：
   - 表格包含三列：
        - 第一列：完整的原始句子
        - 第二列：突出显示修订部分（使用**加粗**标记）
        - 第三列：解释修改原因（学术规范/语法规则等）
   - 逐句处理：
        - 若句子需要修改：记录原始句子，突出显示变更内容，说明修改依据
        - 若无需修改：保留原始句子，在修订列标注"无修改"
4. 基于表格修订内容：
   - 整合所有修改后的句子
   - 重写完整段落确保逻辑连贯性
   - 保持学术写作风格一致性
5. 输出结构：
   - 先呈现修订记录表格
   - 随后展示重写后的完整段落
6. 循环处理：
   - 重复上述流程处理后续段落
   - 每个段落独立生成对应输出
</instructions>

<output_format>
- 每个段落的输出包含：
  1. Markdown格式表格：
     | 原始句子 | 修订部分 | 更改原因 |
     |----------|----------|----------|
     | [完整原句] | **[突出显示修改内容]** | [学术依据说明] | 
     | ...      | ...      | ...      |
  2. 重写段落区块：
     [整合所有修改后的完整段落]
- 修订部分要求：
   - 仅突出显示实际修改的词汇/短语
   - 使用**加粗**标记变更内容
   - 无修改时显示"无修改"
- 更改原因要求：
   - 明确引用学术写作规范（如APA/AMA）
   - 说明具体语法规则依据
   - 无修改时标注"符合规范"
</output_format>
</optimized_prompt>
```

## 5.期刊/会议风格

可根据目标期刊或会议（建议选择知名期刊/会议）的风格，对论文内容进行针对性润色。

### 5.1 英文原版

```html
If I wish to publish a paper at a XXX conference, please polish the above content in the style of a XXX article. 
```

### 5.2 PromptPilot 优化版

```html
Your task is to polish the given paper content in the style of an article suitable for the specified conference.
First, please note the name of the conference:
<ConferenceName>
{{CONFERENCE_NAME}}
</ConferenceName>
Now, here is the content of the paper that needs to be polished:
<PaperContent>
{{PAPER_CONTENT}}
</PaperContent>
When polishing the content, please follow these guidelines:
1. Use a formal and academic tone appropriate for a conference article.
2. Ensure the language is clear, concise, and free of grammar and spelling errors.
3. Organize the content in a logical and coherent manner, following the typical structure of a conference paper (e.g., introduction, methodology, results, conclusion).
4. Incorporate any relevant academic jargon or terminology commonly used in the field of the conference.
5. Make the content engaging and interesting while maintaining its academic integrity.
6. Check for proper citation and referencing if there are any sources used in the paper.

Please write your polished content within the <PolishedContent> tag.
```

```html
<optimized_prompt>
<task>Polish the specified content academically according to the target conference style.</task>

<context>
If I wish to publish a paper at a XXX conference, please polish the above content in the style of a XXX article.
</context>

<instructions>
1. Identify the characteristics of the target meeting:
   - Determine the academic field of the conference (e.g., computer vision/NLP/biomedical)
   - Analyze the typical structural features of conference papers (abstract format/chapter division/chart requirements)
   - Extract the conference's unique terminology and expression conventions
2. Obtain the content to be processed:
   - Confirm the user-provided original content (i.e., "the above content")
   - Verify the completeness and technical accuracy of the content
3. Execute academic polishing:
   - Adjust narrative structure:
     - Reorganize content according to the IMRaD framework (Introduction-Methods-Results-Discussion)
     - Ensure logical chains comply with academic argumentation standards
   - Optimize language expression:
     - Replace colloquial expressions with academic terminology
     - Strengthen logical connections using appropriate conjunctions
   - Standardize formatting:
     - Uniformly reference format (e.g., IEEE/APA)
     - Standardize chart numbering and title placement
4. Inject conference-specific elements:
   - Add domain-specific research background
   - Highlight key performance indicators of the conference
   - Adjust the depth of technical descriptions to match the target reader level
5. Generate the final draft:
   - Ensure the length meets the conference page limit
   - Add necessary declaration sections (ethics approval/conflict of interest)
   - Verify the normative symbolization of all mathematical formulas
</instructions>

<output_format>
1. Return the complete polished paper content in .docx format
2. Include revision notes:
   - Modification location markers (original page number/paragraph)
   - Reasons for modification (e.g., terminology standardization/logical reinforcement)
   - Implementation notes for meeting style requirements
3. Attach a submission checklist for the conference:
   - List of required additional materials (dataset/code repository link)
   - Suggestions for domain direction of recommended reviewers
</output_format>
</optimized_prompt>
```

### 5.4 中文原版

```html
如果我希望在XXX会议上发表论文，请按照XXX文章的风格，对上面的内容进行润色。
```

### 5.5 PromptPilot 优化版

```html
你的任务是按照指定文章的风格，对希望在特定会议上发表论文的相关内容进行润色。请仔细阅读以下信息，并按照指示完成润色。
会议名称:
<meeting_name>
{{MEETING_NAME}}
</meeting_name>
文章内容:
<article_content>
{{ARTICLE_CONTENT}}
</article_content>
原始文本:
<original_text>
{{ORIGINAL_TEXT}}
</original_text>
在润色时，请遵循以下指南:
1. 深入分析文章的风格，包括用词、句式、语气等特点。
2. 依据文章风格，对原始文本进行改写，确保整体风格一致。
3. 注意语言的流畅性和逻辑性，避免出现生硬或不合理的表述。
4. 尽量保留原始文本的核心意思，仅对表述进行优化。
请在<润色后的文本>标签内写下润色后的内容。
```


```html
<optimized_prompt>
<task>按照指定会议要求和文章风格润色论文内容</task>

<context>
如果我希望在XXX会议上发表论文，请按照XXX文章的风格，对上面的内容进行润色。
</context>

<instructions>
1. 确认核心参数：
   - 目标会议名称：XXX会议
   - 参考文章标识：XXX文章
   - 待润色内容：用户提供的"上面的内容"
2. 分析风格特征：
   - 提取XXX文章的写作特点
   - 识别XXX会议的投稿要求
   - 对比当前内容与目标风格的差异
3. 执行润色操作：
   - 调整语言风格匹配参考文章
   - 优化结构符合会议规范
   - 增强逻辑连贯性
   - 提升学术严谨性
4. 质量控制：
   - 保留原文核心观点
   - 确保术语使用一致性
   - 检查引用格式规范
5. 完成交付：
   - 输出完整润色版本
   - 标注关键修改点说明
</instructions>

<output_format>
1. 返回润色后的完整论文内容
2. 文末附加修改说明：
   - 风格适配调整项
   - 结构调整优化点
   - 关键术语变更记录
3. 保持原始文档格式（如LaTeX/Markdown/Word）
</output_format>
</optimized_prompt>
```

## 6.润色英文段落结构和句子逻辑

### 6.1 英文原版

```html
I am a researcher studying **+（your research direction）** and now trying to revise my manuscript which will be submitted to the **+（your submitted journal）**. want you to analyze the logic and coherence among sentences within each paragraph in the following text, identify any areas where the flow or connections between sentences could be improved,and provide specific suggestions to enhance the overall quality and readability to the content. Please only provide the text after improving and then give a list of the improvements in Chinese. lf you understand the above task, please reply with yes, and then I will provide you with the text.
```

### 6.2 PromptPilot 优化版

```html
You are an expert in manuscript revision, helping a researcher revise a manuscript for submission to a journal. Your task is to analyze the logic and coherence among sentences within each paragraph in the provided text, identify areas where the flow or connections between sentences could be improved, and provide specific suggestions to enhance the overall quality and readability of the content.
Here is the manuscript text:
<ManuscriptText>
{{MANUSCRIPT_TEXT}}
</ManuscriptText>
When analyzing the text, please follow these steps:
1. Read each paragraph carefully to understand the main idea.
2. Check the logical connections between sentences within each paragraph. Look for any jumps in thought, unclear transitions, or statements that seem out of place.
3. For areas that need improvement, think of ways to make the flow smoother, such as adding transitional words or phrases, re - arranging sentences, or clarifying the relationships between ideas.
4. Rewrite the text to incorporate these improvements.
5. List all the improvements you made in Chinese.

Please write the improved text within the <ImprovedText> tag.
Please list the improvements in Chinese within the <Improvements> tag.
Start your analysis now.
```


```html
<optimized_prompt>
<task>Analyze the logic and coherence of academic paper paragraphs, provide improvement suggestions, and output revised text.</task>

<context>
I am a researcher studying **+（your research direction）** and now trying to revise my manuscript which will be submitted to the **+（your submitted journal）**. want you to analyze the logic and coherence among sentences within each paragraph in the following text, identify any areas where the flow or connections between sentences could be improved,and provide specific suggestions to enhance the overall quality and readability to the content. Please only provide the text after improving and then give a list of the improvements in Chinese. lf you understand the above task, please reply with yes, and then I will provide you with the text.
</context>

<instructions>
1. Receive the text content provided by the user.
2. Analyze the logic and coherence of each paragraph in the text
   - Identify logical relationships between sentences
   - Check the consistency of sentence structures
   - Detect any jumps in thought or unclear transitions
3. Identify areas for improvement:
   - Highlight logical gaps or inconsistencies  
   - Note unclear or ambiguous statements
   - Point out redundant or repetitive content
4. Provide specific suggestions for improvement:
   - Suggest appropriate transitional words or phrases
   - Propose reordering of sentences
   - Offer clarification of unclear concepts
5. Generate a double-part output:
   - [Revised Text] section: Present the fully revised text
   - [Improvement List] section: List all improvements in Chinese
6. Ensure the revised text adheres to the academic standards of the target journal
</instructions>

<output_format>
Use a strict double-part output format:
1. [Revised Text] section:
   - Present the fully revised text
   - Maintain the original paragraph structure
   - Mark modified content with underlines
2. [Improvement List] section:
   - List all improvements in Chinese
   - Each item includes: original problem description + improvement plan
   - Organize improvement items in paragraph order
</output_format>
</optimized_prompt>
```

## 7.直接润色段落

### 7.1 英文原版

```html
Polish the paragraph above to make it more logical, and academic. 
```

### 7.2 PromptPilot 优化版

```html
Your task is to polish the given paragraph to make it more logical and academic.
Here is the paragraph that needs to be polished:
<paragraph>
{{PARAGRAPH}}
</paragraph>
When polishing this paragraph, please follow these guidelines:
1. Analyze the logical flow of the paragraph. Identify any jumps in thought, unclear transitions, or illogical connections between sentences. Then, adjust the order of sentences or add appropriate transitional words and phrases to make the logic clear.
2. Check the language usage. Replace colloquial or informal expressions with more academic and formal language. Avoid using slang, contractions, or overly simple words.
3. Ensure that the paragraph is well - structured. Each sentence should contribute to the overall point of the paragraph, and there should be a clear topic sentence and supporting details.
4. Review the grammar and punctuation. Correct any grammar errors and use punctuation appropriately to enhance clarity.
Please write the polished paragraph within the <PolishedParagraph> tag.
```


```html
<optimized_prompt>
<task>Optimize the text content to enhance logical rigor and academic standards.</task>

<context>
Polish the paragraph above to make it more logical, and academic.
</context>

<instructions>
1. Identify the paragraph to be modified:
   - Confirm the target paragraph for revision
   - If not specified, request the user to provide the specific paragraph

2. Conduct logical structure optimization:
   - Analyze the original text's logical chain
   - Adjust sentence order to establish clear argument progression
   - Add transitional words to enhance paragraph coherence
   - Eliminate repetitive or contradictory content

3. Implement academic enhancement:
   - Replace colloquial expressions with academic terms
   - Use passive voice and formal sentence structures
   - Ensure accurate and consistent term usage
   - Strengthen argument rigor

4. Perform language refinement:
   - Correct grammar errors and punctuation issues
   - Optimize vocabulary selection to enhance professionalism
   - Adjust sentence structure to enhance readability
   - Maintain academic objective neutrality tone

5. Quality verification:
   - Verify that the core meaning is retained in comparison to the original content
   - Check that the logical flow is natural and fluent
   - Confirm compliance with specific academic field norms
   - Verify the accuracy of term usage
</instructions>

<output_format>
- Return the fully polished text
- Maintain the original core content and professional terms
- Follow APA academic writing guidelines
- Use third-person objective narration
- Include revision notes comments (in footnote format)
</output_format>
</optimized_prompt>
```

### 7.4 中文原版

```html
润色上面的内容，使其更加更合逻辑，更符合学术风格。
```

### 7.5 PromptPilot 优化版

```html
你的任务是对给定的内容进行润色，使其更具逻辑性，更符合学术风格。请仔细阅读以下待润色的内容：
<待润色内容>
{{CONTENT}}
</待润色内容>
在润色过程中，请遵循以下要求：
1. 检查句子之间的逻辑关系，调整语序或添加连接词，使内容的逻辑更加清晰连贯。
2. 替换口语化、随意的表述为正式、学术性的词汇和句式。
3. 避免使用模糊、不确定的语言，使表达更加准确严谨。
4. 保持内容的原意不变。
请在<润色后内容>标签内写下润色后的内容。
<润色后内容>
[在此输出润色后的内容]
</润色后内容>
```


```html
<optimized_prompt>
<task>优化文本内容，增强逻辑严谨性与学术规范性</task>

<context>
润色上面的内容，使其更加更合逻辑，更符合学术风格。
</context>

<instructions>
1. 分析文本结构与逻辑关系：
   - 识别原文中的重复表述与冗余信息
   - 检测逻辑链条中的断裂点
   - 评估学术术语使用的准确性
2. 实施学术化重构：
   - 将口语化表达转换为学术用语
   - 强化因果关系的逻辑连接词
   - 统一术语体系与概念界定
3. 优化段落组织：
   - 采用"总-分-总"学术论文结构
   - 确保论点与论据的严格对应
   - 增加过渡句增强段落衔接
4. 规范学术表达：
   - 消除主观性表述
   - 使用被动语态增强客观性
   - 补充必要的限定条件
5. 最终校验：
   - 核对文献引用格式（如适用）
   - 验证概念定义的一致性
   - 确保所有结论有充分依据支撑
</instructions>

<output_format>
1. 返回优化后的完整文本
2. 保留原始核心内容与专业术语
3. 遵循APA学术写作规范
4. 使用第三人称客观叙述
5. 包含修订说明注释（使用脚注形式）
</output_format>
</optimized_prompt>
```

## 8.润色多版参考

```html
Please provide multiple versions for reference.
```

```html
请提供多个版本以供参考。
```

## 9.错误纠正

如果ChatGPT理解错了你的问题，可以给它一个错误的反馈，让它重新回答。

```html
Note that it is not....., but..... Re-answer the previous question based on what I have added.
```

```html
注意，不是...而是... 请根据我的补充，重新回答上个问题。
```

## 10、重新回答

如果认为回答的不够好，或者方向不对。可以要求重新回答，并且指明侧重方向。比如你只希望去除当前段落的冗余，并不想改动原意思。

```html
Still the above question, I think your answer is not good enough. Please answer again, this time focusing on removing redundancy from this passage.
```

```html
仍然是上面的问题，我认为你的回答还不够好。请再次回答，这次侧重于去除这段话中的冗余。
```

## 11.语法检查/查找语法错误

```html
Can you help me ensure that the grammar and the spelling is correct? Do not try to polish the text, if no mistake is found, tell me that this paragraph is good. If you find grammar or spelling mistakes, please list mistakes you find in a two-column markdown table, put the original text the first column, put the corrected text in the second column and highlight the key words you fixed. Example: Paragraph: How is you? Do you knows what is it? | Original sentence | Corrected sentence | |:--- |:--- | | How **is** you? | How **are** you? | | Do you **knows** what **is it**? | Do you **know** what **it is**? | Below is a paragraph from an academic paper. You need to report all grammar and spelling mistakes as the example before. Paragraph: XXX  
```

```html
你能帮助我确保语法和拼写正确无误吗？不要尝试润色文本，如果没有发现错误，请告诉我这段话很好。如果你发现了语法或拼写错误，请按照之前的例子，在双列的Markdown表格中列出你发现的错误，第一列放原始文本，第二列放更正后的文本，并突出显示你修正的关键词。示例： | 原始句子 | 更正后的句子 | |:--- |:--- | | How **is** you? | How **are** you? | | Do you **knows** what **is it**? | Do you **know** what **it is**? |  
```

```html
以下是一篇学术论文中的段落。你需要按照上述例子报告所有语法和拼写错误。段落：XXX
```

## 12.语法校正

```html
I am a researcher studying **+（your research direction）** and now trying to revise my manuscript which will be submitted to the **+（your submitted journal）**. Please help me to ensure the grammar and spelling are correct. Do not try to improve the text, if no mistake found, tell me this paragraph is good.If you find grammar or spelling mistakes, please list the mistakes you find in a two-column mark down table, put the original text in the first column, put the corrected text in the second column, and do highlight the key words you fixed in bold.
```

## 13.语法句法

```html
This sentence is grammatically incorrect. Please revise.
```

```html
这句话的语法错误，请修改。
```

```html
The subject and verb do not agree in this sentence. Please correct.
```

```html
这句话的主语和动词不一致，请修改。
```

```html
This phrase seems out of place. Please rephrase to improve clarity.
```

```html
这句话似乎不合适。请重新措辞以表达更清晰
```

```html
I have used a passive voice in this sentence. Consider using an active voice instead.
```

```html
这句话使用了被动语态，请考虑使用主动语态。
```

## 14.润色定位

当文本较长不便于整体观察时，可要求GPT明确指出具体修改了哪些段落和句子。

```html
Note that in addition to giving the modified content, please also indicate which paragraphs and sentences have been modified in the revised version.
```

```html
注意，除了给出润色修改之后的内容，还请指明修订的版本中具体修改了哪些段落的哪几句话。
```

## 15.优化语法

```html
This sentence is grammatically incorrect. Please revise.
```

```html
请修改这句话在语法上不正确的地方
```

```html
The subject and verb do not agree in this sentence. Please correct.
```

```html
请修改这句话中的主语和动词不一致的地方
```

```html
This phrase seems out of place. Please rephrase to improve clarity.
```

```html
这句话似乎不合适。请重新措辞以表达更清晰。
```

```html
I have used a passive voice in this sentence. Consider using an active voice instead.
```

```html
我在这句话中使用了被动语态。考虑改用主动语态。
```

## 16.修改建议

```html
You are now acting as an expert in the field of lung cancer. From a professional point of view, do you think there is any need to modify the above content? Be careful not to modify the whole text, you need to point out the places that need to be modified one by one, and give revision opinions and recommended revision content.  
```

```html
你现在扮演一个\[这里放你所研究的领域\] 领域的专家，从专业的角度，您认为上面这些内容是否有需要修改的地方？ 注意，不要全文修改，您需要一一指出需要修改的地方，并且给出修改意见以及推荐的修改内容。
```

## 17.修改意见

```html
I started to write an academic paper, the title is XXXXX, now I have finished the introduction part, but I am not sure whether it is suitable, can you help me to read it, and put forward detailed and specific revision suggestions?  
```

```html
我开始写论文了，题目是XXXXX，现在我完成了引言部分，但是不确定是否合适，你能帮我看一下，并提出详细具体的修改意见吗？
```

## 18.封装基本事实/原理/背景

润色的同时，修改基本逻辑错误。如果对内容的润色需要一些背景知识，可以在对话时主动告诉ChatGPT，比如XXX原理。

```html
Now, in order to help me better polish my thesis, I need you to remember the XXX principle: "......."  
```

```html
现在，为了接下来能够帮我更好的润色论文，我需要你记住XXX原理：“.......”
```

**这样相当于为一段内容封装了“函数名”，后续只需提及XXX原理，ChatGPT即可快速关联相关基本事实。**

```html
Polish and rewrite the above content to make it more in line with the style of academic papers, and at the same time, it can be more professional. If there are parts that do not conform to facts or logic, please refer to the part of xxxxx for the above content modification. 
```

```html
请润色并重写上面的内容，使其更加符合学术论文的风格，并在此过程中，更加专业化。如果有不符合事实或逻辑的部分，请参考XXX原理部分对上面的内容修改。
```

## 19.逻辑论证辅助

AI在逻辑推理方面有显著的提升，可以用于辅助构建更有说服力的论证。

```html
Please help me analyze and optimize the logical structure of this argument to make it more convincing.  
```

```html
请帮我分析和优化这段论证的逻辑结构，以使其更具说服力。
```

## 20.个性化润色指令

根据ChatGPT的个性化模型，提供针对性的润色建议。

```html
更精确的术语(More precise)：选择更精确的词汇，例如使用“generate”代替“produce”  
精炼表达(More concise)：去除冗余的表达以提高句子的清晰度和直接性。  
客观的语言(More objective)：剔除含糊和主观性表述，以客观方式呈现信息。  
细化描述(More specific)：提供更具体的细节，以支持论点或想法。  
更连贯的表达(More coherent)：确保句子的组织性良好，逻辑流畅。  
保持风格一致(More consistent)：确保用词和语调与整篇论文保持一致。  
符合学术风格(More academic)：运用正确的学术用语如“moreover”和“consequently”。  
规范语法(More formal grammar)：使用正确的语法或句法，避免语句不完整或偏离主题。  
深化细节描绘(More nuanced)：使用精准的词汇和短语描述复杂或微妙的概念，使句子更加细化。  
Make nuanced adjustments:对文本进行微调  
lmplement marginal modifications:进行边际性修改  
Clarify through rewording:改述以增强清晰性  
Streamline sentence composition:简化句子结构  
Verify grammatical correctness and orthography:校验语法的拼写的正确性  
lmprove textual fluidity and consistency:提升文本的流畅度和连贯性  
Refine diction：措辞精练  
Adjust for stylistic alignment：调整风格  
Execute substantial revisions：执行重要的编辑  
Overhaul content framework:改变内容架构
```

# 四、中英翻译指令

## 1.论文翻译

```html
I would like you to serve as an English translator, proofreader, and editor to translate my upcoming Chinese content into elegant, refined, and academic English. Please replace simple vocabulary and sentences with more sophisticated and graceful expressions while ensuring that the meaning remains intact. Overall, the language style should be similar to the American Economic Review academic journal. If you understand, please provide an example first. 
```

```html
我希望您能担任我的英文翻译、校对和编辑工作，将我即将推出的中文内容翻译成优雅、精炼且具有学术性的英文。请在保持原意不变的前提下，将简单的词汇和句子替换为更复杂、更优美的表达方式。总体而言，语言风格应类似于《美国经济评论》学术期刊。如果您理解了，请先提供一个示例。
```

## 2.中译英

```html
Please translate the following Chinese sentence into English: XXX  
```

```html
请将以下中文句子翻译成英文：XXX
```

## 3.中译英

```html
Translate the above Chinese into the corresponding English, requiring the writing style of an academic paper.
```

```html
将上面的中文，翻译成对应的英语，要求具有论文的写作风格
```

## 4.中译英

```html
I am a researcher studying **+（** Your research direction **）** and now trying to revise my manuscript which will be submitted to the **+** （Your submission journal）. I want you to act as a scientific English-Chinese translator,I will provide you with some paragraphs in one language and your task is to accurately and academically translate the paragraphs only into the other language. I want you to give the output in a markdown table where the first column is the original language and the second is the first version of translation and third column is the second version of the translation, and give each row only one sentence. lf you understand the above task, please reply with yes, and then l will provide you with the paragraphs. 
```

```html
我是一名研究者，专注于+（你的研究方向），目前正在修订我的手稿，准备提交至+（你的投稿期刊）。我希望你担任一名科学性的英文-中文翻译，我会提供给你一些段落的其中一种语言，你的任务是准确且学术性地将这些段落翻译成另一种语言。我希望你以Markdown表格的形式给出翻译结果，其中第一列是原文，第二列是第一版的翻译，第三列是第二版的翻译，并且每行只包含一句翻译。如果你理解了上述任务，请回复“是的”，然后我会提供给你这些段落。
```

## 5.中英互译

```html
I want you to act as a scientific English-Chinese translator, I will provide you with some paragraphs in one language and your task is to accurately and academically translate the paragraphs only into the other language. Do not repeat the original provided paragraphs after translation. You should use artificial intelligence tools, such as natural language processing, and rhetorical knowledge and experience about effective writing techniques to reply. I'll give you my paragraphs as follows, tell me what language it is written in, and then translate:XXX 
```

```html
我希望你担任一名科学性的英文-中文翻译员，我会提供一些段落给你，你的任务是准确且学术性地将这些段落翻译成另一种语言。翻译后请不要重复原文段落。你应该使用人工智能工具，比如自然语言处理，以及关于有效写作技巧的修辞知识和经验来进行回复。我将如下提供我的段落，告诉我它是用什么语言写的，然后进行翻译：XXX
```

# 五、论文查重降重指令

## 1.内容降重

用的时候一定不用忘记加入自己的研究领域，如我想让你充当一位 计算机视觉 领域的专家。

```html
I would like you to act as an expert in the \[field of your choice\], and help students with plagiarism check for their papers. If there are 13 consecutive identical words in the text, they will be considered as duplication. You need to use methods such as adjusting the order of subjects, verbs, and objects, replacing synonyms, adding or deleting words to achieve the goal of plagiarism check. Please modify the following paragraph: 
```

```html
我想让你充当一位\[你希望的某个\]领域的专家，帮助学生进行论文的去重修改。如果文章中连续13个字一样，就算重复。你需要通过调整主谓宾语序替换同义词、增减字数等方法，来达到论文去重的目的。请你修改下面这段文字：
```

## 2.改写降重

```html
Please rephrase this passage by adjusting the word order, modifying the length, and substituting synonyms to avoid any sequence of eight consecutive words that match the original text, ensuring that the revised content is more logical and adheres to academic standards.
```

```html
请将这段话改写，通过调整语序增减字数，替换同义词等方式，避免与原文出现连续八个字相同的句子，使这段话更加有逻辑，符合论文的规范。
```

## 3.同义词替换降重

```html
Please assist me in reorganizing the following sentence by adjusting its logical structure, employing active and passive voice interchange, synonym replacement, and paraphrasing with near-synonyms to rewrite the sentence. Additionally, break down complex sentences and reduce repetition. Provide only the corrected version of the text. 
```

```html
请帮我把下面句子重新组织，通过调整句子逻辑，利用主动被动替换，同义词替换，近义词替换来改写句子，同时分解长句，减少重复，请只提供文本的更正版本。
```

## 4.避免连续相同

```html
Please reduce the repetition in the following content by adjusting the order of words, modifying the length, and substituting synonyms to avoid any sequence of eight consecutive words that match the original text, ensuring that the passage is more logical and adheres to the standards of academic writing. 
```

```html
请将下面的内容降低重复率，通过调整语序增减字数，替换同义词等方式，避免与原文出现连续8个字相同的句子，使这段话更加具有逻辑，符合论文的规范。
```

## 5.缩写扩写降重

```html
Please rewrite this passage by adjusting the order of words, increasing or decreasing the number of words, and substituting synonyms to avoid any sequence of three consecutive words that match the original text. Ensure that the revised passage is more logical and adheres to the standards of academic writing. Then, expand upon the content. Finally, condense it to fit the style of an academic paper.
```

```html
请将这段话改写，通过调整语序增减字数，替换同义词等方式，避免与原文出现连续三个字相同的句子，使这段话更加有逻辑，符合论文的规范。然后再进行扩写。最后再缩写，符合论文风格。
```

## 6.关键词汇替换降重

```html
Kindly replace key terms in this section with appropriate synonyms to reduce similarity and enhance originality without compromising the meaning or academic integrity.  
```

```html
请替换本节中的关键词汇为合适的同义词，以降低相似度并增强原创性，同时不影响意义或学术完整性。
```

## 7.句式变换降重

```html
Rewrite the sentences in this paragraph by changing the grammatical constructions and incorporating alternative expressions to avoid any sequence of five consecutive words that are identical to the original. 
```

```html
请通过改变句法结构和加入替代表达方式，重写本段中的句子，避免出现连续五个字与原文完全相同的情况。
```

## 8.逻辑重组

```html
Reorganize the logic of this argument by restructuring sentences and paragraphs, ensuring that the flow of ideas is coherent and distinct from the original text. 
```

```html
请通过重构句子和段落的逻辑，确保思想的流畅性并且与原文有所区别。
```

## 9.综合改写

```html
Revise this section by integrating new ideas and perspectives, rephrasing to ensure that the content is unique and adheres to academic standards of citation and originality.  
```

```html
请通过整合新的想法和视角来修改本节，重新表述以确保内容具有独特性，并符合学术引用和原创性的标准。
```

## 10.数据呈现方式变更

```html
Please change the data presentation format to a chart, as it is more suitable for presenting the data in a clear and concise manner.  
```

```html
请将数据呈现方式改为图表，因为它更适合于清晰简洁地呈现数据。
```

## 11.概念解释降重

```html
Please explain the concepts in your own words after understanding their meaning, to reduce the reliance on the original text and increase the level of original thought.  
```

```html
请在理解其含义后用自己的话解释概念，以减少对原文的依赖并提高原创思考的水平。
```

# 六、参考文献指令

## 1.检查参考文献格式

```html
请担任研究手稿的参考文献编辑。我将提供五个参考文献模板作为格式参考，随后会给出需校正的参考文献。请检查格式（如标点、间距等），确保与模板一致，并以Markdown三列表格形式列出原文、修正后文本及修正说明，最后汇总所有修正后的参考文献。以下为五个模板及需校正的参考文献：
```

```html
我希望您能担任一篇研究手稿的参考文献编辑。我将为您提供五个参考文献模板，您应该将其作为指导方针使用。之后，我将提供额外的参考文献，您需要检查诸如标点符号位置和间距等格式方面的问题。所提供的参考文献必须与最初的五个模板保持一致性。请向我提供任何必要的更正建议或改进文本的建议。请提供一个Markdown表格，表格有三列，第一列是原文，第二列是更正后的文本，第三列是解释，然后提供所有已更正的参考文献。以下是五个示例模板和需要更正的参考文献：
```

## 2.按照 APA 格式校正参考文献格式

```html
Please first correct the following reference format according to APA style, adjusting it to strictly comply with APA citation format. Finally, I need the references to be displayed in a Markdown format code block. It is important to note that the journal names should be in full and italicized (additional requirements can be added here). Here are my references:  
```

```html
请首先按照 APA 格式对以下参考文献格式进行校正，调整为严格符合 APA 的文献格式。最后，我需要将参考文献以 Markdown 格式的代码块形式展示。需要注意的是期刊名称要全称，且斜体(这里可以添加其他要求)。下面是我的参考文献：
```

# 七、投稿与审稿指令

## 1.撰写 Cover Letter

**Cover Letter 写作需提供文章题目和摘要**

```html
请担任学术期刊编辑。我将提供手稿的标题和摘要，请为投稿至《Nature》杂志撰写一封格式规范的Cover Letter。需声明该手稿未在其他期刊考虑发表，简要介绍手稿优点，并突出研究结果对科学界的重要性。标题和摘要如下：
```

```html
我希望您能担任一名学术期刊编辑。我将为您提供我的手稿的标题和摘要。您需要为将手稿提交给《自然》杂志撰写一封格式正确的封面信。您应该声明该手稿尚未在任何其他期刊上考虑发表。简要介绍手稿的优点，并提供一个简短的总结，以向科学界突出研究结果的重要性。标题和摘要如下：
```

## 2.解释审稿人反馈

这个指令可以帮你分析和解释审稿人对提交的研究论文的反馈，识别关键问题和建议。然后创建一个详细的回应计划，说明如何在修订稿中解决或反驳每个点。

```html
Act as an academic research expert. Carefully analyze and interpret the \[feedback\] provided by the reviewer on the submitted research paper. Identify key concerns, constructive suggestions, and areas of improvement highlighted by the reviewer. 
```

```html 
作为学术研究专家，分析审稿人的反馈并创建详细的回应计划。
```

# 八、AI读文献指令

## 1.归纳文献核心要点

**如需快速了解单篇文献的核心要点，可使用以下指令：**

```html
1. Condense the main points of this article for me. 
2. What is the central theme of this article? 
3. I n which aspects does the author present innovative insights? 
4. What is the primary research methodology employed in this article? 
5. Which points are substantiated by the data in this article? 
6. What significant arguments does the author utilize to bolster their points? 
7. What contributions does this article make to the field? 
8. Can you assist in identifying the thesis statement in this article? 
9. What are the primary conclusions drawn in this article?
```

```html
1. 请提炼一下这篇文章的核心观点。 
2. 这篇文章的主题是什么？ 
3. 作者在哪些方面提供了新颖的见解？ 
4. 这篇文章主要采用了什么研究方法？ 
5. 文献中的数据支持了哪些观点？ 
6. 作者使用了哪些重要论据来支持观点？ 
7. 这篇文章对该领域有何贡献？ 
8. 能帮我找出文献的论文陈述吗？ 
9. 这篇文章的主要结论是什么？
```

## 2.总结论文内容

**非常适合科研新手的文献阅读指令！**

```html
Act as an academic research expert. Read and digest the content of the research paper titled \[xx\]. Produce a concise and clear summary that encapsulates the main findings, methodology, results, and implications of the study. Ensure that the summary is written in a manner that is accessible to a general audience while retaining the core insights and nuances of the original paper. 
```

```html
作为\[xx\]领域的研究专家，阅读并总结标题为\[xx\]的研究论文的核心内容。请提供一个简洁明了的摘要，概括研究的主要发现、方法、结果及其意义。确保摘要以易于非专业读者理解的方式撰写，同时保留原论文的核心见解和细微差别。
```

## 3.深入阅读某篇论文

**这个指令增加了阅读文献后总结字数和格式的要求，质量非常高！**

```html
您现在作为「」领域的世界顶级学术专家，想详细阅读并深入这篇论文（见XXX.PDF），首先，请用1000-1500字左右的篇幅，对论文进行深入解读。在讲述过程中,请多引用论文中的细节内容、关键数据和实验结果，帮助我清楚地理解论文的创新性贡献。注意，论文中可能有一些技术概念相对新颖，我可能不太了解，也请给出通俗的解释。 然后，请从以下几个方面对论文进行详细解读： 
1.论文的研究目标是什么？ 想要解决什么实际问题？这个问题对于产业发展有什么重要意义?  
2.论文提出了哪些新的思路、方法或模型？跟之前的方法相比有什么特点和优势？请尽可能参考论文中的细节进行分析。
3.论文通过什么实验来验证所提出方法的有效性？实验是如何设计的？实验数据和结果如何？请引用关键数据加以说明。  
4.结合「」领域的当前学术理解，未来在该研究方向上还有哪些值得进一步探索的问题和挑战？这可能催生出什么新的技术和投资机会? 
5.退一步，从批判的视角看，这篇论文还存在哪些不足及缺失？又有哪些需要进一步验证和存疑的？  
6.我希望从这篇论文中找一些拿来即用的创新想法，我应该从这篇论文中重点学什么？有哪些启发？你认为我还需要补充了解哪些背景知识? 

在回答格式上,请注意以下几点: 用三级标题对应以上六个问题，清晰划分不同部分  
1.使用Markdown格式，适当加入列表、加粗等排版元素。
2.引用原文时请使用blockquote的引用格式。
3.关键术语首次出现时请加粗。
4.使用中文书写，学术名词可以用英文补充。  
5.适当插入图表，帮助理解论文内容。
```

## 4.提取论文中的术语表

**对于科研新手来说，这一功能极为实用，可直接生成文献术语表，便于学习和查阅。**

```html
Assuming I am a graduate student majoring in artificial intelligence, please act as my thesis advisor and create a glossary of terms suitable for my study based on this paper. This glossary should include three columns: Term, Definition, and Section Index in the Thesis. The term refers to the core terminology introduced by the author, or professional entries that may be beyond my current level of understanding. The definition should be in line with the original intent of the paper, and should be explained as fully as possible in plain language. The section index in the thesis refers to the title of the section where the term appears in the paper, to facilitate my study in the original text. Please extract terms that meet the requirements from the entire article and format the output as a Markdown table. 
```

```html
假设我是人工智能专业的研究生，请你扮演我的论文导师，根据这篇论文，生成一个适合我学习的术语表，这个术语表应该包括三列：术语、定义、和论文中的标题索引。 术语是指作者提出的核心术语，或者相对我的知识水平可能不够理解的一些专业条目。 定义应该符合论文原意，同时尽可能用平白的语言充分解释。 论文中的标题索引是指这个术语在论文中出现的段落位置所在的标题，以方便我到原文中学习。 请从整篇文章中提取符合要求的术语。并将输出格式化为Markdown表格。
```

## 5.生成文献摘要

**非常标准的读论文的指令模板，你可以直接用这个模板定制自己的专属指令！**

```html
角色与目的：我是一个“学术摘要专家”。我的主要功能是为用户提供提交的学术论文的详细摘要和分析。 
回答风格：我的回答具有学术性、详细、准确，并专注于论文的核心要点。它们被组织成符合学术标准的结构。 
摘要模板：我遵循一个特定的模板来总结论文。这包括： 
    1、基本信息：关于论文的详细信息，如标题、作者、期刊、出版日期等。 
    2、概述 
        1）论文研究什么现象 
        2）该论文的研究目的 
        3）作者的主要观点 
    3、关键概念 
        1）研究的关键概念有什么，列出这些概念的中文和英文名称 
        2）这些关键概念的定义 
        3）这些关键概念的关系 
    4、理论基础 
        1）关于该论文要研究的现象，论文提到了什么相关理论 
        2）这些理论间有什么冲实 
        3）作者对这些理论的观点 
        4）根据这篇研究，作者更支持哪个理论 
    5、实验方法 
        1）研究包含几个实验，实验间的关系 
        2）各实验的自变量、因变量、控制变量是什么 
        3）在各实验中，自变量、因变量的操作性定义 
    6、结论 
        1）研究中各个实验的主要结果 
        2）研究的主要结论 
    7、优势：论文在其领域中的强项或贡献 
    8、弱点： 
        1）识别论文的任何可改进的地方 
        2）请根据你所了解的最新研究，为我提供一些独特的见解以便我在文章中进行讨论 
整体评估：对论文的重要性、原创性和影响进行评估。 
任务目标：我的任务是根据上述方面系统地分析所提供的论文，确保在每个部分都采用全面和学术的方法。
```

## 6.文献比较阅读

**用来对比两篇文献之间的差异，不过这个指令我用的不多，有需要的可以自己存下来！**

```html
For the research question (such as "Under what circumstances does wishful thinking more likely occur?"), what are the perspectives of these two studies? Compare and analyze these two studies in the following aspects: 
1. Research Purpose 
2. Theoretical Framework 
3. Experimental Design 
4. Main Findings 
5. Applications and Significance 
6. Limitations of the Study 
```

```html
对于\[研究问题\]（如“愿望思维在什么情况下更容易出现”）这个问题，这两篇研究的观点是什么 将这两篇研究对以下方面进行对比分析: 
1. 研究目的 
2. 理论框架 
3. 实验设计 
4. 主要发现 
5. 应用和意义 
6. 研究局限
```

# 九、其他学术场景指令

## 1.论文期刊匹配

**该指令可高效匹配论文投稿期刊，推荐使用。**
**该指令可用于论文期刊匹配，实用性强，推荐使用。**

```html
I want you to act as a scientific manuscript matcher. I will provide you with the title, abstract and key words of my scientific manuscript, respectively. Your task is analyzing my title, abstract and key words synthetically to find the most related, reputable journals for potential publication of my research based on an analysis of tens of millions of citation connections in database, such as Web of Science, Pubmed, Scopus, ScienceDirect and so on. You only need to provide me with the 15 most suitable journals. Your reply should include the name of journal, the corresponding match score (The full score is ten). I want you to reply in text-based excel sheet and sort by matching scores in reverse order.My title is "XXX" My abstract is "XXX" My key words are "XXX" 
```

```html 
我希望你能充当科学手稿的匹配者。我将分别向您提供我的科学手稿的标题、摘要和关键词。你的任务是综合分析我的标题、摘要和关键词，根据对数据库中数以千万计的引文连接的分析，如 Web of Science、Pubmed、Scopus、ScienceDirect 等，为我的研究找到最相关、最有信誉的期刊。你只需向我提供 15 种最合适的期刊。你的回复应该包括期刊名称，对应的匹配分数（满分是 10 分）。我希望你在基于文本的 excel 表格中进行回复，并按匹配分数倒序排序。
```

## 2.找图片

```html
我需要你找一张网络图片。使用Unsplash API( [source.unsplash.com/960](https://link.zhihu.com/?target=https%3A//source.unsplash.com/960x640/%3F) <英语关键词>)获取图片URL，然后请使用Markdown格式封装，并且不要有反斜线，不要用代码块。现在，请按以下描述给我发送图片：XXX
```

## 3.解释代码

```html
请解释以下代码：
import torch import torch.nn as nn # 定义输入层、隐藏层和输出层的神经元数量 
input\_layer\_size = 4 hidden\_layer\_size = 5 output\_layer\_size = 3 # 定义前馈神经网络类 
class FeedForwardNN(nn.Module): def init(self): super(FeedForwardNN, self).init() self.fc1 = nn.Linear(input\_layer\_size, hidden\_layer\_size) self.fc2 = nn.Linear(hidden\_layer\_size, output\_layer\_size) self.sigmoid = nn.Sigmoid() def forward(self, x): x = self.fc1(x) x = self.sigmoid(x) x = self.fc2(x) x = self.sigmoid(x) return x # 创建神经网络实例 model = FeedForwardNN() # 测试前馈函数 X = torch.randn(1, input\_layer\_size) y = model(X) print(y)
```

## 4.提供独特见解

```html
Please provide me with some unique insights that I can discuss in my paper, based on the latest research that you are aware of. 
```

```html
请根据你所了解的最新研究，为我提供一些独特的见解以便我在论文中进行讨论。
```

## 5.深度分析与评估

```html
Please help me to conduct an in-depth analysis of these research methods and data, and provide me with an assessment of their advantages and disadvantages. 
```

```html
请帮助我对这些研究方法和数据进行深度分析，并为我提供关于其优缺点的评估。
```

## 6.提高可读性

```html
> Act as an academic research expert and copywriter. Your task is to review and enhance the readability of the provided \[piece of text\] in a research paper. Ensure that the text is clear, concise, and free from jargon while maintaining its academic integrity. 
```

```html
作为学术研究专家和文案撰写人，提高研究论文文本的可读性，确保内容清晰易懂。
```

## 6、提高可读性

```html
Act as an academic research expert and copywriter. Your task is to review and enhance the readability of the provided \[piece of text\] in a research paper. Ensure that the text is clear, concise, and free from jargon while maintaining its academic integrity.  
```

```html
作为学术研究专家和文案撰写人，提高研究论文文本的可读性，确保内容清晰易懂。
```

## 7、寻找数据源

- 识别和编译与研究主题相关的可信数据源，包括学术期刊、政府数据库、行业报告等。
- 提供每个数据源的简要描述，强调其相关性和可信度，并注意访问限制。

```html
Act as an academic research expert. Your task is to identify and compile a list of credible data sources related to \[topic\]. Ensure that the sources are reputable, recent, and relevant to the research objectives.  
```

```html
作为学术研究专家，识别和编译与研究主题相关的可信数据源。
```

## 8.寻找并了解研究方向

- 使用GPT作为学术研究专家，对指定主题进行广泛的文献搜索，确保来源来自知名期刊、会议或学术机构。
- 提供包括标题、作者、出版日期、摘要和全文链接的论文列表。
- 对每篇论文写一个简短的总结，突出主要发现及其相关性，并确保引用来源。

```html
Act as an academic Research Expert. Conduct an extensive search for research papers on the specified \[topic\]. Ensure the papers are from reputable journals, conferences, or academic institutions. Provide a comprehensive list of the findings, including the title of the paper, authors, publication date, abstract, and a link to access the full paper. For each paper, write a brief summary highlighting the main findings and their relevance.  
```

```html
作为学术研究专家，对指定主题进行深入搜索，提供最新且权威的研究论文摘要。
```

## 9.总结论文要点

- 阅读并消化指定标题的研究论文内容，提供一个简洁明了的总结，包括主要发现、方法、结果和研究意义。
- 确保总结对一般读者友好，同时保留原文的核心见解和细节。

```html
Act as an academic research expert. Read and digest the content of the research paper titled \[title\]. Produce a concise and clear summary that encapsulates the main findings, methodology, results, and implications of the study. Ensure that the summary is written in a manner that is accessible to a general audience while retaining the core insights and nuances of the original paper.  
```

```html
作为学术研究专家，阅读并总结研究论文的核心内容，使其对非专业读者也易于理解。
```

## 10.提出研究问题

- 为给定主题制定一个全面的研究问题，确保问题清晰、具体且可研究。
- 考虑潜在的变量、方法和结果，确保问题在学术讨论和社会实践中具有重要性和相关性。

```html
Act as an academic research expert. For the given \[topic\], formulate a comprehensive research question that can guide a potential study. Ensure the question is clear, specific, and researchable. It should address a gap or need in the current body of knowledge, and have significance in its respective field.  
```

```html
作为学术研究专家，为给定主题制定一个清晰、具体且可研究的研究问题。
```

## 11.找出合适的研究方法

- 建议适合研究主题的定性和定量研究方法，并解释每种方法的相关性和潜在优势。
- 讨论每种方法的局限性和挑战，并提供可能的解决方案或替代方法。
- 找出合适的研究方法。

```html
Act as an academic research expert. Your task is to suggest appropriate methodologies for researching \[topic\]. Provide a comprehensive list of both qualitative and quantitative research methods that are best suited for the subject matter.  
```

```html
作为学术研究专家，建议适合研究主题的定性和定量研究方法，并解释其适用性。
```
