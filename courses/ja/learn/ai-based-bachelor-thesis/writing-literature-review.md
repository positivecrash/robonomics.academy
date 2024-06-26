---
title: "執筆：文献レビュー"
description: AIパワードツールで学士論文を素早く始める
metaOptions: [AIパワードツールで学士論文を学ぶ、素早く始める]
defaultName: Quickstart Your Bachelor's Thesis with AI-powered Tools
---

<RoboAcademyText fWeight="500">
では、おそらくほとんどの学術的な作業の中で最も退屈な部分である文献検索とソースの分析を書き始めます。
</RoboAcademyText>

一見すると、AIアシスタントは他の何よりもこのタスクをうまく処理できるはずです。やるべきことは、インターネット上で関連する作品を見つけ、そのテキストをある形で取得し、分析するだけです。しかし、このタスクには多くの落とし穴が見つかっており、それについてさらに議論されます。


## 最初の試み

より簡単なタスクから始めましょう。既存の導入テキストを使用して、それに関連する参照文献と引用を追加し、その文の関連性を確認します。ChatGPTとBing Chatへの最初のリクエストは次のようになります（ソースの数を指定してください）：

<RoboAcademyDialog>

Add 10 references and quotes for イントロduction part to support the statements in the text.
</RoboAcademyDialog>

両方のチャットボットは、ソースをテキスト内に正しく配置することができました...しかし、実際のソースを見つけることに完全に失敗しました。問題は、AIアシスタントが存在しないソース（しかし実際のものに非常に似ている）を発明し、それをテキストに追加し、架空の著者を引用し始めたことです。

<RoboAcademyDialog>

C. Li et al. "Blockchain-based secure and trustworthy data sharing scheme for smart homes." IEEE Transactions on Industrial Informatics, vol. 16, no. 2, pp. 1236-1245, 2020.

"The deployment of smart home systems has led to concerns over data security and privacy. Blockchain technology has been proposed as a solution to these concerns, as it enables secure and trustworthy data sharing among smart home devices. This paper proposes a blockchain-based secure and trustworthy data sharing scheme for smart homes. The proposed scheme uses blockchain to ensure the integrity and confidentiality of data generated by smart home devices."

</RoboAcademyDialog>

自然な見た目に注目してください：文献の形式に従っており、実際のIEEEジャーナルが引用されています。使用を防ぐ唯一の方法は、Google Scholarで確認することです。

<RoboAcademyNote title="Warning" type="warning">
 AIアシスタントによって提供されたリンク、引用、ソースは常に二重チェックしてください。
</RoboAcademyNote>

この問題は[幻覚効果](https://en.wikipedia.org/wiki/Hallucination_(artificial_intelligence))と呼ばれ、現在、人工知能の専門家の間で多くの論争を引き起こしています。幻覚は検証が非常にコストがかかるレベルで発生する可能性があるため（たとえば、AIが実際に存在しない複雑な流体力学現象を詳細に説明することがある）、その信頼性の低さによりAIサービスのすべての助けが損なわれます。

比較のため、さまざまなサービスからの統計データが次のようになります：

- ChatGPT：10のうち9つのソースが偽物
- Bing Chat：10のうち7つのソースが偽物
- Auto-GPT：何らかの理由で書誌ウェブサイトのパーサーの開発を開始したため、タスクを完了しませんでした。

インターネットにアクセスできる場合AIサービスはより良く機能しますが、同時に、存在しないソースへの直接リンクを作成する可能性があります。もちろん、全体的な結果は印象的ではありませんが、この問題を心に留めて続けましょう。

## リクエストの明確化

数回の試みの後、最良の戦術は、導入テキストを段落ごとに提供してソースを求めることであることがわかりました。さらに、AIは科学論文の代わりにブログ、フォーラム、通常のウェブサイトの記事からソースを提供することを好むことがわかりました。したがって、アシスタントが記事を選択すべき特定のソース（IEEE、Springerジャーナル、arXivウェブアーカイブなど）を指定する価値があります。

<RoboAcademyDialog>

Find 5 scientific sources that prove statements in this text. Use only arXiv, IEEE, Springer articles from 2018 to 2023: "THE_PARAGRAPH"
</RoboAcademyDialog>

このリクエストはBing Chatのみに使用されました。ChatGPTはインターネットアクセスがないため、タスクをうまく処理できませんでした。結果ははるかに良くなりました：Bing Chatは時々すべての実際のソースを提供し、さらに、ソースがどのテキストの記述をサポートしているかを説明する簡単な説明を提供しました。ただし、Bing Chatは見つかったソースのbibtexレコードを作成すること失敗しました（再び幻覚を生じさせるため）、そのため最後にGoogle Scholarの手動使用が必要でした。


## 文献レビューに移動

さて、学士論文の第2部のための完全な文献検索のより複雑なタスクに移ることができます。まず、計画に従って、次のトピックについて2つのサブセクションを書いてみましょう：

<RoboAcademyDialog>

&mdash; 概要 of smart home technology and its security and privacy issues
<br/>&mdash; イントロduction to web3 technology and its potential benefits for smart homes
</RoboAcademyDialog>

次のリクエストが使用されました：

<RoboAcademyDialog>

Write a literature review with "THE_TOPIC" in 300 words. Write as if you are writing part of a technical scientific article.
</RoboAcademyDialog>

AIがデフォルトでブログに掲載されるよりも適したテキストを書くため、最後のスタイルに関する明確化が追加されました。最初に得られた結果はあまり印象的ではありませんでしたが、Amazonのスマートデバイスの広告など、不要な詳細が多すぎるものでした。それにもかかわらず、結果はこのサブセクションのプランとして使用でき、その後の追加のリクエストが可能です。最終的に、次の構造が達成されました：

- スマートホーム技術の説明
- デバイスとその使用例の例
- スマートホーム技術の既存の問題
- これらの問題に対処するための解決策の例：
- 既存の解決策の欠点

全体的に、得られたテキストは学士論文に使用できます。同様のプロセスがWeb3技術に関する2番目のトピックで行われ、その後、上記のスキームに従って各サブセクションのための対応するソースが見つかりました。

## 分析用の記事を見つける

分析の標準的な戦術には、強力な書誌検索サービス（Scopus、Web of Science、Google Scholar）を使用して、トピックに関する最も関連性の高い5〜10の引用された作品を見つけることが含まれます。次のリクエストを使用してこれを試してみましょう:

<RoboAcademyDialog>

Find five most cited technical scientific articles about developing a smart home systems based of web3 or blockchain or smart contract among IEEE, Springer and arXiv articles from 2020 to 2023
</RoboAcademyDialog>

残念ながら、結果は良質ではありませんでした：

- ChatGPTはインターネットにアクセスできず、2021年までの情報に限定されていると強調しました。提案された5つのソースはすべて存在しないものでした。
- Bing Chatは5つの代わりに3つの実際のソースを見つけましたが、残念ながら1）そのうちの2つだけがトピックに関連していました、2）それらは最も引用されたものではありませんでした（そのうち1つは引用が全くありませんでした）、3）いくつかのケースではソースが偽物でした（AIはそれらの引用数さえ提供していました）。
- 与えられたトピックに関して、Auto-GPTが最も正確であることがわかりましたが、最も引用された記事を選択することができませんでした。Google Scholarを使用すべきだと明確にした後もです。

残念ながら、これらのAIサービスの能力の範囲内には、科学記事のための専門的な文献検索はまだ含まれていませんので、Google Scholarを使用してトップ5の最も引用された記事を見つけることが簡単で速いです。

## 関連作品のブルートフォース解析

その後、何らかの方法で、見つかった記事の全文を取得する必要があります。通常の場合、それぞれを個人的に読む必要がありますが、AIアシスタントから要約テキストをリクエストしようとします。すぐに問題に直面します:

1）記事は通常、2列のテキストを持つPDF形式で利用可能です。チャットボットは単純にPDFファイルを読むことができませんし、Auto-GPTは現在この形式を読むことができません（しかし、それ自体でこの問題の解決策を見つけようとしましたが、失敗しました！）

<RoboAcademyTerminal title="AutoGPT Terminal">

**SYSTEM:**  Command read_file returned: Error: 'utf-8' codec can't decode byte 0xe2 in position 10: invalid continuation byte
THOUGHTS:  It looks like I am encountering an encoding issue while trying to open the edgechain PDF file. I can try to extract text from the PDF using the 'tika' library and analyze the contents. I'll use the 'execute_shell' command to install the 'tika' library before using it to extract text from the PDF file.

**REASONING:**  Due to encoding issues trying to read the PDF file, I need a different approach to read the contents of the PDF file in order to analyze and summarize the article.

</RoboAcademyTerminal>

とにかく、PDF記事は画像や表を含まないプレーンテキスト形式に変換する必要があります。これには、[PyMuPDF](https://pymupdf.readthedocs.io/en/latest/)、[GROBID](https://grobid.readthedocs.io/en/latest/イントロduction/)、および[PDFMiner](https://pdfminersix.readthedocs.io/en/latest/)などのソフトウェアを使用できます。

2）これらのAIツールを使用して記事全体を分析することを実質的に妨げるより深刻な問題があります。残念ながら、現在の形態では、GPTには制限されたコンテキスト長があり、これによりAuto-GPTは単に分析を開始することを拒否し、チャットボットは会話の最初を失います:

<RoboAcademyTerminal title="AutoGPT Terminal">

openai.error.InvalidRequestError: This model's maximum context length is 8191 tokens, however you requested 15615 tokens (15615 in your prompt; 0 for the completion). Please reduce your prompt; or completion length.

</RoboAcademyTerminal>

## 関連作品の段階的な分析

したがって、少しの策略を使い、記事をページごとにAIに通し、受け取ったテキストの短い要約をリクエストします。そ後、これらの要約をまとめて最終的な記事の分析を行います。たとえば、ChatGPTを使用することができます。

<RoboAcademyDialog>

<ChatGPT/>

EdgeChain: An Edge-IoT Framework and Prototype Based on Blockchain and Smart Contracts

This article describes EdgeChain, a framework, which addresses scalability and security challenges in the Internet of Things domain by leveraging edge computing, blockchain technology, and smart contracts. Authors highlight the weaknesses of IoT devices and centralized cloud computing and proposes edge computing as a solution. The framework employs a permissioned blockchain and an internal currency system to connect IoT devices with edge cloud resources. Smart contracts enforce regulations and automate policy enforcement.

The paper outlines the key features of the EdgeChain framework, including permissioned blockchain, credit-based resource management, smart contract enforcement, compatibility with legacy devices, and distributed deployment options. It explains the modules of the framework, such as the IoT Proxy, smart contracts interface, blockchain server, and application interface.

Furthermore, the text delves into the deployment of blockchain, development of smart contracts, device registration, and IoT behavior regulation within the EdgeChain framework. It emphasizes thorough testing, legacy device support, and monitoring of device behaviors for policy enforcement.

Overall, the EdgeChain framework shows promise in addressing scalability and security challenges in the IoT domain through the integration of edge computing, blockchain, and smart contracts. The prototype evaluation indicates its potential as a secure and distributed platform for future IoT applications.

</RoboAcademyDialog>

次に、残りの記事に対して同じ分析プロセスを繰り返す必要があり、それでは、私たちの学士論文の完全な文献レビューができます。最終的に、最良の記事を選択し、そのテキストを抽出し、AIが生成した結果を確認して、それらを参照とともに一貫したテキストにまとめる前に、タスク全体は標準の2-3週間ではなく約2日かかりました。

<RoboAcademyText>

今、私たちは論文の本質、つまり私たちの作業の方法の説明に進むことができます。

</RoboAcademyText>