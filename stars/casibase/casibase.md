---
project: casibase
stars: 3966
description: ⚡️AI Cloud OS: Open-source enterprise-level AI knowledge base and MCP (model-context-protocol)/A2A (agent-to-agent) management platform with admin UI, user management and Single-Sign-On⚡️, supports ChatGPT, Claude, Llama, Ollama, HuggingFace, etc., chat bot demo: https://ai.casibase.com, admin UI demo: https://ai-admin.casibase.com
url: https://github.com/casibase/casibase
---

📦⚡️ Casibase
=============

### AI Cloud OS: Open-source enterprise-level AI knowledge base and MCP (model-context-protocol)/A2A (agent-to-agent) management platform with admin UI, user management and Single-Sign-On⚡️, supports ChatGPT, Claude, Llama, Ollama, HuggingFace, etc.

Online Demo
-----------

### Read-only site (any modification operation will fail)

-   Chat bot: https://ai.casibase.com
-   Admin UI: https://ai-admin.casibase.com

### Writable site (original data will be restored for every 5 minutes)

-   Chat bot: https://demo.casibase.com
-   Admin UI: https://demo-admin.casibase.com

Documentation
-------------

https://casibase.org

Architecture
------------

Casibase contains 2 parts:

**Name**

**Description**

**Language**

Frontend

User interface for Casibase

JavaScript + React

Backend

Server-side logic and API for Casibase

Golang + Beego + Python + Flask + MySQL

Supported Models
----------------

**Language Model**

Model

Sub Type

Link

OpenAI

dall-e-3, gpt-3.5-turbo-0125, gpt-3.5-turbo, gpt-3.5-turbo-1106, gpt-3.5-turbo-instruct, gpt-3.5-turbo-16k-0613, gpt-3.5-turbo-16k, gpt-4-0125-preview, gpt-4-1106-preview, gpt-4-turbo-preview, gpt-4-vision-preview, gpt-4-1106-vision-preview, gpt-4, gpt-4-0613, gpt-4-32k, gpt-4-32k-0613, gpt-4o, gpt-4o-2024-05-13, gpt-4o-mini, gpt-4o-mini-2024-07-18

OpenAI

Claude

claude-2.0, claude-2.1, claude-instant-1.2, claude-3-sonnet-20240229, claude-3-opus-20240229, claude-3-haiku-20240307

Claude

Local

custom-model

Local Computer

DeepSeek

deepseek-chat, deepseek-reasoner

DeepSeek

Azure

dall-e-3, gpt-3.5-turbo-0125, gpt-3.5-turbo, gpt-3.5-turbo-1106, gpt-3.5-turbo-instruct, gpt-3.5-turbo-16k-0613, gpt-3.5-turbo-16k, gpt-4-0125-preview, gpt-4-1106-preview, gpt-4-turbo-preview, gpt-4-vision-preview, gpt-4-1106-vision-preview, gpt-4, gpt-4-0613, gpt-4-32k, gpt-4-32k-0613, gpt-4o, gpt-4o-2024-05-13, gpt-4o-mini, gpt-4o-mini-2024-07-18

Azure

Amazon Bedrock

claude, claude-instant, command, command-light, embed-english, embed-multilingual, jurassic-2-mid, jurassic-2-ultra, llama-2-chat-13b, llama-2-chat-70b, titan-text-lite, titan-text-express, titan-embeddings, titan-multimodal-embeddings

Amazon Bedrock

Qwen

qwen-long, qwen-turbo, qwen-plus, qwen-max, qwen-max-longcontext

Qwen

Gemini

gemini-pro, gemini-pro-vision

Gemini

Hugging Face

meta-llama/Llama-2-7b, tiiuae/falcon-180B, bigscience/bloom, gpt2, baichuan-inc/Baichuan2-13B-Chat, THUDM/chatglm2-6b

Hugging Face

Cohere

command-light, command

Cohere

iFlytek

spark-v1.5, spark-v2.0

iFlytek

ChatGLM

glm-3-turbo, glm-4, glm-4V

ChatGLM

MiniMax

abab5-chat

MiniMax

Ernie

ERNIE-Bot, ERNIE-Bot-turbo, BLOOMZ-7B, Llama-2

Ernie

Moonshot

moonshot-v1-8k, moonshot-v1-32k, moonshot-v1-128k

Moonshot

Baichuan

Baichuan2-Turbo, Baichuan3-Turbo, Baichuan4

Baichuan

Doubao

Doubao-lite-4k, Doubao-lite-32k, Doubao-lite-128k, Doubao-pro-4k, Doubao-pro-32k, Doubao-pro-128k

Doubao

StepFun

step-1-8k, step-1-32k, step-1-128k, sstep-1-256k, step-1-flash, step-2-16k

StepFun

Hunyuan

hunyuan-lite, hunyuan-standard, hunyuan-standard-256K, hunyuan-pro, hunyuan-code, hunyuan-role, hunyuan-turbo

Hunyuan

Mistral

mistral-large-latest, pixtral-large-latest, mistral-small-latest, codestral-latest, ministral-8b-latest, ministral-3b-latest, pixtral-12b, mistral-nemo, open-mistral-7b, open-mixtral-8x7b, open-mixtral-8x22b

Mistral

OpenRouter

google/palm-2-codechat-bison, google/palm-2-chat-bison, openai/gpt-3.5-turbo, openai/gpt-3.5-turbo-16k, openai/gpt-4, openai/gpt-4-32k, anthropic/claude-2, anthropic/claude-instant-v1, meta-llama/llama-2-13b-chat, meta-llama/llama-2-70b-chat, palm-2-codechat-bison, palm-2-chat-bison, gpt-3.5-turbo, gpt-3.5-turbo-16k, gpt-4, gpt-4-32k, claude-2, claude-instant-v1, llama-2-13b-chat, llama-2-70b-chat

OpenRouter

**Embedding Model**

Model

Sub Type

Link

OpenAI

text-embedding-ada-002, text-embedding-3-small, text-embedding-3-large

OpenAI

Local

custom-embedding

Local Computer

Azure

text-embedding-ada-002, text-embedding-3-small, text-embedding-3-large

Azure

Hugging Face

sentence-transformers/all-MiniLM-L6-v2

Hugging Face

Qwen

text-embedding-v1, text-embedding-v2, text-embedding-v3

Qwen

Cohere

embed-english-v2.0, embed-english-light-v2.0, embed-multilingual-v2.0, embed-english-v3.0

Cohere

Ernie

default

Ernie

MiniMax

embo-01

MiniMax

Hunyuan

hunyuan-embedding

Hunyuan

Jina

jina-embeddings-v2-base-zh, jina-embeddings-v2-base-en, jina-embeddings-v2-base-de, jina-embeddings-v2-base-code

Jina

Documentation
-------------

https://casibase.org

Install
-------

https://casibase.org/docs/basic/server-installation

How to contact?
---------------

Discord: https://discord.gg/5rPsrAzK7S

Contribute
----------

For Casibase, if you have any questions, you can give issues, or you can also directly start Pull Requests(but we recommend giving issues first to communicate with the community).

License
-------

Apache-2.0
