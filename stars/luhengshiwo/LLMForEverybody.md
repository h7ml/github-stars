---
project: LLMForEverybody
stars: 4365
description: 每个人都能看懂的大模型知识分享，LLMs春/秋招大模型面试前必看，让你和面试官侃侃而谈
url: https://github.com/luhengshiwo/LLMForEverybody
---

目录
--

-   🐳序-AGI之路
-   🐱第一章-大模型之Pre-Training
    -   🐼架构
    -   🐹Optimizer
    -   🐰激活函数
    -   🐭Attention
    -   🐯位置编码
    -   🐨Tokenizer
    -   🐻并行策略
    -   🐷大模型训练框架
-   🐶第二章-大模型之部署与推理
-   🐯第三章-大模型微调
-   🐻第四章-大模型量化
-   🐼第五章-显卡与大模型并行
-   🐨第六章-Prompt-Engineering
-   🦁第七章-Agent
    -   🐷RAG
-   🐘第八章-大模型企业落地
-   🐰第九章-大模型评估指标
-   🐷第十章-热点
-   🦁第十一章-数学

序-AGI之路
-------

**⬆ 一键返回目录**

大家都在谈的Scaling\_Law是什么

智能涌现和AGI的起源

什么是perplexity

Pre-Training预训练Llama-3.1 405B超大杯，需要多少算力资源？

第一章-大模型之Pre-Training
--------------------

**⬆ 一键返回目录**

### 架构

10分钟搞清楚为什么Transformer中使用LayerNorm而不是BatchNorm

混合专家模型MoE详解节选

最简单的方式理解Mamba（中文翻译）

10分钟了解什么是多模态大模型

### Optimizer

全网最全的神经网络优化器optimizer总结

神经网络的优化器（一）综述

神经网络的优化器（二）SGD

神经网络的优化器（三）Momentum

神经网络的优化器（四）ASGD

神经网络的优化器（五）Rprop

神经网络的优化器（六）AdaGrad

神经网络的优化器（七）AdaDeleta

神经网络的优化器（八）RMSprop

神经网络的优化器（九）Adam

神经网络的优化器（十）Nadam

神经网络的优化器（十一）AdamW

神经网络的优化器（十二）RAdam

### 激活函数

为什么大型语言模型都在使用SwiGLU作为激活函数？

神经网络的激活函数（一）概述

神经网络的激活函数（二）Sigmiod、Softmax和Tanh

神经网络的激活函数（三）ReLU和它的变种

神经网络的激活函数（四）ELU和它的变种SELU

神经网络的激活函数（五）门控系列-GLU、Swish和SwiGLU

神经网络的激活函数（六）GELU和Mish

### Attention机制

看懂FlashAttention需要的数学储备是？高考数学最后一道大题

FlashAttentionv2相比于v1有哪些更新？

为什么会发展出Multi-Query-Attention和Group-Query-Attention

一文了解Deepseek系列中的MLA技术

### 位置编码

什么是大模型的位置编码Position-Encoding

复变函数在大模型位置编码中的应用

最美的数学公式-欧拉公式

从欧拉公式的美到旋转位置编码RoPE

### Tokenizer

全网最全的大模型分词器（Tokenizer）总结

搞懂大模型的分词器（一）

搞懂大模型的分词器（二）

搞懂大模型的分词器（三）

搞懂大模型的分词器（四）

搞懂大模型的分词器（五）

搞懂大模型的分词器（六）

### 并行策略

大模型并行策略\[中文翻译\]

大模型分布式训练并行技术（一）概述

大模型分布式训练并行技术（二）数据并行

大模型分布式训练并行技术（三）流水线并行

大模型分布式训练并行技术（四）张量并行

大模型分布式训练并行技术（五）混合并行

### 大模型训练框架

大模型训练框架（一）综述

大模型训练框架（二）FSDP

大模型训练框架（三）DeepSpeed

大模型训练框架（四）Megatron-LM

大模型训练框架（五）Accelerate

第二章-大模型之部署与推理
-------------

**⬆ 一键返回目录**

10分钟私有化部署大模型到本地

模型部署不求人！从TTFT到Throughput的性能估算终极公式

大模型output-token为什么比input-token贵

如何评判大模型的输出速度？首Token延迟和其余Token延迟有什么不同？

大模型的latency（延迟）和throughput（吞吐量）有什么区别

vLLM使用PagedAttention轻松、快速且廉价地提供LLM服务（中文版翻译）

DevOps，AIOps，MLOps，LLMOps，这些Ops都是什么？

大模型推理框架（一）综述

大模型推理框架（二）vLLM

大模型推理框架（三）Text generation inference (TGI)

大模型推理框架（四）TensorRT-LLM

大模型推理框架（五）Ollama

第三章-大模型微调
---------

**⬆ 一键返回目录**

10分钟教你套壳（不是）Llama-3，小白也能上手

大模型的参数高效微调（PEFT），LoRA微调以及其它

大模型微调之Soft prompts（一）概述

大模型微调之Soft prompts（二）Prompt Tuning

大模型微调之Soft prompts（三）Prefix-Tuning

大模型微调之Soft prompts（四）P-Tuning

大模型微调之Soft prompts（五）Multitask prompt tuning

大模型微调之Adapters（一）概述

大模型微调之Adapters（二）LoRA

大模型微调之Adapters（三）QLoRA

大模型微调之Adapters（四）AdaLoRA

大模型微调框架（一）综述

大模型微调框架（二）Huggingface-PEFT

大模型微调框架（三）Llama-Factory

第四章-大模型量化
---------

**⬆ 一键返回目录**

10分钟理解大模型的量化

大模型量化认知的三重境界

第五章-显卡与大模型并行
------------

**⬆ 一键返回目录**

AGI时代人人都可以看懂的显卡知识

Transformer架构的GPU并行和之前的NLP算法有什么不同？

大模型部署三要素：显存、计算与通信深度解析

第六章-Prompt-Engineering
----------------------

**⬆ 一键返回目录**

过去式就能越狱大模型？一文了解大模型安全攻防战

万字长文Prompt-Engineering-解锁大模型的力量

COT思维链，TOT思维树，GOT思维图，这些都是什么

第七章-Agent
---------

**⬆ 一键返回目录**

如何设计智能体架构：参考OpenAI还是Anthropic?

MCP：基础概念、快速应用和背后原理

LLM应用落地指南之应用的分类(一)

LLM应用落地之架构设计（二）

LLM应用落地之Text-2-SQL（三）

开发大模型or使用大模型

Agent设计范式与常见框架

langchain向左coze向右

### RAG

向量数据库拥抱大模型

搭配Knowledge-Graph的RAG架构

GraphRAG：解锁大模型对叙述性私人数据的检索能力（中文翻译）

干货：落地企业级RAG的实践指南

10分钟了解如何进行多模态RAG

第八章-大模型企业落地
-----------

**⬆ 一键返回目录**

CRUD-ETL工程师的末日从NL2SQL到ChatBI

大模型落地难点之幻觉

大模型落地难点之输出的不确定性

大模型落地难点之结构化输出

大模型应用涌现出的新工作机会-红队测试Red-teaming

大模型复读机问题

第九章-大模型评估指标
-----------

大模型有哪些评估指标？

大模型性能评测之大海捞针(Needle In A Haystack)

评估指标/大模型性能评测之数星星

第十章-热点
------

**⬆ 一键返回目录**

Llama 3.1 405B 为什么这么大？

9.11大于9.9？大模型怎么又翻车了？

韩国“N 号房”事件因Deep Fake再现，探究背后的技术和应对方法

我是怎么通过2022下半年软考高级：系统架构设计师考试的

用Exploit and Explore解决不知道吃什么的选择困难症

第十一章-数学
-------

**⬆ 一键返回目录**

### 线性代数

0基础学习AI大模型必备数学知识之线性代数（一）

0基础学习AI大模型必备数学知识之线性代数（二）

0基础学习AI大模型必备数学知识之线性代数（三）

### 微积分

0基础学习AI大模型必备数学知识之微积分（一）

0基础学习AI大模型必备数学知识之微积分（二）

### 概率统计

0基础学习AI大模型必备数学知识之概率统计（一）贝叶斯定理和概率分布

0基础学习AI大模型必备数学知识之概率统计（二）概率分布的描述方法

0基础学习AI大模型必备数学知识之概率统计（三）中心极限定理

第十二章-企业与个人思考
------------

**⬆ 一键返回目录**

### 企业

GenAI浪潮下的终极战场：如何从模仿者蜕变为“平台掌控者”？

### 个人

Star History
------------
