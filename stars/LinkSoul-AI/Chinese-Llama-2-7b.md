---
project: Chinese-Llama-2-7b
stars: 2228
description: 开源社区第一个能下载、能运行的中文 LLaMA2 模型！
url: https://github.com/LinkSoul-AI/Chinese-Llama-2-7b
---

Chinese Llama 2 7B
==================

全部开源，完全可商用的**中文版 Llama2 模型及中英文 SFT 数据集**，输入格式严格遵循 _llama-2-chat_ 格式，兼容适配所有针对原版 _llama-2-chat_ 模型的优化。

基础演示
----

在线试玩
----

> Talk is cheap, Show you the Demo.

-   Demo 地址 / HuggingFace Spaces
-   Colab (FP16/需要开启高RAM,免费版无法使用)
-   Colab (INT4/需要开启高RAM,免费版无法使用)

最新更新
----

-   10月26日 提供始智AI链接Chinese Llama2 Chat Model 🔥🔥🔥
-   8月24日 新加ModelScope链接Chinese Llama2 Chat Model 🔥🔥🔥
-   7月31号 基于 Chinese-llama2-7b 的中英双语语音-文本 LLaSM 多模态模型开源 🔥🔥🔥
-   7月31号 基于 Chinese-llama2-7b 的中英双语视觉-文本 Chinese-LLaVA 多模态模型开源 🔥🔥🔥
-   7月26号 Chinese-llama2-7b-ggml 模型开源🔥🔥
-   7月23日 更新7b模型，添加API，提供4bit量化模型🔥🔥
-   7月22号 SFT训练/推理代码上线 🔥
-   7月21号 docker 一键部署上线 🔥
-   7月21号 demo上线 🔥
-   7月21号 中英双语 SFT 数据开源 🔥🔥
-   7月21号 Chinese-llama2-7b 模型开源 🔥🔥

资源下载
----

-   模型下载
    
    -   始智AI: Chinese Llama2 Chat Model
    -   ModelScope: Chinese Llama2 Chat Model
    -   HuggingFace: Chinese Llama2 Chat Model
    -   百度网盘: 1.0 正式版
    -   百度网盘: 1.1 加强火力版
-   4bit量化
    
    -   HuggingFace：Chinese Llama2 4bit Chat Model
    -   百度网盘: Chinese Llama2 4bit Chat Model
-   GGML Q4 模型：
    
    -   https://huggingface.co/LinkSoul/Chinese-Llama-2-7b-ggml
    -   https://huggingface.co/rffx0/Chinese-Llama-2-7b-ggml-model-q4\_0
    -   https://huggingface.co/soulteary/Chinese-Llama-2-7b-ggml-q4
    -   百度网盘: Chinese-Llama-2-7b-ggml

> 我们使用了中英文 SFT 数据集，数据量 1000 万。

-   数据集：https://huggingface.co/datasets/LinkSoul/instruction\_merge\_set

快速测试
----

from transformers import AutoTokenizer, AutoModelForCausalLM, TextStreamer

model\_path \= "LinkSoul/Chinese-Llama-2-7b"

tokenizer \= AutoTokenizer.from\_pretrained(model\_path, use\_fast\=False)
model \= AutoModelForCausalLM.from\_pretrained(model\_path).half().cuda()
streamer \= TextStreamer(tokenizer, skip\_prompt\=True, skip\_special\_tokens\=True)

instruction \= """\[INST\] <<SYS>>\\nYou are a helpful, respectful and honest assistant. Always answer as helpfully as possible, while being safe.  Your answers should not include any harmful, unethical, racist, sexist, toxic, dangerous, or illegal content. Please ensure that your responses are socially unbiased and positive in nature.
            If a question does not make any sense, or is not factually coherent, explain why instead of answering something not correct. If you don't know the answer to a question, please don't share false information.\\n<</SYS>>\\n\\n{} \[/INST\]"""

prompt \= instruction.format("用中文回答，When is the best time to visit Beijing, and do you have any suggestions for me?")
generate\_ids \= model.generate(tokenizer(prompt, return\_tensors\='pt').input\_ids.cuda(), max\_new\_tokens\=4096, streamer\=streamer)

Docker
------

你可以使用仓库中的 Dockerfile，来快速制作基于 Nvidia 最新版本的 `nvcr.io/nvidia/pytorch:23.06-py3` 基础镜像，在任何地方使用容器来运行中文的 LLaMA2 模型应用。

docker build -t linksoul/chinese-llama2-chat .

镜像构建完毕，使用命令运行镜像即可：

docker run --gpus all --ipc=host --ulimit memlock=-1 --ulimit stack=67108864 --rm -it -v \`pwd\`/LinkSoul:/app/LinkSoul -p 7860:7860 linksoul/chinese-llama2-chat

GGML / Llama.cpp
----------------

想要在 CPU 环境运行 LLaMA2 模型么？使用下面的方法吧。

-   使用 `ggml/convert_to_ggml.py` 进行转换操作，详见脚本支持的 CLI 参数。
-   或使用 `docker pull soulteary/llama2:converter` 下载模型格式转换工具镜像，在 Docker 容器中使用下面的两条命令完成操作（教程 构建能够使用 CPU 运行的 MetaAI LLaMA2 中文大模型 ）：

python3 convert.py /app/LinkSoul/Chinese-Llama-2-7b/ --outfile /app/LinkSoul/Chinese-Llama-2-7b-ggml.bin
./quantize /app/LinkSoul/Chinese-Llama-2-7b-ggml.bin /app/LinkSoul/Chinese-Llama-2-7b-ggml-q4.bin q4\_0

量化配置的定义:

转自: https://www.reddit.com/r/LocalLLaMA/comments/139yt87/notable\_differences\_between\_q4\_2\_and\_q5\_1/

-   q4\_0 = 32 numbers in chunk, 4 bits per weight, 1 scale value at 32-bit float (5 bits per value in average), each weight is given by the common scale \* quantized value.
    
-   q4\_1 = 32 numbers in chunk, 4 bits per weight, 1 scale value and 1 bias value at 32-bit float (6 bits per value in average), each weight is given by the common scale \* quantized value + common bias.
    
-   q4\_2 = same as q4\_0, but 16 numbers in chunk, 4 bits per weight, 1 scale value that is 16-bit float, same size as q4\_0 but better because chunks are smaller.
    
-   q4\_3 = already dead, but analogous: q4\_1 but 16 numbers in chunk, 4 bits per weight, scale value that is 16 bit and bias also 16 bits, same size as q4\_1 but better because chunks are smaller.
    
-   q5\_0 = 32 numbers in chunk, 5 bits per weight, 1 scale value at 16-bit float, size is 5.5 bits per weight
    
-   q5\_1 = 32 numbers in a chunk, 5 bits per weight, 1 scale value at 16 bit float and 1 bias value at 16 bit, size is 6 bits per weight.
    
-   q8\_0 = same as q4\_0, except 8 bits per weight, 1 scale value at 32 bits, making total of 9 bits per weight.
    

API部署
-----

首先需要安装额外的依赖 `pip install fastapi uvicorn`，然后运行仓库中的 api.py：

python api.py

默认部署在本地的 8000 端口，通过 POST 方法进行调用

curl -X POST "http://127.0.0.1:8000" \\
     -H 'Content-Type: application/json' \\
     -d '{"prompt": "你好", "history": \[\]}'

得到的返回值为

{
  "response":" 你好！我是一个人工智能语言模型，可以回答你的问题和进行对话。请问你有什么需要帮助的吗？ ",
  "history":\[\["<<SYS>>\\nYou are a helpful, respectful and honest assistant. Always answer as helpfully as possible, while being safe.  Your answers should not include any harmful, unethical, racist, sexist, toxic, dangerous, or illegal content. Please ensure that your responses are socially unbiased and positive in nature.\\n\\n            If a question does not make any sense, or is not factually coherent, explain why instead of answering something not correct. If you don't know the answer to a question, please don't share false information.\\n<</SYS>>\\n\\n你好"," 你好！我是一个人工智能语言模型，可以回答你的问题和进行对话。请问你有什么需要帮助的吗？ "\]\],
  "status":200,
  "time":"2023-08-01 09:22:16"
}

如何训练
----

DATASET="LinkSoul/instruction\_merge\_set"

DATA\_CACHE\_PATH="hf\_datasets\_cache"
MODEL\_PATH="/PATH/TO/TRANSFORMERS/VERSION/LLAMA2"

output\_dir="./checkpoints\_llama2"

torchrun --nnodes=1 --node\_rank=0 --nproc\_per\_node=8 \\
    --master\_port=25003 \\
        train.py \\
        --model\_name\_or\_path ${MODEL\_PATH} \\
        --data\_path ${DATASET} \\
        --data\_cache\_path ${DATA\_CACHE\_PATH} \\
        --bf16 True \\
        --output\_dir ${output\_dir} \\
        --num\_train\_epochs 1 \\
        --per\_device\_train\_batch\_size 4 \\
        --per\_device\_eval\_batch\_size 4 \\
        --gradient\_accumulation\_steps 1 \\
        --evaluation\_strategy 'no' \\
        --save\_strategy 'steps' \\
        --save\_steps 1200 \\
        --save\_total\_limit 5 \\
        --learning\_rate 2e-5 \\
        --weight\_decay 0. \\
        --warmup\_ratio 0.03 \\
        --lr\_scheduler\_type cosine \\
        --logging\_steps 1 \\
        --fsdp 'full\_shard auto\_wrap' \\
        --fsdp\_transformer\_layer\_cls\_to\_wrap 'LlamaDecoderLayer' \\
        --tf32 True \\
        --model\_max\_length 4096 \\
        --gradient\_checkpointing True

相关项目
----

-   Llama2
-   soulteary/docker-llama2-chat

项目协议
----

Apache-2.0 license

微信交流群
-----
