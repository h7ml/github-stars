---
project: ColossalAI
stars: 41133
description: Making large AI models cheaper, faster and more accessible
url: https://github.com/hpcaitech/ColossalAI
---

Colossal-AI
===========

Colossal-AI: Making large AI models cheaper, faster, and more accessible

### Paper | Documentation | Examples | Forum | GPU Cloud Playground | Blog

| English | 中文 |

Get Started with Colossal-AI Without Setup
------------------------------------------

Access high-end, on-demand compute for your research instantly—no setup needed.

Sign up now and get $10 in credits!

Limited Academic Bonuses:

-   Top up $1,000 and receive 300 credits
-   Top up $500 and receive 100 credits

Latest News
-----------

-   \[2025/02\] DeepSeek 671B Fine-Tuning Guide Revealed—Unlock the Upgraded DeepSeek Suite with One Click, AI Players Ecstatic!
-   \[2024/12\] The development cost of video generation models has saved by 50%! Open-source solutions are now available with H200 GPU vouchers \[code\] \[vouchers\]
-   \[2024/10\] How to build a low-cost Sora-like app? Solutions for you
-   \[2024/09\] Singapore Startup HPC-AI Tech Secures 50 Million USD in Series A Funding to Build the Video Generation AI Model and GPU Platform
-   \[2024/09\] Reducing AI Large Model Training Costs by 30% Requires Just a Single Line of Code From FP8 Mixed Precision Training Upgrades
-   \[2024/06\] Open-Sora Continues Open Source: Generate Any 16-Second 720p HD Video with One Click, Model Weights Ready to Use
-   \[2024/05\] Large AI Models Inference Speed Doubled, Colossal-Inference Open Source Release
-   \[2024/04\] Open-Sora Unveils Major Upgrade: Embracing Open Source with Single-Shot 16-Second Video Generation and 720p Resolution
-   \[2024/04\] Most cost-effective solutions for inference, fine-tuning and pretraining, tailored to LLaMA3 series

Table of Contents
-----------------

-   Why Colossal-AI
-   Features
-   Colossal-AI for Real World Applications
    -   Open-Sora: Revealing Complete Model Parameters, Training Details, and Everything for Sora-like Video Generation Models
    -   Colossal-LLaMA-2: One Half-Day of Training Using a Few Hundred Dollars Yields Similar Results to Mainstream Large Models, Open-Source and Commercial-Free Domain-Specific Llm Solution
    -   ColossalChat: An Open-Source Solution for Cloning ChatGPT With a Complete RLHF Pipeline
    -   AIGC: Acceleration of Stable Diffusion
    -   Biomedicine: Acceleration of AlphaFold Protein Structure
-   Parallel Training Demo
    -   LLaMA 1/2/3
    -   MoE
    -   GPT-3
    -   GPT-2
    -   BERT
    -   PaLM
    -   OPT
    -   ViT
    -   Recommendation System Models
-   Single GPU Training Demo
    -   GPT-2
    -   PaLM
-   Inference
    -   Colossal-Inference: Large AI Models Inference Speed Doubled
    -   Grok-1: 314B model of PyTorch + HuggingFace Inference
    -   SwiftInfer:Breaks the Length Limit of LLM for Multi-Round Conversations with 46% Acceleration
-   Installation
    -   PyPI
    -   Install From Source
-   Use Docker
-   Community
-   Contributing
-   Cite Us

Why Colossal-AI
---------------

Prof. James Demmel (UC Berkeley): Colossal-AI makes training AI models efficient, easy, and scalable.

(back to top)

Features
--------

Colossal-AI provides a collection of parallel components for you. We aim to support you to write your distributed deep learning models just like how you write your model on your laptop. We provide user-friendly tools to kickstart distributed training and inference in a few lines.

-   Parallelism strategies
    
    -   Data Parallelism
    -   Pipeline Parallelism
    -   1D, 2D, 2.5D, 3D Tensor Parallelism
    -   Sequence Parallelism
    -   Zero Redundancy Optimizer (ZeRO)
    -   Auto-Parallelism
-   Heterogeneous Memory Management
    
    -   PatrickStar
-   Friendly Usage
    
    -   Parallelism based on the configuration file

(back to top)

Colossal-AI in the Real World
-----------------------------

### Open-Sora

Open-Sora：Revealing Complete Model Parameters, Training Details, and Everything for Sora-like Video Generation Models \[code\] \[blog\] \[Model weights\] \[Demo\] \[GPU Cloud Playground\] \[OpenSora Image\]

(back to top)

### Colossal-LLaMA-2

\[GPU Cloud Playground\] \[LLaMA3 Image\]

-   7B: One half-day of training using a few hundred dollars yields similar results to mainstream large models, open-source and commercial-free domain-specific LLM solution. \[code\] \[blog\] \[HuggingFace model weights\] \[Modelscope model weights\]
    
-   13B: Construct refined 13B private model with just $5000 USD. \[code\] \[blog\] \[HuggingFace model weights\] \[Modelscope model weights\]
    

Model

Backbone

Tokens Consumed

MMLU (5-shot)

CMMLU (5-shot)

AGIEval (5-shot)

GAOKAO (0-shot)

CEval (5-shot)

Baichuan-7B

\-

1.2T

42.32 (42.30)

44.53 (44.02)

38.72

36.74

42.80

Baichuan-13B-Base

\-

1.4T

50.51 (51.60)

55.73 (55.30)

47.20

51.41

53.60

Baichuan2-7B-Base

\-

2.6T

46.97 (54.16)

57.67 (57.07)

45.76

52.60

54.00

Baichuan2-13B-Base

\-

2.6T

54.84 (59.17)

62.62 (61.97)

52.08

58.25

58.10

ChatGLM-6B

\-

1.0T

39.67 (40.63)

41.17 (-)

40.10

36.53

38.90

ChatGLM2-6B

\-

1.4T

44.74 (45.46)

49.40 (-)

46.36

45.49

51.70

InternLM-7B

\-

1.6T

46.70 (51.00)

52.00 (-)

44.77

61.64

52.80

Qwen-7B

\-

2.2T

54.29 (56.70)

56.03 (58.80)

52.47

56.42

59.60

Llama-2-7B

\-

2.0T

44.47 (45.30)

32.97 (-)

32.60

25.46

\-

Linly-AI/Chinese-LLaMA-2-7B-hf

Llama-2-7B

1.0T

37.43

29.92

32.00

27.57

\-

wenge-research/yayi-7b-llama2

Llama-2-7B

\-

38.56

31.52

30.99

25.95

\-

ziqingyang/chinese-llama-2-7b

Llama-2-7B

\-

33.86

34.69

34.52

25.18

34.2

TigerResearch/tigerbot-7b-base

Llama-2-7B

0.3T

43.73

42.04

37.64

30.61

\-

LinkSoul/Chinese-Llama-2-7b

Llama-2-7B

\-

48.41

38.31

38.45

27.72

\-

FlagAlpha/Atom-7B

Llama-2-7B

0.1T

49.96

41.10

39.83

33.00

\-

IDEA-CCNL/Ziya-LLaMA-13B-v1.1

Llama-13B

0.11T

50.25

40.99

40.04

30.54

\-

**Colossal-LLaMA-2-7b-base**

Llama-2-7B

**0.0085T**

53.06

49.89

51.48

58.82

50.2

**Colossal-LLaMA-2-13b-base**

Llama-2-13B

**0.025T**

56.42

61.80

54.69

69.53

60.3

### ColossalChat

ColossalChat: An open-source solution for cloning ChatGPT with a complete RLHF pipeline. \[code\] \[blog\] \[demo\] \[tutorial\]

-   Up to 10 times faster for RLHF PPO Stage3 Training

-   Up to 7.73 times faster for single server training and 1.42 times faster for single-GPU inference

-   Up to 10.3x growth in model capacity on one GPU
-   A mini demo training process requires only 1.62GB of GPU memory (any consumer-grade GPU)

-   Increase the capacity of the fine-tuning model by up to 3.7 times on a single GPU
-   Keep at a sufficiently high running speed

(back to top)

### AIGC

Acceleration of AIGC (AI-Generated Content) models such as Stable Diffusion v1 and Stable Diffusion v2.

-   Training: Reduce Stable Diffusion memory consumption by up to 5.6x and hardware cost by up to 46x (from A100 to RTX3060).

-   DreamBooth Fine-tuning: Personalize your model using just 3-5 images of the desired subject.

-   Inference: Reduce inference GPU memory consumption by 2.5x.

(back to top)

### Biomedicine

Acceleration of AlphaFold Protein Structure

-   FastFold: Accelerating training and inference on GPU Clusters, faster data processing, inference sequence containing more than 10000 residues.

-   FastFold with Intel: 3x inference acceleration and 39% cost reduce.

-   xTrimoMultimer: accelerating structure prediction of protein monomers and multimer by 11x.

(back to top)

Parallel Training Demo
----------------------

### LLaMA3

-   70 billion parameter LLaMA3 model training accelerated by 18% \[code\] \[GPU Cloud Playground\] \[LLaMA3 Image\]

### LLaMA2

-   70 billion parameter LLaMA2 model training accelerated by 195% \[code\] \[blog\]

### LLaMA1

-   65-billion-parameter large model pretraining accelerated by 38% \[code\] \[blog\]

### MoE

-   Enhanced MoE parallelism, Open-source MoE model training can be 9 times more efficient \[code\] \[blog\]

### GPT-3

-   Save 50% GPU resources and 10.7% acceleration

### GPT-2

-   11x lower GPU memory consumption, and superlinear scaling efficiency with Tensor Parallelism

-   24x larger model size on the same hardware
-   over 3x acceleration

### BERT

-   2x faster training, or 50% longer sequence length

### PaLM

-   PaLM-colossalai: Scalable implementation of Google's Pathways Language Model (PaLM).

### OPT

-   Open Pretrained Transformer (OPT), a 175-Billion parameter AI language model released by Meta, which stimulates AI programmers to perform various downstream tasks and application deployments because of public pre-trained model weights.
-   45% speedup fine-tuning OPT at low cost in lines. \[Example\] \[Online Serving\]

Please visit our documentation and examples for more details.

### ViT

-   14x larger batch size, and 5x faster training for Tensor Parallelism = 64

### Recommendation System Models

-   Cached Embedding, utilize software cache to train larger embedding tables with a smaller GPU memory budget.

(back to top)

Single GPU Training Demo
------------------------

### GPT-2

-   20x larger model size on the same hardware

-   120x larger model size on the same hardware (RTX 3080)

### PaLM

-   34x larger model size on the same hardware

(back to top)

Inference
---------

### Colossal-Inference

-   Large AI models inference speed doubled, compared to the offline inference performance of vLLM in some cases. \[code\] \[blog\] \[GPU Cloud Playground\] \[LLaMA3 Image\]

### Grok-1

-   314 Billion Parameter Grok-1 Inference Accelerated by 3.8x, an easy-to-use Python + PyTorch + HuggingFace version for Inference.

\[code\] \[blog\] \[HuggingFace Grok-1 PyTorch model weights\] \[ModelScope Grok-1 PyTorch model weights\]

### SwiftInfer

-   SwiftInfer: Inference performance improved by 46%, open source solution breaks the length limit of LLM for multi-round conversations

(back to top)

Installation
------------

Requirements:

-   PyTorch >= 2.2
-   Python >= 3.7
-   CUDA >= 11.0
-   NVIDIA GPU Compute Capability >= 7.0 (V100/RTX20 and higher)
-   Linux OS

If you encounter any problem with installation, you may want to raise an issue in this repository.

### Install from PyPI

You can easily install Colossal-AI with the following command. **By default, we do not build PyTorch extensions during installation.**

pip install colossalai

**Note: only Linux is supported for now.**

However, if you want to build the PyTorch extensions during installation, you can set `BUILD_EXT=1`.

BUILD\_EXT=1 pip install colossalai

**Otherwise, CUDA kernels will be built during runtime when you actually need them.**

We also keep releasing the nightly version to PyPI every week. This allows you to access the unreleased features and bug fixes in the main branch. Installation can be made via

pip install colossalai-nightly

### Download From Source

> The version of Colossal-AI will be in line with the main branch of the repository. Feel free to raise an issue if you encounter any problems. :)

git clone https://github.com/hpcaitech/ColossalAI.git
cd ColossalAI

# install colossalai
pip install .

By default, we do not compile CUDA/C++ kernels. ColossalAI will build them during runtime. If you want to install and enable CUDA kernel fusion (compulsory installation when using fused optimizer):

BUILD\_EXT=1 pip install .

For Users with CUDA 10.2, you can still build ColossalAI from source. However, you need to manually download the cub library and copy it to the corresponding directory.

# clone the repository
git clone https://github.com/hpcaitech/ColossalAI.git
cd ColossalAI

# download the cub library
wget https://github.com/NVIDIA/cub/archive/refs/tags/1.8.0.zip
unzip 1.8.0.zip
cp -r cub-1.8.0/cub/ colossalai/kernel/cuda\_native/csrc/kernels/include/

# install
BUILD\_EXT=1 pip install .

(back to top)

Use Docker
----------

### Pull from DockerHub

You can directly pull the docker image from our DockerHub page. The image is automatically uploaded upon release.

### Build On Your Own

Run the following command to build a docker image from Dockerfile provided.

> Building Colossal-AI from scratch requires GPU support, you need to use Nvidia Docker Runtime as the default when doing `docker build`. More details can be found here. We recommend you install Colossal-AI from our project page directly.

cd ColossalAI
docker build -t colossalai ./docker

Run the following command to start the docker container in interactive mode.

docker run -ti --gpus all --rm --ipc=host colossalai bash

(back to top)

Community
---------

Join the Colossal-AI community on Forum, Slack, and WeChat(微信) to share your suggestions, feedback, and questions with our engineering team.

Contributing
------------

Referring to the successful attempts of BLOOM and Stable Diffusion, any and all developers and partners with computing powers, datasets, models are welcome to join and build the Colossal-AI community, making efforts towards the era of big AI models!

You may contact us or participate in the following ways:

1.  Leaving a Star ⭐ to show your like and support. Thanks!
2.  Posting an issue, or submitting a PR on GitHub follow the guideline in Contributing
3.  Send your official proposal to email contact@hpcaitech.com

Thanks so much to all of our amazing contributors!

(back to top)

CI/CD
-----

We leverage the power of GitHub Actions to automate our development, release and deployment workflows. Please check out this documentation on how the automated workflows are operated.

Cite Us
-------

This project is inspired by some related projects (some by our team and some by other organizations). We would like to credit these amazing projects as listed in the Reference List.

To cite this project, you can use the following BibTeX citation.

```
@inproceedings{10.1145/3605573.3605613,
author = {Li, Shenggui and Liu, Hongxin and Bian, Zhengda and Fang, Jiarui and Huang, Haichen and Liu, Yuliang and Wang, Boxiang and You, Yang},
title = {Colossal-AI: A Unified Deep Learning System For Large-Scale Parallel Training},
year = {2023},
isbn = {9798400708435},
publisher = {Association for Computing Machinery},
address = {New York, NY, USA},
url = {https://doi.org/10.1145/3605573.3605613},
doi = {10.1145/3605573.3605613},
abstract = {The success of Transformer models has pushed the deep learning model scale to billions of parameters, but the memory limitation of a single GPU has led to an urgent need for training on multi-GPU clusters. However, the best practice for choosing the optimal parallel strategy is still lacking, as it requires domain expertise in both deep learning and parallel computing. The Colossal-AI system addressed the above challenge by introducing a unified interface to scale your sequential code of model training to distributed environments. It supports parallel training methods such as data, pipeline, tensor, and sequence parallelism and is integrated with heterogeneous training and zero redundancy optimizer. Compared to the baseline system, Colossal-AI can achieve up to 2.76 times training speedup on large-scale models.},
booktitle = {Proceedings of the 52nd International Conference on Parallel Processing},
pages = {766–775},
numpages = {10},
keywords = {datasets, gaze detection, text tagging, neural networks},
location = {Salt Lake City, UT, USA},
series = {ICPP '23}
}
```

Colossal-AI has been accepted as official tutorial by top conferences NeurIPS, SC, AAAI, PPoPP, CVPR, ISC, NVIDIA GTC ,etc.

(back to top)
