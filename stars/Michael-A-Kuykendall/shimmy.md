---
project: shimmy
stars: 3309
description: ⚡ Python-free Rust inference server — OpenAI-API compatible. GGUF + SafeTensors, hot model swap, auto-discovery, single binary. FREE now, FREE forever.
url: https://github.com/Michael-A-Kuykendall/shimmy
---

The Lightweight OpenAI API Server
=================================

### 🔒 Local Inference Without Dependencies 🚀

**Shimmy will be free forever.** No asterisks. No "free for now." No pivot to paid.

### 💝 Support Shimmy's Growth

🚀 **If Shimmy helps you, consider sponsoring — 100% of support goes to keeping it free forever.**

-   **$5/month**: Coffee tier ☕ - Eternal gratitude + sponsor badge
-   **$25/month**: Bug prioritizer 🐛 - Priority support + name in SPONSORS.md
-   **$100/month**: Corporate backer 🏢 - Logo placement + monthly office hours
-   **$500/month**: Infrastructure partner 🚀 - Direct support + roadmap input

**🎯 Become a Sponsor** | See our amazing sponsors 🙏

* * *

Drop-in OpenAI API Replacement for Local LLMs
---------------------------------------------

Shimmy is a **4.8MB single-binary** that provides **100% OpenAI-compatible endpoints** for GGUF models. Point your existing AI tools to Shimmy and they just work — locally, privately, and free.

Developer Tools
---------------

Whether you're forking Shimmy or integrating it as a service, we provide complete documentation and integration templates.

### Try it in 30 seconds

# 1) Install + run
cargo install shimmy --features huggingface
shimmy serve &

# 2) See models and pick one
shimmy list

# 3) Smoke test the OpenAI API
curl -s http://127.0.0.1:11435/v1/chat/completions \\
  -H 'Content-Type: application/json' \\
  -d '{
        "model":"REPLACE\_WITH\_MODEL\_FROM\_list",
        "messages":\[{"role":"user","content":"Say hi in 5 words."}\],
        "max\_tokens":32
      }' | jq -r '.choices\[0\].message.content'

🚀 Compatible with OpenAI SDKs and Tools
----------------------------------------

**No code changes needed** - just change the API endpoint:

-   **Any OpenAI client**: Python, Node.js, curl, etc.
-   **Development applications**: Compatible with standard SDKs
-   **VSCode Extensions**: Point to `http://localhost:11435`
-   **Cursor Editor**: Built-in OpenAI compatibility
-   **Continue.dev**: Drop-in model provider

### Use with OpenAI SDKs

-   Node.js (openai v4)

import OpenAI from "openai";

const openai \= new OpenAI({
  baseURL: "http://127.0.0.1:11435/v1",
  apiKey: "sk-local", // placeholder, Shimmy ignores it
});

const resp \= await openai.chat.completions.create({
  model: "REPLACE\_WITH\_MODEL",
  messages: \[{ role: "user", content: "Say hi in 5 words." }\],
  max\_tokens: 32,
});

console.log(resp.choices\[0\].message?.content);

-   Python (openai>=1.0.0)

from openai import OpenAI

client \= OpenAI(base\_url\="http://127.0.0.1:11435/v1", api\_key\="sk-local")

resp \= client.chat.completions.create(
    model\="REPLACE\_WITH\_MODEL",
    messages\=\[{"role": "user", "content": "Say hi in 5 words."}\],
    max\_tokens\=32,
)

print(resp.choices\[0\].message.content)

⚡ Zero Configuration Required
-----------------------------

-   **Automatically finds models** from Hugging Face cache, Ollama, local dirs
-   **Auto-allocates ports** to avoid conflicts
-   **Auto-detects LoRA adapters** for specialized models
-   **Just works** - no config files, no setup wizards

🧠 Advanced MOE (Mixture of Experts) Support
--------------------------------------------

**Run 70B+ models on consumer hardware** with intelligent CPU/GPU hybrid processing:

-   **🔄 CPU MOE Offloading**: Automatically distribute model layers across CPU and GPU
-   **🧮 Intelligent Layer Placement**: Optimizes which layers run where for maximum performance
-   **💾 Memory Efficiency**: Fit larger models in limited VRAM by using system RAM strategically
-   **⚡ Hybrid Acceleration**: Get GPU speed where it matters most, CPU reliability everywhere else
-   **🎛️ Configurable**: `--cpu-moe` and `--n-cpu-moe` flags for fine control

# Enable MOE CPU offloading during installation
cargo install shimmy --features moe

# Run with MOE hybrid processing
shimmy serve --cpu-moe --n-cpu-moe 8

# Automatically balances: GPU layers (fast) + CPU layers (memory-efficient)

**Perfect for**: Large models (70B+), limited VRAM systems, cost-effective inference

🎯 Perfect for Local Development
--------------------------------

-   **Privacy**: Your code never leaves your machine
-   **Cost**: No API keys, no per-token billing
-   **Speed**: Local inference, sub-second responses
-   **Reliability**: No rate limits, no downtime

Quick Start (30 seconds)
------------------------

### Installation

#### **🪟 Windows**

# RECOMMENDED: Use pre-built binary (no build dependencies required)
curl -L https://github.com/Michael-A-Kuykendall/shimmy/releases/latest/download/shimmy.exe -o shimmy.exe

# OR: Install from source with MOE support
# First install build dependencies:
winget install LLVM.LLVM
# Then install shimmy with MOE:
cargo install shimmy --features moe

# For CUDA + MOE hybrid processing:
cargo install shimmy --features llama-cuda,moe

> **⚠️ Windows Notes**:
> 
> -   **Pre-built binary recommended** to avoid build dependency issues
> -   **MSVC compatibility**: Uses `shimmy-llama-cpp-2` packages for better Windows support
> -   If Windows Defender flags the binary, add an exclusion or use `cargo install`
> -   For `cargo install`: Install LLVM first to resolve `libclang.dll` errors

#### **🍎 macOS / 🐧 Linux**

# Install from crates.io
cargo install shimmy --features huggingface

### GPU Acceleration

Shimmy supports multiple GPU backends for accelerated inference:

#### **🖥️ Available Backends**

Backend

Hardware

Installation

**CUDA**

NVIDIA GPUs

`cargo install shimmy --features llama-cuda`

**CUDA + MOE**

NVIDIA GPUs + CPU

`cargo install shimmy --features llama-cuda,moe`

**Vulkan**

Cross-platform GPUs

`cargo install shimmy --features llama-vulkan`

**OpenCL**

AMD/Intel/Others

`cargo install shimmy --features llama-opencl`

**MLX**

Apple Silicon

`cargo install shimmy --features mlx`

**MOE Hybrid**

Any GPU + CPU

`cargo install shimmy --features moe`

**All Features**

Everything

`cargo install shimmy --features gpu,moe`

#### **🔍 Check GPU Support**

# Show detected GPU backends
shimmy gpu-info

#### **⚡ Usage Notes**

-   GPU backends are **automatically detected** at runtime
-   Falls back to CPU if GPU is unavailable
-   Multiple backends can be compiled in, best one selected automatically
-   Use `--gpu-backend <backend>` to force specific backend

### Get Models

Shimmy auto-discovers models from:

-   **Hugging Face cache**: `~/.cache/huggingface/hub/`
-   **Ollama models**: `~/.ollama/models/`
-   **Local directory**: `./models/`
-   **Environment**: `SHIMMY_BASE_GGUF=path/to/model.gguf`

# Download models that work out of the box
huggingface-cli download microsoft/Phi-3-mini-4k-instruct-gguf --local-dir ./models/
huggingface-cli download bartowski/Llama-3.2-1B-Instruct-GGUF --local-dir ./models/

### Start Server

# Auto-allocates port to avoid conflicts
shimmy serve

# Or use manual port
shimmy serve --bind 127.0.0.1:11435

Point your development tools to the displayed port — VSCode Copilot, Cursor, Continue.dev all work instantly.

📦 Download & Install
---------------------

### Package Managers

-   **Rust**: `cargo install shimmy --features moe` _(recommended)_
-   **Rust (basic)**: `cargo install shimmy`
-   **VS Code**: Shimmy Extension
-   **Windows MSVC**: Uses `shimmy-llama-cpp-2` packages for better compatibility
-   **npm**: `npm install -g shimmy-js` _(planned)_
-   **Python**: `pip install shimmy` _(planned)_

### Direct Downloads

-   **GitHub Releases**: Latest binaries
-   **Docker**: `docker pull shimmy/shimmy:latest` _(coming soon)_

### 🍎 macOS Support

**Full compatibility confirmed!** Shimmy works flawlessly on macOS with Metal GPU acceleration.

# Install dependencies
brew install cmake rust

# Install shimmy
cargo install shimmy

**✅ Verified working:**

-   Intel and Apple Silicon Macs
-   Metal GPU acceleration (automatic)
-   MLX native acceleration for Apple Silicon
-   Xcode 17+ compatibility
-   All LoRA adapter features

Integration Examples
--------------------

### VSCode Copilot

{
  "github.copilot.advanced": {
    "serverUrl": "http://localhost:11435"
  }
}

### Continue.dev

{
  "models": \[{
    "title": "Local Shimmy",
    "provider": "openai",
    "model": "your-model-name",
    "apiBase": "http://localhost:11435/v1"
  }\]
}

### Cursor IDE

Works out of the box - just point to `http://localhost:11435/v1`

Why Shimmy Will Always Be Free
------------------------------

I built Shimmy to retain privacy-first control on my AI development and keep things local and lean.

**This is my commitment**: Shimmy stays MIT licensed, forever. If you want to support development, sponsor it. If you don't, just build something cool with it.

> 💡 **Shimmy saves you time and money. If it's useful, consider sponsoring for $5/month — less than your Netflix subscription, infinitely more useful for developers.**

API Reference
-------------

### Endpoints

-   `GET /health` - Health check
-   `POST /v1/chat/completions` - OpenAI-compatible chat
-   `GET /v1/models` - List available models
-   `POST /api/generate` - Shimmy native API
-   `GET /ws/generate` - WebSocket streaming

### CLI Commands

shimmy serve                    # Start server (auto port allocation)
shimmy serve --bind 127.0.0.1:8080  # Manual port binding
shimmy serve --cpu-moe --n-cpu-moe 8  # Enable MOE CPU offloading
shimmy list                     # Show available models (LLM-filtered)
shimmy discover                 # Refresh model discovery
shimmy generate --name X --prompt "Hi"  # Test generation
shimmy probe model-name         # Verify model loads
shimmy gpu-info                 # Show GPU backend status

Technical Architecture
----------------------

-   **Rust + Tokio**: Memory-safe, async performance
-   **llama.cpp backend**: Industry-standard GGUF inference
-   **OpenAI API compatibility**: Drop-in replacement
-   **Dynamic port management**: Zero conflicts, auto-allocation
-   **Zero-config auto-discovery**: Just works™

### 🚀 Advanced Features

-   **🧠 MOE CPU Offloading**: Hybrid GPU/CPU processing for large models (70B+)
-   **🎯 Smart Model Filtering**: Automatically excludes non-language models (Stable Diffusion, Whisper, CLIP)
-   **🛡️ 6-Gate Release Validation**: Constitutional quality limits ensure reliability
-   **⚡ Smart Model Preloading**: Background loading with usage tracking for instant model switching
-   **💾 Response Caching**: LRU + TTL cache delivering 20-40% performance gains on repeat queries
-   **🚀 Integration Templates**: One-command deployment for Docker, Kubernetes, Railway, Fly.io, FastAPI, Express
-   **🔄 Request Routing**: Multi-instance support with health checking and load balancing
-   **📊 Advanced Observability**: Real-time metrics with self-optimization and Prometheus integration
-   **🔗 RustChain Integration**: Universal workflow transpilation with workflow orchestration

Community & Support
-------------------

-   **🐛 Bug Reports**: GitHub Issues
-   **💬 Discussions**: GitHub Discussions
-   **📖 Documentation**: docs/ • Engineering Methodology • OpenAI Compatibility Matrix • Benchmarks (Reproducible)
-   **💝 Sponsorship**: GitHub Sponsors

### Star History

### 🚀 Momentum Snapshot

📦 **Sub-5MB single binary** (142x smaller than Ollama) 🌟 **stars and climbing fast** ⏱ **<1s startup** 🦀 **100% Rust, no Python**

### 📰 As Featured On

🔥 **Hacker News** • **Front Page Again** • **IPE Newsletter**

**Companies**: Need invoicing? Email michaelallenkuykendall@gmail.com

⚡ Performance Comparison
------------------------

Tool

Binary Size

Startup Time

Memory Usage

OpenAI API

**Shimmy**

**4.8MB**

**<100ms**

**50MB**

**100%**

Ollama

680MB

5-10s

200MB+

Partial

llama.cpp

89MB

1-2s

100MB

Via llama-server

Quality & Reliability
---------------------

Shimmy maintains high code quality through comprehensive testing:

-   **Comprehensive test suite** with property-based testing
-   **Automated CI/CD pipeline** with quality gates
-   **Runtime invariant checking** for critical operations
-   **Cross-platform compatibility testing**

### Development Testing

Run the complete test suite:

# Using cargo aliases
cargo test-quick           # Quick development tests

# Using Makefile  
make test                  # Full test suite
make test-quick            # Quick development tests

See our testing approach for technical details.

* * *

License & Philosophy
--------------------

MIT License - forever and always.

**Philosophy**: Infrastructure should be invisible. Shimmy is infrastructure.

**Testing Philosophy**: Reliability through comprehensive validation and property-based testing.

* * *

**Forever maintainer**: Michael A. Kuykendall **Promise**: This will never become a paid product **Mission**: Making local model inference simple and reliable
