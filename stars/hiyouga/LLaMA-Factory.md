---
project: LLaMA-Factory
stars: 37254
description: Unified Efficient Fine-Tuning of 100+ LLMs (ACL 2024)
url: https://github.com/hiyouga/LLaMA-Factory
---

👋 Join our WeChat or NPU user group.

\[ English | 中文 \]

**Fine-tuning a large language model can be easy as...**

en.mp4

Choose your path:

-   **Documentation (WIP)**: https://llamafactory.readthedocs.io/zh-cn/latest/
-   **Colab**: https://colab.research.google.com/drive/1eRTPn37ltBbYsISy9Aw2NuI2Aq5CQrD9?usp=sharing
-   **Local machine**: Please refer to usage
-   **PAI-DSW**: Llama3 Example | Qwen2-VL Example
-   **Amazon SageMaker**: Blog

Note

Except for the above links, all other websites are unauthorized third-party websites. Please carefully use them.

Table of Contents
-----------------

-   Features
-   Benchmark
-   Changelog
-   Supported Models
-   Supported Training Approaches
-   Provided Datasets
-   Requirement
-   Getting Started
    -   Installation
    -   Data Preparation
    -   Quickstart
    -   Fine-Tuning with LLaMA Board GUI
    -   Build Docker
    -   Deploy with OpenAI-style API and vLLM
    -   Download from ModelScope Hub
    -   Download from Modelers Hub
    -   Use W&B Logger
    -   Use SwanLab Logger
-   Projects using LLaMA Factory
-   License
-   Citation
-   Acknowledgement

Features
--------

-   **Various models**: LLaMA, LLaVA, Mistral, Mixtral-MoE, Qwen, Qwen2-VL, Yi, Gemma, Baichuan, ChatGLM, Phi, etc.
-   **Integrated methods**: (Continuous) pre-training, (multimodal) supervised fine-tuning, reward modeling, PPO, DPO, KTO, ORPO, etc.
-   **Scalable resources**: 16-bit full-tuning, freeze-tuning, LoRA and 2/3/4/5/6/8-bit QLoRA via AQLM/AWQ/GPTQ/LLM.int8/HQQ/EETQ.
-   **Advanced algorithms**: GaLore, BAdam, Adam-mini, DoRA, LongLoRA, LLaMA Pro, Mixture-of-Depths, LoRA+, LoftQ, PiSSA and Agent tuning.
-   **Practical tricks**: FlashAttention-2, Unsloth, Liger Kernel, RoPE scaling, NEFTune and rsLoRA.
-   **Experiment monitors**: LlamaBoard, TensorBoard, Wandb, MLflow, SwanLab, etc.
-   **Faster inference**: OpenAI-style API, Gradio UI and CLI with vLLM worker.

Benchmark
---------

Compared to ChatGLM's P-Tuning, LLaMA Factory's LoRA tuning offers up to **3.7 times faster** training speed with a better Rouge score on the advertising text generation task. By leveraging 4-bit quantization technique, LLaMA Factory's QLoRA further improves the efficiency regarding the GPU memory.

Definitions

-   **Training Speed**: the number of training samples processed per second during the training. (bs=4, cutoff\_len=1024)
-   **Rouge Score**: Rouge-2 score on the development set of the advertising text generation task. (bs=4, cutoff\_len=1024)
-   **GPU Memory**: Peak GPU memory usage in 4-bit quantized training. (bs=1, cutoff\_len=1024)
-   We adopt `pre_seq_len=128` for ChatGLM's P-Tuning and `lora_rank=32` for LLaMA Factory's LoRA tuning.

Changelog
---------

\[24/12/21\] We supported using **SwanLab** for experiment tracking and visualization. See this section for details.

\[24/11/27\] We supported fine-tuning the **Skywork-o1** model and the **OpenO1** dataset.

\[24/10/09\] We supported downloading pre-trained models and datasets from the **Modelers Hub**. See this tutorial for usage.

Full Changelog

\[24/09/19\] We supported fine-tuning the **Qwen2.5** models.

\[24/08/30\] We supported fine-tuning the **Qwen2-VL** models. Thank @simonJJJ's PR.

\[24/08/27\] We supported **Liger Kernel**. Try `enable_liger_kernel: true` for efficient training.

\[24/08/09\] We supported **Adam-mini** optimizer. See examples for usage. Thank @relic-yuexi's PR.

\[24/07/04\] We supported contamination-free packed training. Use `neat_packing: true` to activate it. Thank @chuan298's PR.

\[24/06/16\] We supported **PiSSA** algorithm. See examples for usage.

\[24/06/07\] We supported fine-tuning the **Qwen2** and **GLM-4** models.

\[24/05/26\] We supported **SimPO** algorithm for preference learning. See examples for usage.

\[24/05/20\] We supported fine-tuning the **PaliGemma** series models. Note that the PaliGemma models are pre-trained models, you need to fine-tune them with `paligemma` template for chat completion.

\[24/05/18\] We supported **KTO** algorithm for preference learning. See examples for usage.

\[24/05/14\] We supported training and inference on the Ascend NPU devices. Check installation section for details.

\[24/04/26\] We supported fine-tuning the **LLaVA-1.5** multimodal LLMs. See examples for usage.

\[24/04/22\] We provided a **Colab notebook** for fine-tuning the Llama-3 model on a free T4 GPU. Two Llama-3-derived models fine-tuned using LLaMA Factory are available at Hugging Face, check Llama3-8B-Chinese-Chat and Llama3-Chinese for details.

\[24/04/21\] We supported **Mixture-of-Depths** according to AstraMindAI's implementation. See examples for usage.

\[24/04/16\] We supported **BAdam** optimizer. See examples for usage.

\[24/04/16\] We supported **unsloth**'s long-sequence training (Llama-2-7B-56k within 24GB). It achieves **117%** speed and **50%** memory compared with FlashAttention-2, more benchmarks can be found in this page.

\[24/03/31\] We supported **ORPO**. See examples for usage.

\[24/03/21\] Our paper "LlamaFactory: Unified Efficient Fine-Tuning of 100+ Language Models" is available at arXiv!

\[24/03/20\] We supported **FSDP+QLoRA** that fine-tunes a 70B model on 2x24GB GPUs. See examples for usage.

\[24/03/13\] We supported **LoRA+**. See examples for usage.

\[24/03/07\] We supported **GaLore** optimizer. See examples for usage.

\[24/03/07\] We integrated **vLLM** for faster and concurrent inference. Try `infer_backend: vllm` to enjoy **270%** inference speed.

\[24/02/28\] We supported weight-decomposed LoRA (**DoRA**). Try `use_dora: true` to activate DoRA training.

\[24/02/15\] We supported **block expansion** proposed by LLaMA Pro. See examples for usage.

\[24/02/05\] Qwen1.5 (Qwen2 beta version) series models are supported in LLaMA-Factory. Check this blog post for details.

\[24/01/18\] We supported **agent tuning** for most models, equipping model with tool using abilities by fine-tuning with `dataset: glaive_toolcall_en`.

\[23/12/23\] We supported **unsloth**'s implementation to boost LoRA tuning for the LLaMA, Mistral and Yi models. Try `use_unsloth: true` argument to activate unsloth patch. It achieves **170%** speed in our benchmark, check this page for details.

\[23/12/12\] We supported fine-tuning the latest MoE model **Mixtral 8x7B** in our framework. See hardware requirement here.

\[23/12/01\] We supported downloading pre-trained models and datasets from the **ModelScope Hub**. See this tutorial for usage.

\[23/10/21\] We supported **NEFTune** trick for fine-tuning. Try `neftune_noise_alpha: 5` argument to activate NEFTune.

\[23/09/27\] We supported **$S^2$-Attn** proposed by LongLoRA for the LLaMA models. Try `shift_attn: true` argument to enable shift short attention.

\[23/09/23\] We integrated MMLU, C-Eval and CMMLU benchmarks in this repo. See examples for usage.

\[23/09/10\] We supported **FlashAttention-2**. Try `flash_attn: fa2` argument to enable FlashAttention-2 if you are using RTX4090, A100 or H100 GPUs.

\[23/08/12\] We supported **RoPE scaling** to extend the context length of the LLaMA models. Try `rope_scaling: linear` argument in training and `rope_scaling: dynamic` argument at inference to extrapolate the position embeddings.

\[23/08/11\] We supported **DPO training** for instruction-tuned models. See examples for usage.

\[23/07/31\] We supported **dataset streaming**. Try `streaming: true` and `max_steps: 10000` arguments to load your dataset in streaming mode.

\[23/07/29\] We released two instruction-tuned 13B models at Hugging Face. See these Hugging Face Repos (LLaMA-2 / Baichuan) for details.

\[23/07/18\] We developed an **all-in-one Web UI** for training, evaluation and inference. Try `train_web.py` to fine-tune models in your Web browser. Thank @KanadeSiina and @codemayq for their efforts in the development.

\[23/07/09\] We released **FastEdit** ⚡🩹, an easy-to-use package for editing the factual knowledge of large language models efficiently. Please follow FastEdit if you are interested.

\[23/06/29\] We provided a **reproducible example** of training a chat model using instruction-following datasets, see Baichuan-7B-sft for details.

\[23/06/22\] We aligned the demo API with the OpenAI's format where you can insert the fine-tuned model in **arbitrary ChatGPT-based applications**.

\[23/06/03\] We supported quantized training and inference (aka **QLoRA**). See examples for usage.

Supported Models
----------------

Model

Model size

Template

Baichuan 2

7B/13B

baichuan2

BLOOM/BLOOMZ

560M/1.1B/1.7B/3B/7.1B/176B

\-

ChatGLM3

6B

chatglm3

Command R

35B/104B

cohere

DeepSeek (Code/MoE)

7B/16B/67B/236B

deepseek

DeepSeek 2.5/3

236B/685B

deepseek3

Falcon

7B/11B/40B/180B

falcon

Gemma/Gemma 2/CodeGemma

2B/7B/9B/27B

gemma

GLM-4

9B

glm4

GPT-2

0.1B/0.4B/0.8B/1.5B

\-

Granite 3.0-3.1

1B/2B/3B/8B

granite3

Index

1.9B

index

InternLM2/InternLM2.5

7B/20B

intern2

Llama

7B/13B/33B/65B

\-

Llama 2

7B/13B/70B

llama2

Llama 3-3.3

1B/3B/8B/70B

llama3

Llama 3.2 Vision

11B/90B

mllama

LLaVA-1.5

7B/13B

llava

LLaVA-NeXT

7B/8B/13B/34B/72B/110B

llava\_next

LLaVA-NeXT-Video

7B/34B

llava\_next\_video

MiniCPM

1B/2B/4B

cpm/cpm3

Mistral/Mixtral

7B/8x7B/8x22B

mistral

OLMo

1B/7B

\-

PaliGemma/PaliGemma2

3B/10B/28B

paligemma

Phi-1.5/Phi-2

1.3B/2.7B

\-

Phi-3

4B/14B

phi

Phi-3-small

7B

phi\_small

Pixtral

12B

pixtral

Qwen/QwQ (1-2.5) (Code/Math/MoE)

0.5B/1.5B/3B/7B/14B/32B/72B/110B

qwen

Qwen2-VL/QVQ

2B/7B/72B

qwen2\_vl

Skywork o1

8B

skywork\_o1

StarCoder 2

3B/7B/15B

\-

TeleChat2

3B/7B/35B/115B

telechat2

XVERSE

7B/13B/65B

xverse

Yi/Yi-1.5 (Code)

1.5B/6B/9B/34B

yi

Yi-VL

6B/34B

yi\_vl

Yuan 2

2B/51B/102B

yuan

Note

For the "base" models, the `template` argument can be chosen from `default`, `alpaca`, `vicuna` etc. But make sure to use the **corresponding template** for the "instruct/chat" models.

Remember to use the **SAME** template in training and inference.

Please refer to constants.py for a full list of models we supported.

You also can add a custom chat template to template.py.

Supported Training Approaches
-----------------------------

Approach

Full-tuning

Freeze-tuning

LoRA

QLoRA

Pre-Training

✅

✅

✅

✅

Supervised Fine-Tuning

✅

✅

✅

✅

Reward Modeling

✅

✅

✅

✅

PPO Training

✅

✅

✅

✅

DPO Training

✅

✅

✅

✅

KTO Training

✅

✅

✅

✅

ORPO Training

✅

✅

✅

✅

SimPO Training

✅

✅

✅

✅

Tip

The implementation details of PPO can be found in this blog.

Provided Datasets
-----------------

Pre-training datasets

-   Wiki Demo (en)
-   RefinedWeb (en)
-   RedPajama V2 (en)
-   Wikipedia (en)
-   Wikipedia (zh)
-   Pile (en)
-   SkyPile (zh)
-   FineWeb (en)
-   FineWeb-Edu (en)
-   The Stack (en)
-   StarCoder (en)

Supervised fine-tuning datasets

-   Identity (en&zh)
-   Stanford Alpaca (en)
-   Stanford Alpaca (zh)
-   Alpaca GPT4 (en&zh)
-   Glaive Function Calling V2 (en&zh)
-   LIMA (en)
-   Guanaco Dataset (multilingual)
-   BELLE 2M (zh)
-   BELLE 1M (zh)
-   BELLE 0.5M (zh)
-   BELLE Dialogue 0.4M (zh)
-   BELLE School Math 0.25M (zh)
-   BELLE Multiturn Chat 0.8M (zh)
-   UltraChat (en)
-   OpenPlatypus (en)
-   CodeAlpaca 20k (en)
-   Alpaca CoT (multilingual)
-   OpenOrca (en)
-   SlimOrca (en)
-   MathInstruct (en)
-   Firefly 1.1M (zh)
-   Wiki QA (en)
-   Web QA (zh)
-   WebNovel (zh)
-   Nectar (en)
-   deepctrl (en&zh)
-   Advertise Generating (zh)
-   ShareGPT Hyperfiltered (en)
-   ShareGPT4 (en&zh)
-   UltraChat 200k (en)
-   AgentInstruct (en)
-   LMSYS Chat 1M (en)
-   Evol Instruct V2 (en)
-   Cosmopedia (en)
-   STEM (zh)
-   Ruozhiba (zh)
-   Neo-sft (zh)
-   Magpie-Pro-300K-Filtered (en)
-   Magpie-ultra-v0.1 (en)
-   WebInstructSub (en)
-   OpenO1-SFT (en&zh)
-   LLaVA mixed (en&zh)
-   Pokemon-gpt4o-captions (en&zh)
-   Open Assistant (de)
-   Dolly 15k (de)
-   Alpaca GPT4 (de)
-   OpenSchnabeltier (de)
-   Evol Instruct (de)
-   Dolphin (de)
-   Booksum (de)
-   Airoboros (de)
-   Ultrachat (de)

Preference datasets

-   DPO mixed (en&zh)
-   UltraFeedback (en)
-   RLHF-V (en)
-   VLFeedback (en)
-   Orca DPO Pairs (en)
-   HH-RLHF (en)
-   Nectar (en)
-   Orca DPO (de)
-   KTO mixed (en)

Some datasets require confirmation before using them, so we recommend logging in with your Hugging Face account using these commands.

pip install --upgrade huggingface\_hub
huggingface-cli login

Requirement
-----------

Mandatory

Minimum

Recommend

python

3.8

3.11

torch

1.13.1

2.4.0

transformers

4.41.2

4.43.4

datasets

2.16.0

2.20.0

accelerate

0.30.1

0.32.0

peft

0.11.1

0.12.0

trl

0.8.6

0.9.6

Optional

Minimum

Recommend

CUDA

11.6

12.2

deepspeed

0.10.0

0.14.0

bitsandbytes

0.39.0

0.43.1

vllm

0.4.3

0.5.0

flash-attn

2.3.0

2.6.3

### Hardware Requirement

\* _estimated_

Method

Bits

7B

13B

30B

70B

110B

8x7B

8x22B

Full

AMP

120GB

240GB

600GB

1200GB

2000GB

900GB

2400GB

Full

16

60GB

120GB

300GB

600GB

900GB

400GB

1200GB

Freeze

16

20GB

40GB

80GB

200GB

360GB

160GB

400GB

LoRA/GaLore/BAdam

16

16GB

32GB

64GB

160GB

240GB

120GB

320GB

QLoRA

8

10GB

20GB

40GB

80GB

140GB

60GB

160GB

QLoRA

4

6GB

12GB

24GB

48GB

72GB

30GB

96GB

QLoRA

2

4GB

8GB

16GB

24GB

48GB

18GB

48GB

Getting Started
---------------

### Installation

Important

Installation is mandatory.

git clone --depth 1 https://github.com/hiyouga/LLaMA-Factory.git
cd LLaMA-Factory
pip install -e ".\[torch,metrics\]"

Extra dependencies available: torch, torch-npu, metrics, deepspeed, liger-kernel, bitsandbytes, hqq, eetq, gptq, awq, aqlm, vllm, galore, badam, adam-mini, qwen, modelscope, openmind, swanlab, quality

Tip

Use `pip install --no-deps -e .` to resolve package conflicts.

For Windows users

If you want to enable the quantized LoRA (QLoRA) on the Windows platform, you need to install a pre-built version of `bitsandbytes` library, which supports CUDA 11.1 to 12.2, please select the appropriate release version based on your CUDA version.

pip install https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.41.2.post2-py3-none-win\_amd64.whl

To enable FlashAttention-2 on the Windows platform, you need to install the precompiled `flash-attn` library, which supports CUDA 12.1 to 12.2. Please download the corresponding version from flash-attention based on your requirements.

For Ascend NPU users

To install LLaMA Factory on Ascend NPU devices, please specify extra dependencies: `pip install -e ".[torch-npu,metrics]"`. Additionally, you need to install the **Ascend CANN Toolkit and Kernels**. Please follow the installation tutorial or use the following commands:

# replace the url according to your CANN version and devices
# install CANN Toolkit
wget https://ascend-repo.obs.cn-east-2.myhuaweicloud.com/Milan-ASL/Milan-ASL%20V100R001C17SPC701/Ascend-cann-toolkit\_8.0.RC1.alpha001\_linux-"$(uname -i)".run
bash Ascend-cann-toolkit\_8.0.RC1.alpha001\_linux-"$(uname -i)".run --install

# install CANN Kernels
wget https://ascend-repo.obs.cn-east-2.myhuaweicloud.com/Milan-ASL/Milan-ASL%20V100R001C17SPC701/Ascend-cann-kernels-910b\_8.0.RC1.alpha001\_linux.run
bash Ascend-cann-kernels-910b\_8.0.RC1.alpha001\_linux.run --install

# set env variables
source /usr/local/Ascend/ascend-toolkit/set\_env.sh

Requirement

Minimum

Recommend

CANN

8.0.RC1

8.0.RC1

torch

2.1.0

2.1.0

torch-npu

2.1.0

2.1.0.post3

deepspeed

0.13.2

0.13.2

Remember to use `ASCEND_RT_VISIBLE_DEVICES` instead of `CUDA_VISIBLE_DEVICES` to specify the device to use.

If you cannot infer model on NPU devices, try setting `do_sample: false` in the configurations.

Download the pre-built Docker images: 32GB | 64GB

### Data Preparation

Please refer to data/README.md for checking the details about the format of dataset files. You can either use datasets on HuggingFace / ModelScope / Modelers hub or load the dataset in local disk.

Note

Please update `data/dataset_info.json` to use your custom dataset.

### Quickstart

Use the following 3 commands to run LoRA **fine-tuning**, **inference** and **merging** of the Llama3-8B-Instruct model, respectively.

llamafactory-cli train examples/train\_lora/llama3\_lora\_sft.yaml
llamafactory-cli chat examples/inference/llama3\_lora\_sft.yaml
llamafactory-cli export examples/merge\_lora/llama3\_lora\_sft.yaml

See examples/README.md for advanced usage (including distributed training).

Tip

Use `llamafactory-cli help` to show help information.

### Fine-Tuning with LLaMA Board GUI (powered by Gradio)

llamafactory-cli webui

### Build Docker

For CUDA users:

cd docker/docker-cuda/
docker compose up -d
docker compose exec llamafactory bash

For Ascend NPU users:

cd docker/docker-npu/
docker compose up -d
docker compose exec llamafactory bash

For AMD ROCm users:

cd docker/docker-rocm/
docker compose up -d
docker compose exec llamafactory bash

Build without Docker Compose

For CUDA users:

docker build -f ./docker/docker-cuda/Dockerfile \\
    --build-arg INSTALL\_BNB=false \\
    --build-arg INSTALL\_VLLM=false \\
    --build-arg INSTALL\_DEEPSPEED=false \\
    --build-arg INSTALL\_FLASHATTN=false \\
    --build-arg PIP\_INDEX=https://pypi.org/simple \\
    -t llamafactory:latest .

docker run -dit --gpus=all \\
    -v ./hf\_cache:/root/.cache/huggingface \\
    -v ./ms\_cache:/root/.cache/modelscope \\
    -v ./om\_cache:/root/.cache/openmind \\
    -v ./data:/app/data \\
    -v ./output:/app/output \\
    -p 7860:7860 \\
    -p 8000:8000 \\
    --shm-size 16G \\
    --name llamafactory \\
    llamafactory:latest

docker exec -it llamafactory bash

For Ascend NPU users:

# Choose docker image upon your environment
docker build -f ./docker/docker-npu/Dockerfile \\
    --build-arg INSTALL\_DEEPSPEED=false \\
    --build-arg PIP\_INDEX=https://pypi.org/simple \\
    -t llamafactory:latest .

# Change \`device\` upon your resources
docker run -dit \\
    -v ./hf\_cache:/root/.cache/huggingface \\
    -v ./ms\_cache:/root/.cache/modelscope \\
    -v ./om\_cache:/root/.cache/openmind \\
    -v ./data:/app/data \\
    -v ./output:/app/output \\
    -v /usr/local/dcmi:/usr/local/dcmi \\
    -v /usr/local/bin/npu-smi:/usr/local/bin/npu-smi \\
    -v /usr/local/Ascend/driver:/usr/local/Ascend/driver \\
    -v /etc/ascend\_install.info:/etc/ascend\_install.info \\
    -p 7860:7860 \\
    -p 8000:8000 \\
    --device /dev/davinci0 \\
    --device /dev/davinci\_manager \\
    --device /dev/devmm\_svm \\
    --device /dev/hisi\_hdc \\
    --shm-size 16G \\
    --name llamafactory \\
    llamafactory:latest

docker exec -it llamafactory bash

For AMD ROCm users:

docker build -f ./docker/docker-rocm/Dockerfile \\
    --build-arg INSTALL\_BNB=false \\
    --build-arg INSTALL\_VLLM=false \\
    --build-arg INSTALL\_DEEPSPEED=false \\
    --build-arg INSTALL\_FLASHATTN=false \\
    --build-arg PIP\_INDEX=https://pypi.org/simple \\
    -t llamafactory:latest .

docker run -dit \\
    -v ./hf\_cache:/root/.cache/huggingface \\
    -v ./ms\_cache:/root/.cache/modelscope \\
    -v ./om\_cache:/root/.cache/openmind \\
    -v ./data:/app/data \\
    -v ./output:/app/output \\
    -v ./saves:/app/saves \\
    -p 7860:7860 \\
    -p 8000:8000 \\
    --device /dev/kfd \\
    --device /dev/dri \\
    --shm-size 16G \\
    --name llamafactory \\
    llamafactory:latest

docker exec -it llamafactory bash

Details about volume

-   `hf_cache`: Utilize Hugging Face cache on the host machine. Reassignable if a cache already exists in a different directory.
-   `ms_cache`: Similar to Hugging Face cache but for ModelScope users.
-   `om_cache`: Similar to Hugging Face cache but for Modelers users.
-   `data`: Place datasets on this dir of the host machine so that they can be selected on LLaMA Board GUI.
-   `output`: Set export dir to this location so that the merged result can be accessed directly on the host machine.

### Deploy with OpenAI-style API and vLLM

API\_PORT=8000 llamafactory-cli api examples/inference/llama3\_vllm.yaml

Tip

Visit this page for API document.

Examples: Image understanding | Function calling

### Download from ModelScope Hub

If you have trouble with downloading models and datasets from Hugging Face, you can use ModelScope.

export USE\_MODELSCOPE\_HUB=1 # \`set USE\_MODELSCOPE\_HUB=1\` for Windows

Train the model by specifying a model ID of the ModelScope Hub as the `model_name_or_path`. You can find a full list of model IDs at ModelScope Hub, e.g., `LLM-Research/Meta-Llama-3-8B-Instruct`.

### Download from Modelers Hub

You can also use Modelers Hub to download models and datasets.

export USE\_OPENMIND\_HUB=1 # \`set USE\_OPENMIND\_HUB=1\` for Windows

Train the model by specifying a model ID of the Modelers Hub as the `model_name_or_path`. You can find a full list of model IDs at Modelers Hub, e.g., `TeleAI/TeleChat-7B-pt`.

### Use W&B Logger

To use Weights & Biases for logging experimental results, you need to add the following arguments to yaml files.

report\_to: wandb
run\_name: test\_run # optional

Set `WANDB_API_KEY` to your key when launching training tasks to log in with your W&B account.

### Use SwanLab Logger

To use SwanLab for logging experimental results, you need to add the following arguments to yaml files.

use\_swanlab: true
swanlab\_run\_name: test\_run # optional

When launching training tasks, you can log in to SwanLab in three ways:

1.  Add `swanlab_api_key=<your_api_key>` to the yaml file, and set it to your API key.
2.  Set the environment variable `SWANLAB_API_KEY` to your API key.
3.  Use the `swanlab login` command to complete the login.

Projects using LLaMA Factory
----------------------------

If you have a project that should be incorporated, please contact via email or create a pull request.

Click to show

1.  Wang et al. ESRL: Efficient Sampling-based Reinforcement Learning for Sequence Generation. 2023. \[arxiv\]
2.  Yu et al. Open, Closed, or Small Language Models for Text Classification? 2023. \[arxiv\]
3.  Wang et al. UbiPhysio: Support Daily Functioning, Fitness, and Rehabilitation with Action Understanding and Feedback in Natural Language. 2023. \[arxiv\]
4.  Luceri et al. Leveraging Large Language Models to Detect Influence Campaigns in Social Media. 2023. \[arxiv\]
5.  Zhang et al. Alleviating Hallucinations of Large Language Models through Induced Hallucinations. 2023. \[arxiv\]
6.  Wang et al. Know Your Needs Better: Towards Structured Understanding of Marketer Demands with Analogical Reasoning Augmented LLMs. KDD 2024. \[arxiv\]
7.  Wang et al. CANDLE: Iterative Conceptualization and Instantiation Distillation from Large Language Models for Commonsense Reasoning. ACL 2024. \[arxiv\]
8.  Choi et al. FACT-GPT: Fact-Checking Augmentation via Claim Matching with LLMs. 2024. \[arxiv\]
9.  Zhang et al. AutoMathText: Autonomous Data Selection with Language Models for Mathematical Texts. 2024. \[arxiv\]
10.  Lyu et al. KnowTuning: Knowledge-aware Fine-tuning for Large Language Models. 2024. \[arxiv\]
11.  Yang et al. LaCo: Large Language Model Pruning via Layer Collaps. 2024. \[arxiv\]
12.  Bhardwaj et al. Language Models are Homer Simpson! Safety Re-Alignment of Fine-tuned Language Models through Task Arithmetic. 2024. \[arxiv\]
13.  Yang et al. Enhancing Empathetic Response Generation by Augmenting LLMs with Small-scale Empathetic Models. 2024. \[arxiv\]
14.  Yi et al. Generation Meets Verification: Accelerating Large Language Model Inference with Smart Parallel Auto-Correct Decoding. ACL 2024 Findings. \[arxiv\]
15.  Cao et al. Head-wise Shareable Attention for Large Language Models. 2024. \[arxiv\]
16.  Zhang et al. Enhancing Multilingual Capabilities of Large Language Models through Self-Distillation from Resource-Rich Languages. 2024. \[arxiv\]
17.  Kim et al. Efficient and Effective Vocabulary Expansion Towards Multilingual Large Language Models. 2024. \[arxiv\]
18.  Yu et al. KIEval: A Knowledge-grounded Interactive Evaluation Framework for Large Language Models. ACL 2024. \[arxiv\]
19.  Huang et al. Key-Point-Driven Data Synthesis with its Enhancement on Mathematical Reasoning. 2024. \[arxiv\]
20.  Duan et al. Negating Negatives: Alignment without Human Positive Samples via Distributional Dispreference Optimization. 2024. \[arxiv\]
21.  Xie and Schwertfeger. Empowering Robotics with Large Language Models: osmAG Map Comprehension with LLMs. 2024. \[arxiv\]
22.  Wu et al. Large Language Models are Parallel Multilingual Learners. 2024. \[arxiv\]
23.  Zhang et al. EDT: Improving Large Language Models' Generation by Entropy-based Dynamic Temperature Sampling. 2024. \[arxiv\]
24.  Weller et al. FollowIR: Evaluating and Teaching Information Retrieval Models to Follow Instructions. 2024. \[arxiv\]
25.  Hongbin Na. CBT-LLM: A Chinese Large Language Model for Cognitive Behavioral Therapy-based Mental Health Question Answering. COLING 2024. \[arxiv\]
26.  Zan et al. CodeS: Natural Language to Code Repository via Multi-Layer Sketch. 2024. \[arxiv\]
27.  Liu et al. Extensive Self-Contrast Enables Feedback-Free Language Model Alignment. 2024. \[arxiv\]
28.  Luo et al. BAdam: A Memory Efficient Full Parameter Training Method for Large Language Models. 2024. \[arxiv\]
29.  Du et al. Chinese Tiny LLM: Pretraining a Chinese-Centric Large Language Model. 2024. \[arxiv\]
30.  Ma et al. Parameter Efficient Quasi-Orthogonal Fine-Tuning via Givens Rotation. ICML 2024. \[arxiv\]
31.  Liu et al. Dynamic Generation of Personalities with Large Language Models. 2024. \[arxiv\]
32.  Shang et al. How Far Have We Gone in Stripped Binary Code Understanding Using Large Language Models. 2024. \[arxiv\]
33.  Huang et al. LLMTune: Accelerate Database Knob Tuning with Large Language Models. 2024. \[arxiv\]
34.  Deng et al. Text-Tuple-Table: Towards Information Integration in Text-to-Table Generation via Global Tuple Extraction. 2024. \[arxiv\]
35.  Acikgoz et al. Hippocrates: An Open-Source Framework for Advancing Large Language Models in Healthcare. 2024. \[arxiv\]
36.  Zhang et al. Small Language Models Need Strong Verifiers to Self-Correct Reasoning. ACL 2024 Findings. \[arxiv\]
37.  Zhou et al. FREB-TQA: A Fine-Grained Robustness Evaluation Benchmark for Table Question Answering. NAACL 2024. \[arxiv\]
38.  Xu et al. Large Language Models for Cyber Security: A Systematic Literature Review. 2024. \[arxiv\]
39.  Dammu et al. "They are uncultured": Unveiling Covert Harms and Social Threats in LLM Generated Conversations. 2024. \[arxiv\]
40.  Yi et al. A safety realignment framework via subspace-oriented model fusion for large language models. 2024. \[arxiv\]
41.  Lou et al. SPO: Multi-Dimensional Preference Sequential Alignment With Implicit Reward Modeling. 2024. \[arxiv\]
42.  Zhang et al. Getting More from Less: Large Language Models are Good Spontaneous Multilingual Learners. 2024. \[arxiv\]
43.  Zhang et al. TS-Align: A Teacher-Student Collaborative Framework for Scalable Iterative Finetuning of Large Language Models. 2024. \[arxiv\]
44.  Zihong Chen. Sentence Segmentation and Sentence Punctuation Based on XunziALLM. 2024. \[paper\]
45.  Gao et al. The Best of Both Worlds: Toward an Honest and Helpful Large Language Model. 2024. \[arxiv\]
46.  Wang and Song. MARS: Benchmarking the Metaphysical Reasoning Abilities of Language Models with a Multi-task Evaluation Dataset. 2024. \[arxiv\]
47.  Hu et al. Computational Limits of Low-Rank Adaptation (LoRA) for Transformer-Based Models. 2024. \[arxiv\]
48.  Ge et al. Time Sensitive Knowledge Editing through Efficient Finetuning. ACL 2024. \[arxiv\]
49.  Tan et al. Peer Review as A Multi-Turn and Long-Context Dialogue with Role-Based Interactions. 2024. \[arxiv\]
50.  Song et al. Turbo Sparse: Achieving LLM SOTA Performance with Minimal Activated Parameters. 2024. \[arxiv\]
51.  Gu et al. RWKV-CLIP: A Robust Vision-Language Representation Learner. 2024. \[arxiv\]
52.  Chen et al. Advancing Tool-Augmented Large Language Models: Integrating Insights from Errors in Inference Trees. 2024. \[arxiv\]
53.  Zhu et al. Are Large Language Models Good Statisticians?. 2024. \[arxiv\]
54.  Li et al. Know the Unknown: An Uncertainty-Sensitive Method for LLM Instruction Tuning. 2024. \[arxiv\]
55.  Ding et al. IntentionQA: A Benchmark for Evaluating Purchase Intention Comprehension Abilities of Language Models in E-commerce. 2024. \[arxiv\]
56.  He et al. COMMUNITY-CROSS-INSTRUCT: Unsupervised Instruction Generation for Aligning Large Language Models to Online Communities. 2024. \[arxiv\]
57.  Lin et al. FVEL: Interactive Formal Verification Environment with Large Language Models via Theorem Proving. 2024. \[arxiv\]
58.  Treutlein et al. Connecting the Dots: LLMs can Infer and Verbalize Latent Structure from Disparate Training Data. 2024. \[arxiv\]
59.  Feng et al. SS-Bench: A Benchmark for Social Story Generation and Evaluation. 2024. \[arxiv\]
60.  Feng et al. Self-Constructed Context Decompilation with Fined-grained Alignment Enhancement. 2024. \[arxiv\]
61.  Liu et al. Large Language Models for Cuffless Blood Pressure Measurement From Wearable Biosignals. 2024. \[arxiv\]
62.  Iyer et al. Exploring Very Low-Resource Translation with LLMs: The University of Edinburgh's Submission to AmericasNLP 2024 Translation Task. AmericasNLP 2024. \[paper\]
63.  Li et al. Calibrating LLMs with Preference Optimization on Thought Trees for Generating Rationale in Science Question Scoring. 2024. \[arxiv\]
64.  Yang et al. Financial Knowledge Large Language Model. 2024. \[arxiv\]
65.  Lin et al. DogeRM: Equipping Reward Models with Domain Knowledge through Model Merging. 2024. \[arxiv\]
66.  Bako et al. Evaluating the Semantic Profiling Abilities of LLMs for Natural Language Utterances in Data Visualization. 2024. \[arxiv\]
67.  Huang et al. RoLoRA: Fine-tuning Rotated Outlier-free LLMs for Effective Weight-Activation Quantization. 2024. \[arxiv\]
68.  Jiang et al. LLM-Collaboration on Automatic Science Journalism for the General Audience. 2024. \[arxiv\]
69.  Inouye et al. Applied Auto-tuning on LoRA Hyperparameters. 2024. \[paper\]
70.  Qi et al. Research on Tibetan Tourism Viewpoints information generation system based on LLM. 2024. \[arxiv\]
71.  Xu et al. Course-Correction: Safety Alignment Using Synthetic Preferences. 2024. \[arxiv\]
72.  Sun et al. LAMBDA: A Large Model Based Data Agent. 2024. \[arxiv\]
73.  Zhu et al. CollectiveSFT: Scaling Large Language Models for Chinese Medical Benchmark with Collective Instructions in Healthcare. 2024. \[arxiv\]
74.  Yu et al. Correcting Negative Bias in Large Language Models through Negative Attention Score Alignment. 2024. \[arxiv\]
75.  Xie et al. The Power of Personalized Datasets: Advancing Chinese Composition Writing for Elementary School through Targeted Model Fine-Tuning. IALP 2024. \[paper\]
76.  Liu et al. Instruct-Code-Llama: Improving Capabilities of Language Model in Competition Level Code Generation by Online Judge Feedback. ICIC 2024. \[paper\]
77.  Wang et al. Cybernetic Sentinels: Unveiling the Impact of Safety Data Selection on Model Security in Supervised Fine-Tuning. ICIC 2024. \[paper\]
78.  Xia et al. Understanding the Performance and Estimating the Cost of LLM Fine-Tuning. 2024. \[arxiv\]
79.  Zeng et al. Perceive, Reflect, and Plan: Designing LLM Agent for Goal-Directed City Navigation without Instructions. 2024. \[arxiv\]
80.  Xia et al. Using Pre-trained Language Model for Accurate ESG Prediction. FinNLP 2024. \[paper\]
81.  Liang et al. I-SHEEP: Self-Alignment of LLM from Scratch through an Iterative Self-Enhancement Paradigm. 2024. \[arxiv\]
82.  Bai et al. Aligning Large Language Model with Direct Multi-Preference Optimization for Recommendation. CIKM 2024. \[paper\]
83.  **StarWhisper**: A large language model for Astronomy, based on ChatGLM2-6B and Qwen-14B.
84.  **DISC-LawLLM**: A large language model specialized in Chinese legal domain, based on Baichuan-13B, is capable of retrieving and reasoning on legal knowledge.
85.  **Sunsimiao**: A large language model specialized in Chinese medical domain, based on Baichuan-7B and ChatGLM-6B.
86.  **CareGPT**: A series of large language models for Chinese medical domain, based on LLaMA2-7B and Baichuan-13B.
87.  **MachineMindset**: A series of MBTI Personality large language models, capable of giving any LLM 16 different personality types based on different datasets and training methods.
88.  **Luminia-13B-v3**: A large language model specialized in generate metadata for stable diffusion. \[demo\]
89.  **Chinese-LLaVA-Med**: A multimodal large language model specialized in Chinese medical domain, based on LLaVA-1.5-7B.
90.  **AutoRE**: A document-level relation extraction system based on large language models.
91.  **NVIDIA RTX AI Toolkit**: SDKs for fine-tuning LLMs on Windows PC for NVIDIA RTX.
92.  **LazyLLM**: An easy and lazy way for building multi-agent LLMs applications and supports model fine-tuning via LLaMA Factory.
93.  **RAG-Retrieval**: A full pipeline for RAG retrieval model fine-tuning, inference, and distillation. \[blog\]
94.  **360-LLaMA-Factory**: A modified library that supports long sequence SFT & DPO using ring attention.

License
-------

This repository is licensed under the Apache-2.0 License.

Please follow the model licenses to use the corresponding model weights: Baichuan 2 / BLOOM / ChatGLM3 / Command R / DeepSeek / Falcon / Gemma / GLM-4 / GPT-2 / Granite / Index / InternLM2 / Llama / Llama 2 (LLaVA-1.5) / Llama 3 / MiniCPM / Mistral/Mixtral/Pixtral / OLMo / Phi-1.5/Phi-2 / Phi-3 / Qwen / Skywork / StarCoder 2 / TeleChat2 / XVERSE / Yi / Yi-1.5 / Yuan 2

Citation
--------

If this work is helpful, please kindly cite as:

@inproceedings{zheng2024llamafactory,
  title\={LlamaFactory: Unified Efficient Fine-Tuning of 100+ Language Models},
  author\={Yaowei Zheng and Richong Zhang and Junhao Zhang and Yanhan Ye and Zheyan Luo and Zhangchi Feng and Yongqiang Ma},
  booktitle\={Proceedings of the 62nd Annual Meeting of the Association for Computational Linguistics (Volume 3: System Demonstrations)},
  address\={Bangkok, Thailand},
  publisher\={Association for Computational Linguistics},
  year\={2024},
  url\={http://arxiv.org/abs/2403.13372}
}

Acknowledgement
---------------

This repo benefits from PEFT, TRL, QLoRA and FastChat. Thanks for their wonderful works.

Star History
------------
