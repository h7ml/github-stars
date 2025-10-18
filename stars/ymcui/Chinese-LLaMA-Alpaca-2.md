---
project: Chinese-LLaMA-Alpaca-2
stars: 7171
description: 中文LLaMA-2 & Alpaca-2大模型二期项目 + 64K超长上下文模型 (Chinese LLaMA-2 & Alpaca-2 LLMs with 64K long context models)
url: https://github.com/ymcui/Chinese-LLaMA-Alpaca-2
---

Chinese-LLaMA-Alpaca-3项目启动！
===========================

**🇨🇳中文** | **🌐English** | **📖文档/Docs** | **❓提问/Issues** | **💬讨论/Discussions** | **⚔️竞技场/Arena**

  
  

本项目基于Meta发布的可商用大模型Llama-2开发，是中文LLaMA&Alpaca大模型的第二期项目，开源了**中文LLaMA-2基座模型和Alpaca-2指令精调大模型**。这些模型**在原版Llama-2的基础上扩充并优化了中文词表**，使用了大规模中文数据进行增量预训练，进一步提升了中文基础语义和指令理解能力，相比一代相关模型获得了显著性能提升。相关模型**支持FlashAttention-2训练**。标准版模型支持4K上下文长度，**长上下文版模型支持16K、64k上下文长度**。**RLHF系列模型**为标准版模型基础上进行人类偏好对齐精调，相比标准版模型在**正确价值观体现**方面获得了显著性能提升。

#### 本项目主要内容

-   🚀 针对Llama-2模型扩充了**新版中文词表**，开源了中文LLaMA-2和Alpaca-2大模型
-   🚀 开源了预训练脚本、指令精调脚本，用户可根据需要进一步训练模型
-   🚀 使用个人电脑的CPU/GPU快速在本地进行大模型量化和部署体验
-   🚀 支持🤗transformers, llama.cpp, text-generation-webui, LangChain, privateGPT, vLLM等LLaMA生态

#### 已开源的模型

-   基座模型（4K上下文）：Chinese-LLaMA-2 (1.3B, 7B, 13B)
-   聊天模型（4K上下文）：Chinese-Alpaca-2 (1.3B, 7B, 13B)
-   长上下文模型（16K/64K）：
    -   Chinese-LLaMA-2-16K (7B, 13B) 、Chinese-Alpaca-2-16K (7B, 13B)
    -   Chinese-LLaMA-2-64K (7B)、Chinese-Alpaca-2-64K (7B)
-   偏好对齐模型：Chinese-Alpaca-2-RLHF (1.3B, 7B)

* * *

中文LLaMA&Alpaca大模型 | 多模态中文LLaMA&Alpaca大模型 | 多模态VLE | 中文MiniRBT | 中文LERT | 中英文PERT | 中文MacBERT | 中文ELECTRA | 中文XLNet | 中文BERT | 知识蒸馏工具TextBrewer | 模型裁剪工具TextPruner | 蒸馏裁剪一体化GRAIN

新闻
--

**\[2024/04/30\] Chinese-LLaMA-Alpaca-3 已正式发布，开源基于Llama-3的Llama-3-Chinese-8B和Llama-3-Chinese-8B-Instruct，推荐所有一期、二期项目用户升级至三代模型，请参阅：https://github.com/ymcui/Chinese-LLaMA-Alpaca-3**

\[2024/03/27\] 本项目已入驻机器之心SOTA!模型平台，欢迎关注：https://sota.jiqizhixin.com/project/chinese-llama-alpaca-2

\[2024/01/23\] 添加新版GGUF模型（imatrix量化）、AWQ量化模型，支持vLLM下加载YaRN长上下文模型。详情查看📚 v4.1版本发布日志

\[2023/12/29\] 发布长上下文模型Chinese-LLaMA-2-7B-64K和Chinese-Alpaca-2-7B-64K，同时发布经过人类偏好对齐（RLHF）的Chinese-Alpaca-2-RLHF（1.3B/7B）。详情查看📚 v4.0版本发布日志

\[2023/09/01\] 发布长上下文模型Chinese-Alpaca-2-7B-16K和Chinese-Alpaca-2-13B-16K，该模型可直接应用于下游任务，例如privateGPT等。详情查看📚 v3.1版本发布日志

\[2023/08/25\] 发布长上下文模型Chinese-LLaMA-2-7B-16K和Chinese-LLaMA-2-13B-16K，支持16K上下文，并可通过NTK方法进一步扩展至24K+。详情查看📚 v3.0版本发布日志

\[2023/08/14\] 发布Chinese-LLaMA-2-13B和Chinese-Alpaca-2-13B，添加text-generation-webui/LangChain/privateGPT支持，添加CFG Sampling解码方法等。详情查看📚 v2.0版本发布日志

\[2023/08/02\] 添加FlashAttention-2训练支持，基于vLLM的推理加速支持，提供长回复系统提示语模板等。详情查看📚 v1.1版本发布日志

\[2023/07/31\] 正式发布Chinese-LLaMA-2-7B（基座模型），使用120G中文语料增量训练（与一代Plus系列相同）；进一步通过5M条指令数据精调（相比一代略微增加），得到Chinese-Alpaca-2-7B（指令/chat模型）。详情查看📚 v1.0版本发布日志

\[2023/07/19\] 🚀启动中文LLaMA-2、Alpaca-2开源大模型项目

内容导引
----

章节

描述

💁🏻‍♂️模型简介

简要介绍本项目相关模型的技术特点

⏬模型下载

中文LLaMA-2、Alpaca-2大模型下载地址

💻推理与部署

介绍了如何对模型进行量化并使用个人电脑部署并体验大模型

💯系统效果

介绍了模型在部分任务上的效果

📝训练与精调

介绍了如何训练和精调中文LLaMA-2、Alpaca-2大模型

❓常见问题

一些常见问题的回复

模型简介
----

本项目推出了基于Llama-2的中文LLaMA-2以及Alpaca-2系列模型，相比一期项目其主要特点如下：

#### 📖 经过优化的中文词表

-   在一期项目中，我们针对一代LLaMA模型的32K词表扩展了中文字词（LLaMA：49953，Alpaca：49954）
-   在本项目中，我们**重新设计了新词表**（大小：55296），进一步提升了中文字词的覆盖程度，同时统一了LLaMA/Alpaca的词表，避免了因混用词表带来的问题，以期进一步提升模型对中文文本的编解码效率

#### ⚡ 基于FlashAttention-2的高效注意力

-   FlashAttention-2是高效注意力机制的一种实现，相比其一代技术具有**更快的速度和更优化的显存占用**
-   当上下文长度更长时，为了避免显存爆炸式的增长，使用此类高效注意力技术尤为重要
-   本项目的所有模型均使用了FlashAttention-2技术进行训练

#### 🚄 基于PI和YaRN的超长上下文扩展技术

-   在一期项目中，我们实现了基于NTK的上下文扩展技术，可在不继续训练模型的情况下支持更长的上下文
-   基于位置插值PI和NTK等方法推出了16K长上下文版模型，支持16K上下文，并可通过NTK方法最高扩展至24K-32K
-   基于YaRN方法进一步推出了64K长上下文版模型，支持64K上下文
-   进一步设计了**方便的自适应经验公式**，无需针对不同的上下文长度设置NTK超参，降低了使用难度

#### 🤖 简化的中英双语系统提示语

-   在一期项目中，中文Alpaca系列模型使用了Stanford Alpaca的指令模板和系统提示语
-   初步实验发现，Llama-2-Chat系列模型的默认系统提示语未能带来统计显著的性能提升，且其内容过于冗长
-   本项目中的Alpaca-2系列模型简化了系统提示语，同时遵循Llama-2-Chat指令模板，以便更好地适配相关生态

#### 👮 人类偏好对齐

-   在一期项目中，中文Alpaca系列模型仅完成预训练和指令精调，获得了基本的对话能力
-   通过基于人类反馈的强化学习（RLHF）实验，发现可显著提升模型传递正确价值观的能力
-   本项目推出了Alpaca-2-RLHF系列模型，使用方式与SFT模型一致

下图展示了本项目以及一期项目推出的所有大模型之间的关系。

模型下载
----

### 模型选择指引

以下是中文LLaMA-2和Alpaca-2模型的对比以及建议使用场景。**如需聊天交互，请选择Alpaca而不是LLaMA。**

对比项

中文LLaMA-2

中文Alpaca-2

模型类型

**基座模型**

**指令/Chat模型（类ChatGPT）**

已开源大小

1.3B、7B、13B

1.3B、7B、13B

训练类型

Causal-LM (CLM)

指令精调

训练方式

7B、13B：LoRA + 全量emb/lm-head  
1.3B：全量

7B、13B：LoRA + 全量emb/lm-head  
1.3B：全量

基于什么模型训练

原版Llama-2（非chat版）

中文LLaMA-2

训练语料

无标注通用语料（120G纯文本）

有标注指令数据（500万条）

词表大小\[1\]

55,296

55,296

上下文长度\[2\]

标准版：4K（12K-18K）  
长上下文版（PI）：16K（24K-32K）  
长上下文版（YaRN）：64K

标准版：4K（12K-18K）  
长上下文版（PI）：16K（24K-32K）  
长上下文版（YaRN）：64K

输入模板

不需要

需要套用特定模板\[3\]，类似Llama-2-Chat

适用场景

文本续写：给定上文，让模型生成下文

指令理解：问答、写作、聊天、交互等

不适用场景

指令理解 、多轮聊天等

文本无限制自由生成

偏好对齐

无

RLHF版本（1.3B、7B）

Note

\[1\] _本项目一代模型和二代模型的词表不同，请勿混用。二代LLaMA和Alpaca的词表相同。_  
\[2\] _括号内表示基于NTK上下文扩展支持的最大长度。_  
\[3\] _Alpaca-2采用了Llama-2-chat系列模板（格式相同，提示语不同），而不是一代Alpaca的模板，请勿混用。_  
\[4\] _不建议单独使用1.3B模型，而是通过投机采样搭配更大的模型（7B、13B）使用。_  

### 完整模型下载

以下是完整版模型，直接下载即可使用，无需其他合并步骤。推荐网络带宽充足的用户。

模型名称

类型

大小

下载地址

GGUF

Chinese-LLaMA-2-13B

基座模型

24.7 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

\[🤗HF\]

Chinese-LLaMA-2-7B

基座模型

12.9 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

\[🤗HF\]

Chinese-LLaMA-2-1.3B

基座模型

2.4 GB

\[🤗HF\] \[🤖ModelScope\]\[Baidu\]

\[🤗HF\]

Chinese-Alpaca-2-13B

指令模型

24.7 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

\[🤗HF\]

Chinese-Alpaca-2-7B

指令模型

12.9 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

\[🤗HF\]

Chinese-Alpaca-2-1.3B

指令模型

2.4 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

\[🤗HF\]

#### 长上下文版模型

以下是长上下文版模型，**推荐以长文本为主的下游任务使用**，否则建议使用上述标准版。

模型名称

类型

大小

下载地址

GGUF

Chinese-LLaMA-2-7B-64K 🆕

基座模型

12.9 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

\[🤗HF\]

Chinese-Alpaca-2-7B-64K 🆕

指令模型

12.9 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

\[🤗HF\]

Chinese-LLaMA-2-13B-16K

基座模型

24.7 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

\[🤗HF\]

Chinese-LLaMA-2-7B-16K

基座模型

12.9 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

\[🤗HF\]

Chinese-Alpaca-2-13B-16K

指令模型

24.7 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

\[🤗HF\]

Chinese-Alpaca-2-7B-16K

指令模型

12.9 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

\[🤗HF\]

#### RLHF版模型

以下是人类偏好对齐版模型，对涉及法律、道德的问题较标准版有更优的价值导向。

模型名称

类型

大小

下载地址

GGUF

Chinese-Alpaca-2-7B-RLHF 🆕

指令模型

12.9 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

\[🤗HF\]

Chinese-Alpaca-2-1.3B-RLHF 🆕

指令模型

2.4 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

\[🤗HF\]

#### AWQ版模型

AWQ（Activation-aware Weight Quantization）是一种高效的模型量化方案，目前可兼容🤗transformers、llama.cpp等主流框架。

本项目模型的AWQ预搜索结果可通过以下链接获取：https://huggingface.co/hfl/chinese-llama-alpaca-2-awq

-   生成AWQ量化模型（AWQ官方目录）：https://github.com/mit-han-lab/llm-awq
-   llama.cpp中使用AWQ：https://github.com/ggerganov/llama.cpp/tree/master/awq-py

### LoRA模型下载

以下是LoRA模型（含emb/lm-head），与上述完整模型一一对应。需要注意的是**LoRA模型无法直接使用**，必须按照教程与重构模型进行合并。推荐网络带宽不足，手头有原版Llama-2且需要轻量下载的用户。

模型名称

类型

合并所需基模型

大小

LoRA下载地址

Chinese-LLaMA-2-LoRA-13B

基座模型

Llama-2-13B-hf

1.5 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

Chinese-LLaMA-2-LoRA-7B

基座模型

Llama-2-7B-hf

1.1 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

Chinese-Alpaca-2-LoRA-13B

指令模型

Llama-2-13B-hf

1.5 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

Chinese-Alpaca-2-LoRA-7B

指令模型

Llama-2-7B-hf

1.1 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

以下是长上下文版模型，**推荐以长文本为主的下游任务使用**，否则建议使用上述标准版。

模型名称

类型

合并所需基模型

大小

LoRA下载地址

Chinese-LLaMA-2-LoRA-7B-64K 🆕

基座模型

Llama-2-7B-hf

1.1 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

Chinese-Alpaca-2-LoRA-7B-64K 🆕

指令模型

Llama-2-7B-hf

1.1 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

Chinese-LLaMA-2-LoRA-13B-16K

基座模型

Llama-2-13B-hf

1.5 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

Chinese-LLaMA-2-LoRA-7B-16K

基座模型

Llama-2-7B-hf

1.1 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

Chinese-Alpaca-2-LoRA-13B-16K

指令模型

Llama-2-13B-hf

1.5 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

Chinese-Alpaca-2-LoRA-7B-16K

指令模型

Llama-2-7B-hf

1.1 GB

\[🤗HF\] \[🤖ModelScope\] \[Baidu\]

Important

LoRA模型无法单独使用，必须与原版Llama-2进行合并才能转为完整模型。请通过以下方法对模型进行合并。

-   **在线转换**：Colab用户可利用本项目提供的notebook进行在线转换并量化模型
-   **手动转换**：离线方式转换，生成不同格式的模型，以便进行量化或进一步精调

推理与部署
-----

本项目中的相关模型主要支持以下量化、推理和部署方式，具体内容请参考对应教程。

工具

特点

CPU

GPU

量化

GUI

API

vLLM§

16K‡

64K‡

投机采样

教程

**llama.cpp**

丰富的量化选项和高效本地推理

✅

✅

✅

❌

✅

❌

✅

✅

✅

link

**🤗Transformers**

原生transformers推理接口

✅

✅

✅

✅

❌

✅

✅

✅

✅

link

**Colab Demo**

在Colab中启动交互界面

✅

✅

✅

✅

❌

✅

✅

✅

✅

link

**仿OpenAI API调用**

仿OpenAI API接口的服务器Demo

✅

✅

✅

❌

✅

✅

✅

✅

❌

link

**text-generation-webui**

前端Web UI界面的部署方式

✅

✅

✅

✅

✅†

❌

✅

❌

❌

link

**LangChain**

适合二次开发的大模型应用开源框架

✅†

✅

✅†

❌

❌

❌

✅

✅

❌

link

**privateGPT**

基于LangChain的多文档本地问答框架

✅

✅

✅

❌

❌

❌

✅

❌

❌

link

Note

† 工具支持该特性，但教程中未实现，详细说明请参考对应官方文档  
‡ 指是否支持长上下文版本模型（需要第三方库支持自定义RoPE）  
§ vLLM后端不支持长上下文版本模型  

系统效果
----

为了评测相关模型的效果，本项目分别进行了生成效果评测和客观效果评测（NLU类），从不同角度对大模型进行评估。需要注意的是，综合评估大模型能力仍然是亟待解决的重要课题，单个数据集的结果并不能综合评估模型性能。推荐用户在自己关注的任务上进行测试，选择适配相关任务的模型。

### 生成效果评测

为了更加直观地了解模型的生成效果，本项目仿照Fastchat Chatbot Arena推出了模型在线对战平台，可浏览和评测模型回复质量。对战平台提供了胜率、Elo评分等评测指标，并且可以查看两两模型的对战胜率等结果。题库来自于一期项目人工制作的200题，以及在此基础上额外增加的题目。生成回复具有随机性，受解码超参、随机种子等因素影响，因此相关评测并非绝对严谨，结果仅供晾晒参考，欢迎自行体验。部分生成样例请查看examples目录。

**⚔️ 模型竞技场：http://llm-arena.ymcui.com**

系统

对战胜率（无平局） ↓

Elo评分

**Chinese-Alpaca-2-13B-16K**

86.84%

1580

**Chinese-Alpaca-2-13B**

72.01%

1579

Chinese-Alpaca-Pro-33B

64.87%

1548

**Chinese-Alpaca-2-7B**

64.11%

1572

Chinese-Alpaca-Pro-7B

62.05%

1500

**Chinese-Alpaca-2-7B-16K**

61.67%

1540

Chinese-Alpaca-Pro-13B

61.26%

1567

Chinese-Alpaca-Plus-33B

31.29%

1401

Chinese-Alpaca-Plus-13B

23.43%

1329

Chinese-Alpaca-Plus-7B

20.92%

1379

Note

以上结果截至2023年9月1日。最新结果请进入**⚔️竞技场**进行查看。

### 客观效果评测：C-Eval

C-Eval是一个全面的中文基础模型评估套件，其中验证集和测试集分别包含1.3K和12.3K个选择题，涵盖52个学科。实验结果以“zero-shot / 5-shot”进行呈现。C-Eval推理代码请参考本项目：📖GitHub Wiki

LLaMA Models

Valid

Test

Alpaca Models

Valid

Test

**Chinese-LLaMA-2-13B**

40.6 / 42.7

38.0 / 41.6

**Chinese-Alpaca-2-13B**

44.3 / 45.9

42.6 / 44.0

**Chinese-LLaMA-2-7B**

28.2 / 36.0

30.3 / 34.2

**Chinese-Alpaca-2-7B**

41.3 / 42.9

40.3 / 39.5

Chinese-LLaMA-Plus-33B

37.4 / 40.0

35.7 / 38.3

Chinese-Alpaca-Plus-33B

46.5 / 46.3

44.9 / 43.5

Chinese-LLaMA-Plus-13B

27.3 / 34.0

27.8 / 33.3

Chinese-Alpaca-Plus-13B

43.3 / 42.4

41.5 / 39.9

Chinese-LLaMA-Plus-7B

27.3 / 28.3

26.9 / 28.4

Chinese-Alpaca-Plus-7B

36.7 / 32.9

36.4 / 32.3

### 客观效果评测：CMMLU

CMMLU是另一个综合性中文评测数据集，专门用于评估语言模型在中文语境下的知识和推理能力，涵盖了从基础学科到高级专业水平的67个主题，共计11.5K个选择题。CMMLU推理代码请参考本项目：📖GitHub Wiki

LLaMA Models

Test (0/few-shot)

Alpaca Models

Test (0/few-shot)

**Chinese-LLaMA-2-13B**

38.9 / 42.5

**Chinese-Alpaca-2-13B**

43.2 / 45.5

**Chinese-LLaMA-2-7B**

27.9 / 34.1

**Chinese-Alpaca-2-7B**

40.0 / 41.8

Chinese-LLaMA-Plus-33B

35.2 / 38.8

Chinese-Alpaca-Plus-33B

46.6 / 45.3

Chinese-LLaMA-Plus-13B

29.6 / 34.0

Chinese-Alpaca-Plus-13B

40.6 / 39.9

Chinese-LLaMA-Plus-7B

25.4 / 26.3

Chinese-Alpaca-Plus-7B

36.8 / 32.6

### 长上下文版模型评测

LongBench是一个大模型长文本理解能力的评测基准，由6大类、20个不同的任务组成，多数任务的平均长度在5K-15K之间，共包含约4.75K条测试数据。以下是本项目长上下文版模型在该中文任务（含代码任务）上的评测效果。LongBench推理代码请参考本项目：📖GitHub Wiki

Models

单文档QA

多文档QA

摘要

Few-shot学习

代码补全

合成任务

Avg

**Chinese-Alpaca-2-7B-64K**

44.7

28.1

14.4

39.0

44.6

5.0

29.3

**Chinese-LLaMA-2-7B-64K**

27.2

16.4

6.5

33.0

7.8

5.0

16.0

**Chinese-Alpaca-2-13B-16K**

47.9

26.7

13.0

22.3

46.6

21.5

29.7

Chinese-Alpaca-2-13B

38.4

20.0

11.9

17.3

46.5

8.0

23.7

**Chinese-Alpaca-2-7B-16K**

46.4

23.3

14.3

29.0

49.6

9.0

28.6

Chinese-Alpaca-2-7B

34.0

17.4

11.8

21.3

50.3

4.5

23.2

**Chinese-LLaMA-2-13B-16K**

36.7

17.7

3.1

29.8

13.8

3.0

17.3

Chinese-LLaMA-2-13B

28.3

14.4

4.6

16.3

10.4

5.4

13.2

**Chinese-LLaMA-2-7B-16K**

33.2

15.9

6.5

23.5

10.3

5.3

15.8

Chinese-LLaMA-2-7B

19.0

13.9

6.4

11.0

11.0

4.7

11.0

### 量化效果评测

以Chinese-LLaMA-2-7B为例，对比不同精度下的模型大小、PPL（困惑度）、C-Eval效果，方便用户了解量化精度损失。PPL以4K上下文大小计算，C-Eval汇报的是valid集合上zero-shot和5-shot结果。

精度

模型大小

PPL

C-Eval

FP16

12.9 GB

9.373

28.2 / 36.0

8-bit量化

6.8 GB

9.476

26.8 / 35.4

4-bit量化

3.7 GB

10.132

25.5 / 32.8

特别地，以下是在llama.cpp下不同量化方法的评测数据，供用户参考，速度以ms/tok计，测试设备为M1 Max。具体细节见📖GitHub Wiki

llama.cpp

F16

Q2\_K

Q3\_K

Q4\_0

Q4\_1

Q4\_K

Q5\_0

Q5\_1

Q5\_K

Q6\_K

Q8\_0

PPL

9.128

11.107

9.576

9.476

9.576

9.240

9.156

9.213

9.168

9.133

9.129

Size

12.91G

2.41G

3.18G

3.69G

4.08G

3.92G

4.47G

4.86G

4.59G

5.30G

6.81G

CPU Speed

117

42

51

39

44

43

48

51

50

54

65

GPU Speed

53

19

21

17

18

20

x

x

25

26

x

### 投机采样加速效果评测

通过投机采样方法并借助Chinese-LLaMA-2-1.3B和Chinese-Alpaca-2-1.3B，可以分别加速7B、13B的LLaMA和Alpaca模型的推理速度。以下是使用投机采样脚本在1\*A40-48G上解码生成效果评测中的问题测得的平均速度（速度以ms/token计，模型均为fp16精度），供用户参考。详细说明见📖GitHub Wiki。

草稿模型

草稿模型速度

目标模型

目标模型速度

投机采样速度（加速比）

Chinese-LLaMA-2-1.3B

7.6

Chinese-LLaMA-2-7B

49.3

36.0（1.37x）

Chinese-LLaMA-2-1.3B

7.6

Chinese-LLaMA-2-13B

66.0

47.1（1.40x）

Chinese-Alpaca-2-1.3B

8.1

Chinese-Alpaca-2-7B

50.2

34.9（1.44x）

Chinese-Alpaca-2-1.3B

8.2

Chinese-Alpaca-2-13B

67.0

41.6（1.61x）

### 人类偏好对齐（RLHF）版本评测

#### 对齐水平

为评估中文模型与人类价值偏好对齐程度，我们自行构建了评测数据集，覆盖了道德、色情、毒品、暴力等人类价值偏好重点关注的多个方面。实验结果以价值体现正确率进行呈现（体现正确价值观题目数 / 总题数）。

Alpaca Models

Accuracy

Alpaca Models

Accuracy

Chinese-Alpaca-2-1.3B

79.3%

Chinese-Alpaca-2-7B

88.3%

**Chinese-Alpaca-2-1.3B-RLHF**

95.8%

**Chinese-Alpaca-2-7B-RLHF**

97.5%

#### 客观效果评测：C-Eval & CMMLU

Alpaca Models

C-Eval (0/few-shot)

CMMLU (0/few-shot)

Chinese-Alpaca-2-1.3B

23.8 / 26.8

24.8 / 25.1

Chinese-Alpaca-2-7B

42.1 / 41.0

40.0 / 41.8

**Chinese-Alpaca-2-1.3B-RLHF**

23.6 / 27.1

24.9 / 25.0

**Chinese-Alpaca-2-7B-RLHF**

40.6 / 41.2

39.5 / 41.0

训练与精调
-----

### 预训练

-   在原版Llama-2的基础上，利用大规模无标注数据进行增量训练，得到Chinese-LLaMA-2系列基座模型
-   训练数据采用了一期项目中Plus版本模型一致的数据，其总量约120G纯文本文件
-   训练代码参考了🤗transformers中的run\_clm.py，使用方法见📖预训练脚本Wiki

### 指令精调

-   在Chinese-LLaMA-2的基础上，利用有标注指令数据进行进一步精调，得到Chinese-Alpaca-2系列模型
-   训练数据采用了一期项目中Pro版本模型使用的指令数据，其总量约500万条指令数据（相比一期略增加）
-   训练代码参考了Stanford Alpaca项目中数据集处理的相关部分，使用方法见📖指令精调脚本Wiki

### RLHF精调

-   在Chinese-Alpaca-2系列模型基础上，利用偏好数据和PPO算法进行人类偏好对齐精调，得到Chinese-Alpaca-2-RLHF系列模型
-   训练数据基于多个开源项目中的人类偏好数据和本项目指令精调数据进行采样，奖励模型阶段、强化学习阶段分别约69.5K、25.6K条样本
-   训练代码基于DeepSpeed-Chat开发，具体流程见📖奖励模型Wiki和📖强化学习Wiki

常见问题
----

请在提Issue前务必先查看FAQ中是否已存在解决方案。具体问题和解答请参考本项目 📖GitHub Wiki

```
问题1：本项目和一期项目的区别？
问题2：模型能否商用？
问题3：接受第三方Pull Request吗？
问题4：为什么不对模型做全量预训练而是用LoRA？
问题5：二代模型支不支持某些支持一代LLaMA的工具？
问题6：Chinese-Alpaca-2是Llama-2-Chat训练得到的吗？
问题7：为什么24G显存微调Chinese-Alpaca-2-7B会OOM？
问题8：可以使用16K长上下文版模型替代标准版模型吗？
问题9：如何解读第三方公开榜单的结果？
问题10：会出34B或者70B级别的模型吗？
问题11：为什么长上下文版模型是16K，不是32K或者100K？
问题12：为什么Alpaca模型会回复说自己是ChatGPT？
问题13：为什么pt_lora_model或者sft_lora_model下的adapter_model.bin只有几百k？
```

引用
--

如果您使用了本项目的相关资源，请参考引用本项目的技术报告：https://arxiv.org/abs/2304.08177

```
@article{Chinese-LLaMA-Alpaca,
    title={Efficient and Effective Text Encoding for Chinese LLaMA and Alpaca},
    author={Cui, Yiming and Yang, Ziqing and Yao, Xin},
    journal={arXiv preprint arXiv:2304.08177},
    url={https://arxiv.org/abs/2304.08177},
    year={2023}
}
```

致谢
--

本项目主要基于以下开源项目二次开发，在此对相关项目和研究开发人员表示感谢。

-   Llama-2 _by Meta_
-   llama.cpp _by @ggerganov_
-   FlashAttention-2 by _Dao-AILab_

同时感谢Chinese-LLaMA-Alpaca（一期项目）的contributor以及关联项目和人员。

免责声明
----

本项目基于由Meta发布的Llama-2模型进行开发，使用过程中请严格遵守Llama-2的开源许可协议。如果涉及使用第三方代码，请务必遵从相关的开源许可协议。模型生成的内容可能会因为计算方法、随机因素以及量化精度损失等影响其准确性，因此，本项目不对模型输出的准确性提供任何保证，也不会对任何因使用相关资源和输出结果产生的损失承担责任。如果将本项目的相关模型用于商业用途，开发者应遵守当地的法律法规，确保模型输出内容的合规性，本项目不对任何由此衍生的产品或服务承担责任。

**局限性声明**

虽然本项目中的模型具备一定的中文理解和生成能力，但也存在局限性，包括但不限于：

-   可能会产生不可预测的有害内容以及不符合人类偏好和价值观的内容
-   由于算力和数据问题，相关模型的训练并不充分，中文理解能力有待进一步提升
-   暂时没有在线可互动的demo（注：用户仍然可以自行在本地部署和体验）

问题反馈
----

如有疑问，请在GitHub Issue中提交。礼貌地提出问题，构建和谐的讨论社区。

-   在提交问题之前，请先查看FAQ能否解决问题，同时建议查阅以往的issue是否能解决你的问题。
-   提交问题请使用本项目设置的Issue模板，以帮助快速定位具体问题。
-   重复以及与本项目无关的issue会被stable-bot处理，敬请谅解。
