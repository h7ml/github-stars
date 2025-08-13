---
project: llm-api-for-next-chat
stars: 7
description: 逆向工程整合多家語言模型並搭配NextChat的Web聊天介面，支援多種不同的聊天機器人模型部分，如ChatGPT、 Llama、DeepSeek等 💬
url: https://github.com/MayGrass/llm-api-for-next-chat
---

llm-api-for-next-chat
=====================

一個專為開源聊天前端 NextChat 設計的後端 API。  
可將多個第三方聊天平台整合為統一的 LLM 服務，讓 NextChat 前端可直接連接並進行對話。

> ⚠️ **免責聲明**  
> 本專案為第三方逆向工程，僅供學術研究與自我學習。與 NextChat 官方無任何直接關聯，請勿用於商業用途。  
> 由於逆向來源的協議與接口可能隨時變動，因此本專案的功能不保證穩定可用，請自行評估風險。  
> 使用本專案造成的任何法律責任與損失，請使用者自行承擔。

目前支援的模型來源網站
-----------

-   🌐 ChatGPT Web
-   🤗 HuggingChat
-   🦾 TheB.AI
-   🔍 DeepSeek（暫時失效）

一鍵部署（Docker Compose）
--------------------

請直接使用 docker compose 快速啟動：

git clone https://github.com/MayGrass/llm-api-for-next-chat.git
cd llm-api-for-next-chat
cp .env.example .env
# 編輯 .env，填入各來源平台的金鑰或token
docker compose up -d

-   **NextChat 前端**：http://localhost:3030
-   **llm-api-for-next-chat 後端**：http://localhost:5000
    
    > 後端網址已經在 docker compose 設定好，通常無需額外調整
    

與 NextChat 串接方式
---------------

1.  使用本專案預設的 docker compose 同時啟動 NextChat 前端與本後端。
2.  前端已預設連接本專案後端，無需再手動設定 API 端點。
3.  開啟 http://localhost:3030 ，即可直接開始對話。

* * *

參考專案 / References
-----------------

本專案開發過程中參考了以下開源專案，在此致謝：

-   xtekky/deepseek4free
-   SreejanPersonal/Hugging-Chat-Reverse-Engineered-API
-   SreejanPersonal/Claude-3-Opus-Free-Reverse-Engineered-API
-   Ink-Osier/PandoraToV1Api
