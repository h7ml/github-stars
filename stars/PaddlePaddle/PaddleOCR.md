---
project: PaddleOCR
stars: 51013
description: Awesome multilingual OCR and Document Parsing toolkits based on PaddlePaddle (practical ultra lightweight OCR system, support 80+ languages recognition, provide data annotation and synthesis tools, support training and deployment among server, mobile, embedded and IoT devices)
url: https://github.com/PaddlePaddle/PaddleOCR
---

English | 简体中文 | 繁體中文 | 日本語 | 한국어 | Français | Русский | Español | العربية

🚀 Introduction
---------------

Since its initial release, PaddleOCR has gained widespread acclaim across academia, industry, and research communities, thanks to its cutting-edge algorithms and proven performance in real-world applications. It's already powering popular open-source projects like Umi-OCR, OmniParser, MinerU, and RAGFlow, making it the go-to OCR toolkit for developers worldwide.

On May 20, 2025, the PaddlePaddle team unveiled PaddleOCR 3.0, fully compatible with the official release of the **PaddlePaddle 3.0** framework. This update further **boosts text-recognition accuracy**, adds support for **multiple text-type recognition** and **handwriting recognition**, and meets the growing demand from large-model applications for **high-precision parsing of complex documents**. When combined with the **ERNIE 4.5 Turbo**, it significantly enhances key-information extraction accuracy. PaddleOCR 3.0 also introduces support for Chinese Heterogeneous AI Accelerators such as **KUNLUNXIN** and **Ascend**. For the complete usage documentation, please refer to the PaddleOCR 3.0 Documentation.

Three Major New Features in PaddleOCR 3.0:

-   Universal-Scene Text Recognition Model PP-OCRv5: A single model that handles five different text types plus complex handwriting. Overall recognition accuracy has increased by 13 percentage points over the previous generation. Online Demo
    
-   General Document-Parsing Solution PP-StructureV3: Delivers high-precision parsing of multi-layout, multi-scene PDFs, outperforming many open- and closed-source solutions on public benchmarks. Online Demo
    
-   Intelligent Document-Understanding Solution PP-ChatOCRv4: Natively powered by the ERNIE 4.5 Turbo, achieving 15 percentage points higher accuracy than its predecessor. Online Demo
    

In addition to providing an outstanding model library, PaddleOCR 3.0 also offers user-friendly tools covering model training, inference, and service deployment, so developers can rapidly bring AI applications to production.

📣 Recent updates
-----------------

#### **2025.06.26: Release of PaddleOCR 3.0.3**, includes:

-   Bug Fix: Resolved the issue where the `enable_mkldnn` parameter was not effective, restoring the default behavior of using MKL-DNN for CPU inference.

#### 🔥🔥 **2025.06.19: Release of PaddleOCR 3.0.2**, includes:

-   **New Features:**
    
    -   The default download source has been changed from `BOS` to `HuggingFace`. Users can also change the environment variable `PADDLE_PDX_MODEL_SOURCE` to `BOS` to set the model download source back to Baidu Object Storage (BOS).
    -   Added service invocation examples for six languages—C++, Java, Go, C#, Node.js, and PHP—for pipelines like PP-OCRv5, PP-StructureV3, and PP-ChatOCRv4.
    -   Improved the layout partition sorting algorithm in the PP-StructureV3 pipeline, enhancing the sorting logic for complex vertical layouts to deliver better results.
    -   Enhanced model selection logic: when a language is specified but a model version is not, the system will automatically select the latest model version supporting that language.
    -   Set a default upper limit for MKL-DNN cache size to prevent unlimited growth, while also allowing users to configure cache capacity.
    -   Updated default configurations for high-performance inference to support Paddle MKL-DNN acceleration and optimized the logic for automatic configuration selection for smarter choices.
    -   Adjusted the logic for obtaining the default device to consider the actual support for computing devices by the installed Paddle framework, making program behavior more intuitive.
    -   Added Android example for PP-OCRv5. Details.
-   **Bug Fixes:**
    
    -   Fixed an issue with some CLI parameters in PP-StructureV3 not taking effect.
    -   Resolved an issue where `export_paddlex_config_to_yaml` would not function correctly in certain cases.
    -   Corrected the discrepancy between the actual behavior of `save_path` and its documentation description.
    -   Fixed potential multithreading errors when using MKL-DNN in basic service deployment.
    -   Corrected channel order errors in image preprocessing for the Latex-OCR model.
    -   Fixed channel order errors in saving visualized images within the text recognition module.
    -   Resolved channel order errors in visualized table results within PP-StructureV3 pipeline.
    -   Fixed an overflow issue in the calculation of `overlap_ratio` under extremely special circumstances in the PP-StructureV3 pipeline.
-   **Documentation Improvements:**
    
    -   Updated the description of the `enable_mkldnn` parameter in the documentation to accurately reflect the program's actual behavior.
    -   Fixed errors in the documentation regarding the `lang` and `ocr_version` parameters.
    -   Added instructions for exporting production line configuration files via CLI.
    -   Fixed missing columns in the performance data table for PP-OCRv5.
    -   Refined benchmark metrics for PP-StructureV3 across different configurations.
-   **Others:**
    
    -   Relaxed version restrictions on dependencies like numpy and pandas, restoring support for Python 3.12.

**History Log**

#### **🔥🔥 2025.06.05: Release of PaddleOCR 3.0.1, includes:**

-   **Optimisation of certain models and model configurations:**
    
    -   Updated the default model configuration for PP-OCRv5, changing both detection and recognition from mobile to server models. To improve default performance in most scenarios, the parameter `limit_side_len` in the configuration has been changed from 736 to 64.
    -   Added a new text line orientation classification model `PP-LCNet_x1_0_textline_ori` with an accuracy of 99.42%. The default text line orientation classifier for OCR, PP-StructureV3, and PP-ChatOCRv4 pipelines has been updated to this model.
    -   Optimised the text line orientation classification model `PP-LCNet_x0_25_textline_ori`, improving accuracy by 3.3 percentage points to a current accuracy of 98.85%.
-   **Optimizations and fixes for some issues in version 3.0.0, details**
    

🔥🔥2025.05.20: Official Release of **PaddleOCR v3.0**, including:

-   **PP-OCRv5**: High-Accuracy Text Recognition Model for All Scenarios - Instant Text from Images/PDFs.
    
    1.  🌐 Single-model support for **five** text types - Seamlessly process **Simplified Chinese, Traditional Chinese, Simplified Chinese Pinyin, English** and **Japanese** within a single model.
    2.  ✍️ Improved **handwriting recognition**: Significantly better at complex cursive scripts and non-standard handwriting.
    3.  🎯 **13-point accuracy gain** over PP-OCRv4, achieving state-of-the-art performance across a variety of real-world scenarios.
-   **PP-StructureV3**: General-Purpose Document Parsing – Unleash SOTA Images/PDFs Parsing for Real-World Scenarios!
    
    1.  🧮 **High-Accuracy multi-scene PDF parsing**, leading both open- and closed-source solutions on the OmniDocBench benchmark.
    2.  🧠 Specialized capabilities include **seal recognition**, **chart-to-table conversion**, **table recognition with nested formulas/images**, **vertical text document parsing**, and **complex table structure analysis**.
-   **PP-ChatOCRv4**: Intelligent Document Understanding – Extract Key Information, not just text from Images/PDFs.
    
    1.  🔥 **15-point accuracy gain** in key-information extraction on PDF/PNG/JPG files over the previous generation.
    2.  💻 Native support for **ERNIE 4.5 Turbo**, with compatibility for large-model deployments via PaddleNLP, Ollama, vLLM, and more.
    3.  🤝 Integrated PP-DocBee2, enabling extraction and understanding of printed text, handwriting, seals, tables, charts, and other common elements in complex documents.

History Log

⚡ Quick Start
-------------

### 1\. Run online demo

### 2\. Installation

Install PaddlePaddle refer to Installation Guide, after then, install the PaddleOCR toolkit.

# Install paddleocr
pip install paddleocr

### 3\. Run inference by CLI

# Run PP-OCRv5 inference
paddleocr ocr -i https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo\_image/general\_ocr\_002.png --use\_doc\_orientation\_classify False --use\_doc\_unwarping False --use\_textline\_orientation False  

# Run PP-StructureV3 inference
paddleocr pp\_structurev3 -i https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo\_image/pp\_structure\_v3\_demo.png --use\_doc\_orientation\_classify False --use\_doc\_unwarping False

# Get the Qianfan API Key at first, and then run PP-ChatOCRv4 inference
paddleocr pp\_chatocrv4\_doc -i https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo\_image/vehicle\_certificate-1.png -k 驾驶室准乘人数 --qianfan\_api\_key your\_api\_key --use\_doc\_orientation\_classify False --use\_doc\_unwarping False 

# Get more information about "paddleocr ocr"
paddleocr ocr --help

### 4\. Run inference by API

**4.1 PP-OCRv5 Example**

\# Initialize PaddleOCR instance
from paddleocr import PaddleOCR
ocr \= PaddleOCR(
    use\_doc\_orientation\_classify\=False,
    use\_doc\_unwarping\=False,
    use\_textline\_orientation\=False)

\# Run OCR inference on a sample image 
result \= ocr.predict(
    input\="https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo\_image/general\_ocr\_002.png")

\# Visualize the results and save the JSON results
for res in result:
    res.print()
    res.save\_to\_img("output")
    res.save\_to\_json("output")

**4.2 PP-StructureV3 Example**

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

\# Visualize the results and save the JSON results
for res in output:
    res.print() 
    res.save\_to\_json(save\_path\="output") 
    res.save\_to\_markdown(save\_path\="output")           **4.3 PP-ChatOCRv4 Example**

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

mllm\_predict\_info \= None
use\_mllm \= False
\# If a multimodal large model is used, the local mllm service needs to be started. You can refer to the documentation: https://github.com/PaddlePaddle/PaddleX/blob/release/3.0/docs/pipeline\_usage/tutorials/vlm\_pipelines/doc\_understanding.en.md performs deployment and updates the mllm\_chat\_bot\_config configuration.
if use\_mllm:
    mllm\_chat\_bot\_config \= {
        "module\_name": "chat\_bot",
        "model\_name": "PP-DocBee",
        "base\_url": "http://127.0.0.1:8080/",  \# your local mllm service url
        "api\_type": "openai",
        "api\_key": "api\_key",  \# your api\_key
    }

    mllm\_predict\_res \= pipeline.mllm\_pred(
        input\="https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo\_image/vehicle\_certificate-1.png",
        key\_list\=\["驾驶室准乘人数"\],
        mllm\_chat\_bot\_config\=mllm\_chat\_bot\_config,
    )
    mllm\_predict\_info \= mllm\_predict\_res\["mllm\_res"\]

visual\_info\_list \= \[\]
for res in visual\_predict\_res:
    visual\_info\_list.append(res\["visual\_info"\])
    layout\_parsing\_result \= res\["layout\_parsing\_result"\]

vector\_info \= pipeline.build\_vector(
    visual\_info\_list, flag\_save\_bytes\_vector\=True, retriever\_config\=retriever\_config
)
chat\_result \= pipeline.chat(
    key\_list\=\["驾驶室准乘人数"\],
    visual\_info\=visual\_info\_list,
    vector\_info\=vector\_info,
    mllm\_predict\_info\=mllm\_predict\_info,
    chat\_bot\_config\=chat\_bot\_config,
    retriever\_config\=retriever\_config,
)
print(chat\_result)

### 5\. Chinese Heterogeneous AI Accelerators

-   Huawei Ascend
-   KUNLUNXIN

⛰️ Advanced Tutorials
---------------------

-   PP-OCRv5 Tutorial
-   PP-StructureV3 Tutorial
-   PP-ChatOCRv4 Tutorial

🔄 Quick Overview of Execution Results
--------------------------------------

👩‍👩‍👧‍👦 Community
---------------------

PaddlePaddle WeChat official account

Join the tech discussion group

😃 Awesome Projects Leveraging PaddleOCR
----------------------------------------

PaddleOCR wouldn't be where it is today without its incredible community! 💗 A massive thank you to all our longtime partners, new collaborators, and everyone who's poured their passion into PaddleOCR — whether we've named you or not. Your support fuels our fire!

Project Name

Description

RAGFlow

RAG engine based on deep document understanding.

MinerU

Multi-type Document to Markdown Conversion Tool

Umi-OCR

Free, Open-source, Batch Offline OCR Software.

OmniParser

OmniParser: Screen Parsing tool for Pure Vision Based GUI Agent.

QAnything

Question and Answer based on Anything.

PDF-Extract-Kit

A powerful open-source toolkit designed to efficiently extract high-quality content from complex and diverse PDF documents.

Dango-Translator

Recognize text on the screen, translate it and show the translation results in real time.

Learn more projects

More projects based on PaddleOCR

👩‍👩‍👧‍👦 Contributors
------------------------

🌟 Star
-------

📄 License
----------

This project is released under the Apache 2.0 license.

🎓 Citation
-----------

```
@misc{paddleocr2020,
title={PaddleOCR, Awesome multilingual OCR toolkits based on PaddlePaddle.},
author={PaddlePaddle Authors},
howpublished = {\url{https://github.com/PaddlePaddle/PaddleOCR}},
year={2020}
}
```
