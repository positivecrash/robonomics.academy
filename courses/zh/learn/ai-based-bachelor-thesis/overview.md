---
title: 概述
description: 使用AI工具快速启动您的学士论文
metaOptions: [学习, 使用AI工具快速启动您的学士论文]
defaultName: Quickstart Your Bachelor's Thesis with AI-powered Tools
---

<RoboAcademyText fWeight="500">
所以，您担心的事情发生了。
</RoboAcademyText>

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmW6qohyJvUF2c3EwhVWZXghArAZQ6KkBsbqT41QRgJRAh', type: 'webm'}]" />

您需要提交一份大量的文本作品，而截止日期非常接近。或者情况可能不同：提交截止日期可能并不那么可怕，但是写大量材料，尤其是具有正式、技术内容的材料，让您感到不安，推迟任务很长时间。无论如何，您必须经历一个相当漫长、单调且经常非常无聊的过程，这会影响您的动力。也许您想多花时间进行创造性和发展性任务，但不幸的是，一些职业和活动是这样结构化的。

## 进入AI

幸运的是，历史上一直在使我们的日常任务变得更加容易的进步已经达到了文本写作的领域。这一次，这是可能的，这要归功于人工智能的进步，特别是生成式语言模型，能够理解和解决请求，并以聊天格式提供更或多或少有意义的答案。在Robonomics，我们简直无法忽视能够提高生活和机器之间的交流和互动水平（并且也使我们的日常任务更加轻松！）的东西。

最新的GPT模型以其功能令人印象深刻，但问题是如何正确使用它们，最重要的是它们能够依赖多少。这些技能被称为提示工程，此，我们提供了这个指南，它将帮助您对当前生成式人工智能的可能性有一个基本的了解。

在本指南中，我们将尝试撰写一篇简单的学士论文，基于我们的"学士"的知识分支和学士已经通过的起始材料。 我们当然会尽量遵守最低限度的学术规则，但两周（这是本指南的计划时间）肯定不足以使学士论文成功（尽管现实有时会证明相反）。 尽管如此，这个指南可以被视为理解AI已经可以平滑处理的最常见和耗时的过程的良好起点。顺便说一句，您不必局限于学士论文任务：这个指南对遵循IMRaD标准（介绍、方法、结果、讨论）的任何文本作品都有用：期刊和会议出版物、博士论文、技术报告、手册等。 

本指南不保证也不旨在成功提交一篇学士论文并获得最高分。

<RoboAcademyNote title="DISCLAIMER" type="warning">
  使用的工具
</RoboAcademyNote>

## 在指南中使用的AI服务中：

**[ChatGPT](https://chat.openai.com/chat)** — 基于OpenAI创建的生成式预训练变压器语言模型（版本3.5和4）的聊天机器人。它以与用户的聊天格式运行，回答他们的请求，这些请求可以从简单的问题到撰写诗歌和调试用户代码。它的知识仅限于2021年9月，因为它无法访问互联网。基本使用是免费的，但需要使用话号码进行注册（在某些国家不可用）。它有一个订阅选项（每月20美元），具有更强大的功能和添加插件的能力，例如访问Wolfram或Slack。

**[Bing Chat](http://www.bing.com)** — 基于GPT-4集成到微软的必应搜索服务中的聊天机器人。需要微软帐户才能访问。基本上，它具有与ChatGPT相同的功能，但具有互联网访问权限，使其更加强大。

**[Auto-GPT](https://news.agpt.co/)** — 一种使用GPT-4创建自主AI代理的软件，该代理解决用户设置的任务。代理可以访问互联网、长期记忆，并具有将信息保存到文件的功能，使其能够执行复杂的操作序列。要使用它，需要在OpenAI上拥有一个帐户，最好是付费订阅。安装说明可在[此处找到](https://docs.agpt.co/setup/)。

**[Notion AI](https://www.notion.so/product/ai)** — 集成到同名知识管理软件中的AI助手。它具有有限的免费访问权限，而订阅费用为每月10美元。它方便处理和改进已经准备好的文本，并具有为此目的预安装的功能。

此外，我们还需要以下服务：

**[Overleaf](http://www.overleaf.com)** — 便捷的在线LaTeX编辑器，用于格式化文本。它具有各种模板，适用于任何类型的工作（从论文和文章到演示文稿）。们将使用[MIT论文模板](https://www.overleaf.com/latex/templates/mit-thesis-template/ytphktgwpktc)。

**[Overleaf](http://www.overleaf.com)** — 便捷的在线LaTeX编辑器，用于格式化文本。它具有各种类型工作的模板（从论文和文章到演示文稿）。我们将使用[MIT论文模板](https://www.overleaf.com/latex/templates/mit-thesis-template/ytphktgwpktc)。

**[Google Scholar](http://scholar.google.com)** — 用于科学出版物的搜索引擎。它用于验证AI服务建议的来源。

## 如何使用AI工具

### AI聊天机器人（ChatGPT，必应）

AI聊天机器人（ChatGPT，必应）不需要特别复杂的方法：您只需要格式化适当的请求并将其发送给聊天机器人（每条消息的字符数有限，但您可以要求聊天机器人等待直到请求的整个文本被发送）。

### Notion AI

对于Notion AI，只需在任何页面上插入一个文本块并调用上下文菜单以请求AI助手。

### Auto-GPT

Auto-GPT需要不同的方法，因为用户需要在开始以下操作之前指定：

- AI助手的名称
- AI助手的角色
- AI助手要完成的最多5个连续目标

之后，Auto-GPT将启动一个代理，为用户显示所有“想法”和执行的操作，即：

- `THOUGHTS` — 代理想要在当前迭代中实现的一个总体想法
- `REASONING` — 代理选择这个想法的原因
- `PLAN` — 实现这个想法的具体行动（在互联网上搜索，分析文件，写入文件等）
- `CRITICISM` — 代理对其行动施加的特殊条件（例如，“仅从IEEE期刊中搜索高质量参考资料”）。

## 第一步

<RoboAcademyNote title="WARNING" type="warning">
  AI工具仍在不断改进中，因此请始终仔细检查获得的结果。
</RoboAcademyNote>

### 为服务提供上下文

最新AI服务的一个重要优势之一是它们在单个会话中相当好地记住请求的上下文。因此，开始撰写学士论文的第一步是构思一个上下文 （一个“传奇”）并将其提供给服务。

作为工作材料，从Robonomics Academy的课程["具有Robonomics和Home Assistant的主权智能家居"](/learn/smart-home-course/overview)开始。结果，创建了以下上下文：

<RoboAcademyDialog>

I am a student of the Department of IoT Engineering and Web3 Science. 

I am going to get Bachelor of Science in Computer Science and Engineering.

I completed an online course called "Smart Home Sovereign". In this course, I went through all the steps necessary to build my own sovereign smart home, the main advantage of which is the security / privacy of user data.
During the course, I set up an IoT hub on a Raspberry Pi and connected smart devices (such as a temperature/humidity sensor, a door sensor, a smart bulb, a motion sensor, etc.) to it via a Zigbee适配器 using the MQTT protocol. The IoT hub is powered by Home Assistant software. Next, I connected the hub to a decentralized cloud, based on Polkadot web3 technology. This is necessary to securely transfer device data to the network without the need for a centralized cloud service provider. This allows me to securely manage my home remotely.

Now I want to take this course as a basis and write a bachelor's thesis with your help.

</RoboAcademyDialog>

AI聊天机器人对这个上下文的典型反应将是建议澄清请求以及服务如何提供帮助。

### 从建议中选择一个主题

下一步（学士情况下的典型步骤）是为论文选择一个主题。在这里，只需发出请求链接`为我的论文提议N个主题`。ChatGPT和Bing Chat提供了以下内容：

<RoboAcademyDialog>

"Designing a Secure and Private Smart Home System using Web3 Technologies" — This topic could involve examining the steps you took to build your sovereign smart home and exploring the security and privacy benefits of using IoT and Web3 technologies.

"Comparing Centralized and Decentralized Approaches to Smart Home Data Management" — This topic could involve comparing and contrasting the benefits and drawbacks of using centralized cloud vendors versus decentralized cloud technologies like Polkadot for managing smart home data.

"Developing a Smart Contract-based Framework for Managing Smart Home Devices" — This topic could involve exploring the use of smart contracts to manage smart home devices and develop a secure and efficient framework for managing them.

"Investigating the Security and Privacy Risks of Smart Home Systems" — This topic could involve examining the potential risks and vulnerabilities of smart home systems, including issues related to data privacy, cybersecurity, and physical safety.

"Exploring the Role of Blockchain in Smart Home Data Management" — This topic could involve examining how blockchain technology could be used to manage smart home data and ensure the security and privacy of user data.

"Investigating the Future of Smart Home Technologies and their Impact on Society" — This topic could involve examining the potential social and economic impacts of smart home technologies, including issues related to privacy, security, and the digital divide.

</RoboAcademyDialog>

指南选择了主题**“使用Web3技术设计安全和私密的智能家居系统”**。

### 具有IMRaD结构的简单计划

接下来，原则上，我们可以按照IMRaD结构的具体部分进行论文写作。但是，最好有一个更详细的学士工作计划。这也可以从AI服务请求。ChatGPT提出了以下计划，没有任何额外条件：


<RoboAcademyDialog>

<ChatGPT/>

1. 介绍duction
    1. Background and motivation
    2. Research questions and objectives
    3. Significance of the study
2. Literature Review
    1. 概述 of smart home technology and its security and privacy issues
    2. 介绍duction to web3 technology and its potential benefits for smart homes
    3. Existing research on using web3 technology for smart home security and privacy
3. Methodology
    1. Description of the smart home system design using web3 technology, including hardware and software components
    2. Implementation details and justification for design choices
    3. Evaluation plan for assessing the security and privacy of the system
4. Results and Analysis
    1. Evaluation of the implemented system with respect to security and privacy metrics
    2. Comparison with existing solutions and analysis of strengths and weaknesses
    3. Discussion of limitations and potential areas for improvement
5. Conclusion and Future Work
    1. Summary of the study's contributions and main findings
    2. Implications and significance of the results for the smart home industry and related fields
    3. Recommendations for future research and development
6. 参考资料

</RoboAcademyDialog>

<RoboAcademyText>
准备工作完成后，我们现在可以继续进行论文的第一部分——引言。
</RoboAcademyText>
  

