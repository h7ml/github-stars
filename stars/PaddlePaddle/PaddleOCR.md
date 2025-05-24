---
project: PaddleOCR
stars: 49505
description: Awesome multilingual OCR toolkits based on PaddlePaddle (practical ultra lightweight OCR system, support 80+ languages recognition, provide data annotation and synthesis tools, support training and deployment among server, mobile, embedded and IoT devices)
url: https://github.com/PaddlePaddle/PaddleOCR
---

中文 | English

🚀 简介
-----

PaddleOCR自发布以来凭借学术前沿算法和产业落地实践，受到了产学研各方的喜爱，并被广泛应用于众多知名开源项目，例如：Umi-OCR、OmniParser、MinerU、RAGFlow等，已成为广大开发者心中的开源OCR领域的首选工具。2025年5月20日，飞桨团队发布**PaddleOCR 3.0**，全面适配**飞桨框架3.0正式版**，进一步**提升文字识别精度**，支持**多文字类型识别**和**手写体识别**，满足大模型应用对**复杂文档高精度解析**的旺盛需求，结合**文心大模型4.5 Turbo**显著提升关键信息抽取精度，并新增**对昆仑芯、昇腾等国产硬件**的支持。

PaddleOCR 3.0**新增**三大特色能力：

-   全场景文字识别模型PP-OCRv5：单模型支持五种文字类型和复杂手写体识别；整体识别精度相比上一代**提升13个百分点**。在线体验
-   通用文档解析方案PP-StructureV3：支持多场景、多版式 PDF 高精度解析，在公开评测集中**领先众多开源和闭源方案**。在线体验
-   智能文档理解方案PP-ChatOCRv4：原生支持文心大模型4.5 Turbo，精度相比上一代**提升15个百分点**。在线体验

PaddleOCR 3.0除了提供优秀的模型库外，还提供好学易用的工具，覆盖模型训练、推理和服务化部署，方便开发者快速落地AI应用。

📣 最新动态
-------

🔥🔥2025.05.20: **PaddleOCR 3.0** 正式发布，包含：

-   **PP-OCRv5**: 全场景高精度文字识别
    
    1.  🌐 单模型支持**五种**文字类型(**简体中文**、**繁体中文**、**中文拼音**、**英文**和**日文**)。
    2.  ✍️ 支持复杂**手写体**识别：复杂连笔、非规范字迹识别性能显著提升。
    3.  🎯 整体识别精度提升 - 多种应用场景达到 SOTA 精度, 相比上一版本PP-OCRv4，识别精度**提升13个百分点**！
-   **PP-StructureV3**: 通用文档解析方案
    
    1.  🧮 支持多场景 PDF 高精度解析，在 OmniDocBench 基准测试中**领先众多开源和闭源方案**。
    2.  🧠 多项专精能力: **印章识别**、**图表转表格**、**嵌套公式/图片的表格识别**、**竖排文本解析**及**复杂表格结构分析**等。
-   **PP-ChatOCRv4**: 智能文档理解方案
    
    1.  🔥 文档图像（PDF/PNG/JPG）关键信息提取精度相比上一代**提升15个百分点**！
    2.  💻 原生支持**文心大模型4.5 Turbo**，还兼容 PaddleNLP、Ollama、vLLM 等工具部署的大模型。
    3.  🤝 集成 PP-DocBee2，支持印刷文字、手写体文字、印章信息、表格、图表等常见的复杂文档信息抽取和理解的能力。

⚡ 快速开始
------

### 1\. 在线体验

### 2\. 本地安装

请参考安装指南完成**PaddlePaddle 3.0**的安装，然后安装paddleocr。

# 安装 paddleocr
pip install paddleocr==3.0.0

### 3\. 命令行方式推理

# 运行 PP-OCRv5 推理
paddleocr ocr -i https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo\_image/general\_ocr\_002.png --use\_doc\_orientation\_classify False --use\_doc\_unwarping False --use\_textline\_orientation False 

# 运行 PP-StructureV3 推理
paddleocr pp\_structurev3 -i https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo\_image/pp\_structure\_v3\_demo.png --use\_doc\_orientation\_classify False --use\_doc\_unwarping False

# 运行 PP-ChatOCRv4 推理前，需要先获得千帆API Key
paddleocr pp\_chatocrv4\_doc -i https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo\_image/vehicle\_certificate-1.png -k 驾驶室准乘人数 --qianfan\_api\_key your\_api\_key --use\_doc\_orientation\_classify False --use\_doc\_unwarping False 

# 查看 "paddleocr ocr" 详细参数
paddleocr ocr --help

### 4\. API方式推理

**4.1 PP-OCRv5 示例**

from paddleocr import PaddleOCR
\# 初始化 PaddleOCR 实例
ocr \= PaddleOCR(
    use\_doc\_orientation\_classify\=False,
    use\_doc\_unwarping\=False,
    use\_textline\_orientation\=False)
\# 对示例图像执行 OCR 推理 
result \= ocr.predict(
    input\="https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo\_image/general\_ocr\_002.png")
\# 可视化结果并保存 json 结果
for res in result:
    res.print()
    res.save\_to\_img("output")
    res.save\_to\_json("output")

**4.2 PP-StructureV3 示例**

from pathlib import Path
from paddleocr import PPStructureV3

pipeline \= PPStructureV3(
    use\_doc\_orientation\_classify\=False,
    use\_doc\_unwarping\=False
)

\# For Image
output \= pipeline.predict(
    input\="https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo\_image/pp\_structure\_v3\_demo.png",
    )

\# 可视化结果并保存 json 结果
for res in output:
    res.print() 
    res.save\_to\_json(save\_path\="output") 
    res.save\_to\_markdown(save\_path\="output") **4.3 PP-ChatOCRv4 示例**

from paddleocr import PPChatOCRv4Doc

chat\_bot\_config \= {
    "module\_name": "chat\_bot",
    "model\_name": "ernie-3.5-8k",
    "base\_url": "https://qianfan.baidubce.com/v2",
    "api\_type": "openai",
    "api\_key": "api\_key",  \# your api\_key
}

retriever\_config \= {
    "module\_name": "retriever",
    "model\_name": "embedding-v1",
    "base\_url": "https://qianfan.baidubce.com/v2",
    "api\_type": "qianfan",
    "api\_key": "api\_key",  \# your api\_key
}

mllm\_chat\_bot\_config \= {
    "module\_name": "chat\_bot",
    "model\_name": "PP-DocBee",
    "base\_url": "http://127.0.0.1:8080/",  \# your local mllm service url
    "api\_type": "openai",
    "api\_key": "api\_key",  \# your api\_key
}

pipeline \= PPChatOCRv4Doc(
    use\_doc\_orientation\_classify\=False,
    use\_doc\_unwarping\=False
)

visual\_predict\_res \= pipeline.visual\_predict(
    input\="https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo\_image/vehicle\_certificate-1.png",
    use\_common\_ocr\=True,
    use\_seal\_recognition\=True,
    use\_table\_recognition\=True,
)

visual\_info\_list \= \[\]
for res in visual\_predict\_res:
    visual\_info\_list.append(res\["visual\_info"\])
    layout\_parsing\_result \= res\["layout\_parsing\_result"\]

vector\_info \= pipeline.build\_vector(
    visual\_info\_list, flag\_save\_bytes\_vector\=True, retriever\_config\=retriever\_config
)
mllm\_predict\_res \= pipeline.mllm\_pred(
    input\="vehicle\_certificate-1.png",
    key\_list\=\["驾驶室准乘人数"\],
    mllm\_chat\_bot\_config\=mllm\_chat\_bot\_config,
)
mllm\_predict\_info \= mllm\_predict\_res\["mllm\_res"\]
chat\_result \= pipeline.chat(
    key\_list\=\["驾驶室准乘人数"\],
    visual\_info\=visual\_info\_list,
    vector\_info\=vector\_info,
    mllm\_predict\_info\=mllm\_predict\_info,
    chat\_bot\_config\=chat\_bot\_config,
    retriever\_config\=retriever\_config,
)
print(chat\_result)

### 5\. **国产化硬件使用**

-   昆仑芯安装指南
-   昇腾安装指南

⛰️ 进阶指南
-------

-   PP-OCRv5 使用教程
-   PP-StructureV3 使用教程
-   PP-ChatOCRv4 使用教程

🔄 效果展示
-------

👩‍👩‍👧‍👦 开发者社区
-----------------

扫码关注飞桨公众号

扫码加入技术交流群

🏆 使用 PaddleOCR 的优秀项目
---------------------

PaddleOCR 的发展离不开社区贡献！💗衷心感谢所有开发者、合作伙伴与贡献者！

项目名称

简介

RAGFlow

基于RAG的AI工作流引擎

MinerU

多类型文档转换Markdown工具

Umi-OCR

开源批量离线OCR软件

OmniParser

基于纯视觉的GUI智能体屏幕解析工具

QAnything

基于任意内容的问答系统

PDF-Extract-Kit

高效复杂PDF文档提取工具包

Dango-Translator

屏幕实时翻译工具

更多项目

👩‍👩‍👧‍👦 贡献者
---------------

🌟 Star
-------

📄 许可协议
-------

本项目的发布受Apache 2.0 license许可认证。

🎓 学术引用
-------

```
@misc{paddleocr2020,
title={PaddleOCR, Awesome multilingual OCR toolkits based on PaddlePaddle.},
author={PaddlePaddle Authors},
howpublished = {\url{https://github.com/PaddlePaddle/PaddleOCR}},
year={2020}
}
```
