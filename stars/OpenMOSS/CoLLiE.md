---
project: CoLLiE
stars: 417
description: Collaborative Training of Large Language Models in an Efficient Way
url: https://github.com/OpenMOSS/CoLLiE
---

CoLLiE
======

CoLLiE (Collaborative Tuning of Large Language Models in an Efficient Way)，一个帮助您从零开始训练大模型的完整工具箱。

#### 

\[ 简体中文 \] | \[ English \]

新闻
--

-   \[2023/12\] 🎉 CoLLiE被EMNLP System Demonstrations接收：CoLLiE: Collaborative Training of Large Language Models in an Efficient Way
-   \[2023/08\] 评测结果新增显存占用与模型大小的关系和吞吐量。
-   \[2023/07\] 发布Python包`collie-lm`。您可以在PyPI中查看更多细节！

目录
--

-   为什么选择CoLLiE
-   特性
-   CoLLiE支持的模型
-   评测
-   安装
-   Docker安装
-   使用
    -   快速开始
    -   有趣的插件
    -   更多成功样例和完整教程
-   社区
-   贡献者
-   引用我们

为什么选择CoLLiE
-----------

CoLLiE是一个可以帮助您从零开始训练大模型的完整工具箱，它提供了数据预处理、模型微调、模型保存以及训练过程各项指标监测等功能。CoLLiE集成了现有的并行策略、高效参数微调方法和高效优化器，以加快训练的速度，提高训练的质量，降低训练的开销。CoLLiE支持主流的多种模型（如MOSS, InternLM, LLaMA, ChatGLM等），您可以轻松在不同的模型之间切换。此外，CoLLiE提供了丰富的文档，使初学者可以快速入门。同时，CoLLiE还提供了高度可定制化的功能和灵活的配置选项，使有经验的用户能够根据自己的需求进行个性化定制。无论您是初学者还是有经验的专业人士，CoLLiE都可以为您提供满足需求的解决方案。

特点
--

CoLLiE 基于 _DeepSpeed_ 和 _PyTorch_，为大型语言模型提供协作式和高效的调优方法。 它主要包括以下四个特点：

-   并行策略
    -   数据并行 (DP)
    -   流水线并行 (PP)
    -   张量并行 (TP)
    -   零冗余优化器 (ZeRO)
-   高效微调
    -   LOMO
    -   LoRA
    -   Flash Attention
-   设计优雅
-   用户友好

完整特性

CoLLiE支持的模型
-----------

-   MOSS系列：MOSS-MOON
-   InternLM系列：InternLM2
-   LLaMA系列：LLaMA、LLaMA-2
-   ChatGLM系列：ChatGLM、ChatGLM2

评测
--

### 显存占用

使用张量并行测试了批量大小为 1，序列长度为 2048，梯度累计步数为 2 下显存占用情况，结果如下：

### 吞吐量

在 A100 和 RTX-3090 上测试了不同批量大小下使用 Adam 优化器的吞吐量，结果如下：

安装
--

在安装前，你需要确保：

-   PyTorch >= 1.13
-   CUDA >= 11.6
-   Linux OS

### PyPI安装

你可以简单地通过PyPI安装，命令如下：

pip install collie-lm

### 源码安装

git clone https://github.com/OpenLMLab/collie
python setup.py install

Docker安装
--------

使用
--

### 快速开始

下面将提供一个使用CoLLiE训练Moss的样例，同时使用LOMO优化器，并且开启ZeRO3来降低显存消耗。

那么，请按照下面的步骤开启你的大模型训练之旅吧~

#### 第一步：导入必要的包

from transformers import AutoTokenizer
from collie.config import CollieConfig
from collie.data import CollieDatasetForTraining
from collie.data import CollieDataLoader
from collie.optim.lomo import Lomo
from collie.controller.trainer import Trainer
from collie.controller.evaluator import EvaluatorForPerplexity, EvaluatorForGeneration
from collie.models.moss\_moon import Moss003MoonForCausalLM
from collie.utils.monitor import StepTimeMonitor, TGSMonitor, MemoryMonitor, LossMonitor, EvalMonitor
from collie.metrics import DecodeMetric, PPLMetric
from collie.module import GPTLMLoss
from collie.utils.data\_provider import GradioProvider

#### 第二步：设置路径

选择预训练模型为MOSS

```
pretrained_model = "fnlp/moss-moon-003-sft"
```

#### 第三步：设置CoLLiE配置

config \= CollieConfig.from\_pretrained(pretrained\_model, trust\_remote\_code\=True)
\# 张量并行
config.tp\_size \= 2
\# 数据并行
config.dp\_size \= 1
\# 流水线并行
config.pp\_size \= 1
\# 训练的epoch数量
config.train\_epochs \= 1
\# 每{100}个step进行一次eval
config.eval\_per\_n\_steps \= 100
\# 每{1}个epoch进行一次eval
config.eval\_per\_n\_epochs \= 1 
\# 每个GPU的batch\_size设置为{16}
config.train\_micro\_batch\_size \= 16
\# 每次eval的batch\_size为{1}
config.eval\_batch\_size \= 1
\# 设置DeepSpeed配置
config.ds\_config \= {
        \# 开启FP16
        "fp16": {
            "enabled": True
        },
        "zero\_allow\_untested\_optimizer": True,
        "zero\_force\_ds\_cpu\_optimizer": False,
        \# 开启ZeRO-3
        "zero\_optimization": {
            "stage": 3,
            "offload\_optimizer": {
                "device": "cpu",
                "pin\_memory": False
            }
        },
        "monitor\_config": {
            "enabled": True,
            "tag": "adan",
            "csv\_monitor": {
                "enabled": True,
                "output\_path": "./ds\_logs/"
            }
        }
}

#### 第四步：设置Tokenizer

tokenizer \= AutoTokenizer.from\_pretrained("fnlp/moss-moon-003-sft", trust\_remote\_code\=True)

#### 第五步：加载数据集

这里自定义一个数据集，数据格式可以提供两种形式，具体请参考文档。

train\_dataset \= \[
    {
        'input': 'Collie is a python package for ',
        'output': 'finetuning large language models.'
    } for \_ in range(10000)
\]
train\_dataset \= CollieDatasetForTraining(train\_dataset, tokenizer)
eval\_dataset \= train\_dataset\[:32\]

#### 第六步：加载预训练模型

model \= Moss003MoonForCausalLM.from\_pretrained(pretrained\_model, config\=config)

#### 第七步：设置优化器

optimizer \= Lomo(
    model,
    lr \= 0.001,
    clip\_grad\_norm \= 5.0
)

#### 第八步：添加监视器

monitors \= \[
    \# 每个step用时监测
    StepTimeMonitor(config),
    \# TGS（每秒生成token数量监测）
    TGSMonitor(config),
    \# 显存使用情况监测
    MemoryMonitor(config),
    \# Loss值监测
    LossMonitor(config),
    \# Eval结果监测
    EvalMonitor(config)
\]

#### 第九步：添加Evaluator

这里添加两个Evaluator，分别用于计算PPL(困惑度：Perplexity)和保存Decode结果。

evaluator\_ppl \= EvaluatorForPerplexity(
    model \= model,
    config \= config,
    dataset \= eval\_dataset,
    monitors \= \[
        EvalMonitor(config)
    \],
    metrics \= {
        'ppl': PPLMetric()
    }
)
evaluator\_decode \= EvaluatorForGeneration(
    model \= model,
    config \= config,
    tokenizer \= tokenizer,
    dataset \= eval\_dataset,
    monitors \= \[
        EvalMonitor(config)
    \],
    metrics \= {
        'decode': DecodeMetric()
    }

)

#### 第十步：实例化Trainer

trainer \= Trainer(
    model \= model,
    config \= config,
    loss\_fn \= GPTLMLoss(\-100),
    optimizer \= optimizer,
    train\_dataset \= train\_dataset,
    monitors \= monitors,
    evaluators \= \[evaluator\_ppl, evaluator\_decode\],
)
\# 开始训练/验证
trainer.train()

#### 最后一步：启动命令行，开始训练！👍

Command CUDA\_VISIBLE\_DEVICES=0,1,2,3 torchrun --rdzv\_backend=c10d --rdzv\_endpoint=localhost:29402 --nnodes=1 --nproc\_per\_node=4 finetune\_moss\_for\_training.py

如果你的命令行出现如下的进度条，那么恭喜你，你已经成功开始训练你的大模型！

完整代码请参考examples/finetune\_moss\_for\_training.py。

### 有趣的插件

CoLLiE提供了许多即插即用的插件，下面将介绍Monitor检测器和异步DataProvider，更多插件等待探索和开发...

#### Monitor监测器

在CollieConfig.ds\_config中添加monitor配置，并在Trainer中启用即可在训练过程中打开监测器。

    "monitor\_config": {
        \# 开启检测器
        "enabled": True,
        \# 保存的文件名前缀
        "tag": "adan",
        \# 保存文件格式:csv
        "csv\_monitor": {
            "enabled": True,
            \# 保存文件夹
            "output\_path": "./ds\_logs/"
        }
    }

启用检测器后，你将在`ds_logs`文件夹中获取相关的文件，如：

#### 异步DataProvider

你只需要在Trainer中添加：data\_provider，即可在训练过程中打开一个异步DataProvider，方便及时Human Eval！

trainer \= Trainer(
    model \= model,
    config \= config,
    loss\_fn \= GPTLMLoss(\-100),
    optimizer \= optimizer,
    train\_dataset \= train\_dataset,
    monitors \= monitors,
    evaluators \= \[evaluator\_ppl, evaluator\_decode\],
    \# 添加
    data\_provider \= GradioProvider(tokenizer)
)

### 更多成功样例和完整教程

CoLLiE提供了完整的 教程。 更多的示例也可在 示例 中查看。

社区
--

贡献者
---

引用我们
----
