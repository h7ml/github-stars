---
project: shimmy
stars: 2739
description: ⚡ Python-free Rust inference server — OpenAI-API compatible. GGUF + SafeTensors, hot model swap, auto-discovery, single binary. FREE now, FREE forever.
url: https://github.com/Michael-A-Kuykendall/shimmy
---

The Privacy-First Alternative to Ollama
=======================================

### 🔒 Local AI Without the Lock-in 🚀

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

Whether you're forking Shimmy or integrating it as a service, we provide:

-   **Integration Templates**: Guidance for embedding Shimmy in your projects
-   **Development Specifications**: GitHub Spec-Kit methodology for planning features
-   **Architectural Guarantees**: Constitutional principles ensuring reliability and lightweight design
-   **Complete Documentation**: Everything you need to build on Shimmy

### GitHub Spec-Kit Integration

Shimmy includes GitHub Spec-Kit methodology for systematic development:

-   Systematic workflow: `/specify` → `/plan` → `/tasks` → implement
-   AI-assistant compatible (Claude Code, GitHub Copilot)
-   Professional specification templates
-   Built-in architectural validation

**Developer Guide →** • **Learn Spec-Kit →**

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

🚀 Works with Your Existing Tools
---------------------------------

**No code changes needed** - just change the API endpoint:

-   **VSCode Extensions**: Point to `http://localhost:11435`
-   **Cursor Editor**: Built-in OpenAI compatibility
-   **Continue.dev**: Drop-in model provider
-   **Any OpenAI client**: Python, Node.js, curl, etc.

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

-   **Auto-discovers models** from Hugging Face cache, Ollama, local dirs
-   **Auto-allocates ports** to avoid conflicts
-   **Auto-detects LoRA adapters** for specialized models
-   **Just works** - no config files, no setup wizards

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

# OR: Install from source (requires LLVM/Clang)
# First install build dependencies:
winget install LLVM.LLVM
# Then install shimmy:
cargo install shimmy --features huggingface

> **⚠️ Windows Notes**:
> 
> -   **Pre-built binary recommended** to avoid build dependency issues
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

**Vulkan**

Cross-platform GPUs

`cargo install shimmy --features llama-vulkan`

**OpenCL**

AMD/Intel/Others

`cargo install shimmy --features llama-opencl`

**MLX**

Apple Silicon

`cargo install shimmy --features mlx`

**All GPUs**

Everything

`cargo install shimmy --features gpu`

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

Point your AI tools to the displayed port — VSCode Copilot, Cursor, Continue.dev all work instantly.

📦 Download & Install
---------------------

### Package Managers

-   **Rust**: `cargo install shimmy`
-   **VS Code**: Shimmy Extension
-   **npm**: `npm install -g shimmy-js` _(coming soon)_
-   **Python**: `pip install shimmy` _(coming soon)_

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
shimmy list                     # Show available models  
shimmy discover                 # Refresh model discovery
shimmy generate --name X --prompt "Hi"  # Test generation
shimmy probe model-name         # Verify model loads

Technical Architecture
----------------------

-   **Rust + Tokio**: Memory-safe, async performance
-   **llama.cpp backend**: Industry-standard GGUF inference
-   **OpenAI API compatibility**: Drop-in replacement
-   **Dynamic port management**: Zero conflicts, auto-allocation
-   **Zero-config auto-discovery**: Just works™

### 🚀 Advanced Features

-   **Smart Model Preloading**: Background loading with usage tracking for instant model switching
-   **Response Caching**: LRU + TTL cache delivering 20-40% performance gains on repeat queries
-   **Integration Templates**: One-command deployment for Docker, Kubernetes, Railway, Fly.io, FastAPI, Express
-   **Request Routing**: Multi-instance support with health checking and load balancing
-   **Advanced Observability**: Real-time metrics with self-optimization and Prometheus integration

Community & Support
-------------------

-   **🐛 Bug Reports**: GitHub Issues
-   **💬 Discussions**: GitHub Discussions
-   **📖 Documentation**: docs/ • Engineering Methodology • OpenAI Compatibility Matrix • Benchmarks (Reproducible)
-   **💝 Sponsorship**: GitHub Sponsors

### Star History

### 🚀 Momentum Snapshot

📦 **Sub-5MB single binary** (142x smaller than Ollama)  
🌟 **stars and climbing fast**  
⏱ **<1s startup**  
🦀 **100% Rust, no Python**

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

None

Quality & Reliability
---------------------

Shimmy maintains high code quality through comprehensive testing:

-   **Comprehensive test suite** with property-based testing
-   **Automated CI/CD pipeline** with quality gates
-   **Runtime invariant checking** for critical operations
-   **Cross-platform compatibility testing**

See our testing approach for technical details.

* * *

License & Philosophy
--------------------

MIT License - forever and always.

**Philosophy**: Infrastructure should be invisible. Shimmy is infrastructure.

**Testing Philosophy**: Reliability through comprehensive validation and property-based testing.

* * *

**Forever maintainer**: Michael A. Kuykendall  
**Promise**: This will never become a paid product  
**Mission**: Making local AI development frictionless
