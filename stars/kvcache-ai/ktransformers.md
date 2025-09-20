---
project: ktransformers
stars: 15078
description: A Flexible Framework for Experiencing Cutting-edge LLM Inference Optimizations
url: https://github.com/kvcache-ai/ktransformers
---

### A Flexible Framework for Experiencing Cutting-edge LLM Inference Optimizations

**🌟 Show Cases | 🚀 Quick Start | 📃 Tutorial | 💬 Discussion | 🙋 FAQ**

🎉 Introduction
---------------

KTransformers, pronounced as Quick Transformers, is designed to enhance your 🤗 Transformers experience with advanced kernel optimizations and placement/parallelism strategies.  
  
KTransformers is a flexible, Python-centric framework designed with extensibility at its core. By implementing and injecting an optimized module with a single line of code, users gain access to a Transformers-compatible interface, RESTful APIs compliant with OpenAI and Ollama, and even a simplified ChatGPT-like web UI.  
  
Our vision for KTransformers is to serve as a flexible platform for experimenting with innovative LLM inference optimizations. Please let us know if you need any other features.

🔥 Updates
----------

-   **Sept 11, 2025**: Support Qwen3-Next. (Tutorial)
-   **Sept 05, 2025**: Support Kimi-K2-0905. (Tutorial)
-   **July 26, 2025**: Support SmallThinker and GLM4-MoE. (Tutorial)
-   **July 11, 2025**: Support Kimi-K2. (Tutorial)
-   **June 30, 2025**: Support 3-layer (GPU-CPU-Disk) prefix cache reuse.
-   **May 14, 2025**: Support Intel Arc GPU (Tutorial).
-   **Apr 29, 2025**: Support AMX-Int8、 AMX-BF16 and Qwen3MoE (Tutorial)

202504290023-4.mov

-   **Apr 9, 2025**: Experimental support for LLaMA 4 models (Tutorial).
-   **Apr 2, 2025**: Support Multi-concurrency. (Tutorial).

v0.2.4.mp4

-   **Mar 15, 2025**: Support ROCm on AMD GPU (Tutorial).
-   **Mar 5, 2025**: Support unsloth 1.58/2.51 bits weights and IQ1\_S/FP8 hybrid weights. Support 139K Longer Context for DeepSeek-V3 and R1 in 24GB VRAM.
-   **Feb 25, 2025**: Support FP8 GPU kernel for DeepSeek-V3 and R1; Longer Context.
-   **Feb 15, 2025**: Longer Context (from 4K to 8K for 24GB VRAM) & Slightly Faster Speed （+15%, up to 16 Tokens/s), update docs and online books.
-   **Feb 10, 2025**: Support Deepseek-R1 and V3 on single (24GB VRAM)/multi gpu and 382G DRAM, up to 3~28x speedup. For detailed show case and reproduction tutorial, see here.
-   **Aug 28, 2024**: Decrease DeepseekV2's required VRAM from 21G to 11G.
-   **Aug 15, 2024**: Update detailed tutorial for injection and multi-GPU.
-   **Aug 14, 2024**: Support llamfile as linear backend.
-   **Aug 12, 2024**: Support multiple GPU; Support new model: mixtral 8\*7B and 8\*22B; Support q2k, q3k, q5k dequant on gpu.
-   **Aug 9, 2024**: Support windows native.

🌟 Show Cases
-------------

### GPT-4/o1-level Local VSCode Copilot on a Desktop with only 24GB VRAM

v3.up.mov

-   **\[NEW!!!\] Local 671B DeepSeek-Coder-V3/R1:** Running its Q4\_K\_M version using only 14GB VRAM and 382GB DRAM(Tutorial).
    
    -   Prefill Speed (tokens/s):
        -   KTransformers: 54.21 (32 cores) → 74.362 (dual-socket, 2×32 cores) → 255.26 (optimized AMX-based MoE kernel, V0.3 only) → 286.55 (selectively using 6 experts, V0.3 only)
        -   Compared to 10.31 tokens/s in llama.cpp with 2×32 cores, achieving up to **27.79× speedup**.
    -   Decode Speed (tokens/s):
        -   KTransformers: 8.73 (32 cores) → 11.26 (dual-socket, 2×32 cores) → 13.69 (selectively using 6 experts, V0.3 only)
        -   Compared to 4.51 tokens/s in llama.cpp with 2×32 cores, achieving up to **3.03× speedup**.
    -   Upcoming Open Source Release:
        -   AMX optimizations and selective expert activation will be open-sourced in V0.3.
        -   Currently available only in preview binary distribution, which can be downloaded here.
-   **Local 236B DeepSeek-Coder-V2:** Running its Q4\_K\_M version using only 21GB VRAM and 136GB DRAM, attainable on a local desktop machine, which scores even better than GPT4-0613 in BigCodeBench.
    

-   **Faster Speed:** Achieving 126 tokens/s for 2K prompt prefill and 13.6 tokens/s for generation through MoE offloading and injecting advanced kernels from Llamafile and Marlin.
-   **VSCode Integration:** Wrapped into an OpenAI and Ollama compatible API for seamless integration as a backend for Tabby and various other frontends.

ktransformers-tabby.mp4

**More advanced features will coming soon, so stay tuned!**

🚀 Quick Start
--------------

Getting started with KTransformers is simple! Follow the steps below to set up and start using it.

we have already supported vendors:

-   Metax
-   Sanechips (ZhuFeng V1.0)
-   Intel
-   Ascend
-   Kunpeng
-   AMD

### 📥 Installation

To install KTransformers, follow the official Installation Guide.

📃 Brief Injection Tutorial
---------------------------

At the heart of KTransformers is a user-friendly, template-based injection framework. This allows researchers to easily replace original torch modules with optimized variants. It also simplifies the process of combining multiple optimizations, allowing the exploration of their synergistic effects.  

Given that vLLM already serves as a great framework for large-scale deployment optimizations, KTransformers is particularly focused on local deployments that are constrained by limited resources. We pay special attention to heterogeneous computing opportunities, such as GPU/CPU offloading of quantized models. For example, we support the efficient Llamafile and Marlin kernels for CPU and GPU, respectively. More details can be found here.

### Example Usage

To utilize the provided kernels, users only need to create a YAML-based injection template and add the call to \`optimize\_and\_load\_gguf\` before using the Transformers model.

with torch.device("meta"):
    model \= AutoModelForCausalLM.from\_config(config, trust\_remote\_code\=True)
optimize\_and\_load\_gguf(model, optimize\_config\_path, gguf\_path, config)
...
generated \= prefill\_and\_generate(model, tokenizer, input\_tensor.cuda(), max\_new\_tokens\=1000)

In this example, the AutoModel is first initialized on the meta device to avoid occupying any memory resources. Then, `optimize_and_load_gguf` iterates through all sub-modules of the model, matches rules specified in your YAML rule file, and replaces them with advanced modules as specified.

After injection, the original `generate` interface is available, but we also provide a compatible `prefill_and_generate` method, which enables further optimizations like CUDAGraph to improve generation speed.

### How to custom your model

A detailed tutorial of the injection and multi-GPU using DeepSeek-V2 as an example is given here.

Below is an example of a YAML template for replacing all original Linear modules with Marlin, an advanced 4-bit quantization kernel.

\- match:
    name: "^model\\\\.layers\\\\..\*$"  # regular expression 
    class: torch.nn.Linear  # only match modules matching name and class simultaneously
  replace:
    class: ktransformers.operators.linear.KTransformerLinear  # optimized Kernel on quantized data types
    device: "cpu"   # which devices to load this module when initializing
    kwargs:
      generate\_device: "cuda"
      generate\_linear\_type: "QuantizedLinearMarlin"

Each rule in the YAML file has two parts: `match` and `replace`. The `match` part specifies which module should be replaced, and the `replace` part specifies the module to be injected into the model along with the initialization keywords.

You can find example rule templates for optimizing DeepSeek-V2 and Qwen2-57B-A14, two SOTA MoE models, in the ktransformers/optimize/optimize\_rules directory. These templates are used to power the `local_chat.py` demo.

If you are interested in our design principles and the implementation of the injection framework, please refer to the design document.

Acknowledgment and Contributors
-------------------------------

The development of KTransformers is based on the flexible and versatile framework provided by Transformers. We also benefit from advanced kernels such as GGUF/GGML, Llamafile, Marlin, sglang and flashinfer. We are planning to contribute back to the community by upstreaming our modifications.

KTransformers is actively maintained and developed by contributors from the MADSys group at Tsinghua University and members from Approaching.AI. We welcome new contributors to join us in making KTransformers faster and easier to use.

Discussion
----------

If you have any questions, feel free to open an issue. Alternatively, you can join our WeChat group for further discussion. QR Code: WeChat Group

🙋 FAQ
------

Some common questions are answered in the FAQ.
