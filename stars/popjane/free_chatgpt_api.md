---
project: free_chatgpt_api
stars: 5492
description: 🔥 公益免费的ChatGPT API，Free ChatGPT API，GPT4 API，可直连，无需代理，使用标准 OpenAI APIKEY 格式访问 ChatGPT，可搭配ChatGPT-next-web、ChatGPT-Midjourney、Lobe-chat、Botgem、FastGPT、沉浸式翻译等项目使用
url: https://github.com/popjane/free_chatgpt_api
---

FREE-CHATGPT-API
================

通过标准的 OpenAI格式免费使用ChatGPT API

快速开始 · 使用方法 · 立即领取免费KEY · 付费极速API · 应用支持

Note

本项目当前API地址已更新为 `https://free.v36.cm` 请知晓！

Important

使用者必须在遵循 OpenAI 的使用条款以及**法律法规**的情况下使用，不得用于非法用途。 根据《生成式人工智能服务管理暂行办法》的要求，请勿对中国地区公众提供一切未经备案的生成式人工智能服务。 该项目API仅用于非商业性的学习、研究、科研测试等合法用途，不得用于任何违法违规用途以及商业用途，否则后果自负。

Tip

本项目仅供个人学习使用，不保证稳定性，且不提供任何技术支持。  
已经发现上百个机器号自动领取KEY批量跑API的行为，严重影响了正常用户的使用。当前限制RPM为96，超过将被CC拦截。  
gpt-4o-mini和gpt-3.5模型本身并不贵，如需高并发API请求，请支持付费API哦！

项目介绍
----

1.  完全免费使用以下勾选模型：
    -   gpt-4o-mini（速度一般，若要体验极速回复，可购买付费API）
    -   gpt-3.5-turbo-0125
    -   gpt-3.5-turbo-1106
    -   gpt-3.5-turbo
    -   gpt-3.5-turbo-16k
    -   net-gpt-3.5-turbo (可联网搜索模型-稳定性稍差)
    -   whisper-1
    -   dall-e-2
    -   text-开头系列模型，例如：text-davinci（免费版已取消text系列模型）
    -   gpt-4全系列（只定期限量开放）
    -   付费版API支持OpenAI所有模型，包括（联网、绘画、聊天、向量、图片分析、文件分析、GPTs等）
    -   付费版API支持Midjourney专业绘画、Suno音乐生成、PPT生成、多种视频模型。
2.  标准的OpenAI接口请求格式。
3.  支持流式响应输出。
4.  完美兼容各类开源的GPT项目/应用/软件。

免费使用
----

1.  首先 🚀 **前往领取免费APIKEY**、领取后请妥善保管你的APIKEY。
2.  复制免费API地址：`https://free.v36.cm`（无需代理，直接可用）。
3.  在支持的应用中绑定你的APIKEY+API地址(`BASE_URL`)，即可开始使用（可查看应用支持列表）。

根据用户量的增加，我们会相应提升服务质量，提供更优质的免费服务。在使用上遇到问题，可以在issues中提出，我们会尽快协助解决。

付费API
-----

Note

为了确保项目的可持续发展，我们意识到仅依赖公益性质的免费Key是难以长期维持的。注意：免费API不提供任何技术支持，如需稳定高并发的API请求请支持付费API。我们诚挚希望大家能够理解并支持这一决策。

🚀 **前往购买纯官转直连付费API**

付费APIKEY与免费APIKEY不通用，购买后需按卡密详情方法重新生成KEY使用。

### 付费API特点

1.  更低延迟、高性能、高可用、高并发、直连官方API（无逆向、无多层中转、非Azure），享受极致体验。
2.  支持OpenAI所有模型，包括（联网、绘画、聊天、训练、图片分析、GPTs等）目前已支持130+模型。
3.  gpt4价格仅为官网价格的2.8-3折之间，gpt-3.5系列模型为1.4-2折之间，白菜价格。
4.  定价策略透明公开，模型扣费倍率与官网同步（甚至更低），永不暗调倍率，无低价格却又高倍率陷阱。
5.  不限时间、按量计费、明细可查，每一笔消费都公开透明。
6.  API仅用于非商业性的学习、研究、科研测试等合法用途，不得用于任何违法违规用途，不得向中国公众提供任何生成式服务，否则后果自负。

常用应用支持
------

Note

理论上支持所有可以自定义API地址的GPT应用，以下是一些常用的应用。

所有应用的API地址（BaseUrl）为`https://free.v36.cm` 教程图片中的api地址前缀请更换为`https://free.v36.cm`

### 一、ChatGPT.好友插件

> 该插件为utools的一个插件，支持自定义模型、一键呼出，即用既走，超级面板，在pc任意位置均可快速发送消息。支持Ai聊天、绘画、语音对话、多api管理、多key绑定、角色独立聊天记录、一键查余额。桌面端的神器，但不支持移动端。
> 
> 是一个功能非常全面的ai聊天应用插件。
> 
> **查看应用**

绑定教程截图：

绑定成功后，鼠标右键ai列表，选择需要的模型即可。

### 二、开源应用Chatgpt-next-web（ChatGPT-Midjourney）

> 开源Chatgpt-next-web 这是一个开源web聊天工具，只支持聊天。
> 
> 开源ChatGPT-Midjourney 二开版本，支持Midjourney对话的开源应用。

绑定教程截图：

点击设置图标。找到自定义接口设置，配置如下：

### 三、Lobe-chat

> Lobe-chat 是一个开源的聊天应用，支持聊天、绘画、语音对话等。

绑定教程截图：

### 四、BotGem

> BotGem 非开源工具，支持PC和移动端，功能单一，只支持聊天，但多端适配。

绑定方法类似上方截图教程，填写免费API地址`https://free.v36.cm`+`apikey` 即可。

### 五、ChatBox

> ChatBox 支持桌面端APP版和web版，点开setting按钮配置即可。

绑定方法类似上方截图教程，填写免费API地址`https://free.v36.cm`+`apikey` 即可。

### 六、FastGPT

> FastGPT 支持知识库的聊天应用。

部署时参数host填写`https://free.v36.cm` 可以传入我们的`apikey` 即可

### 更多应用支持

待更新...

### OpenAi官方python库

> 在openai官方库开发时传入baseurl和apikey即可。
> 
> openai-python

以官网的`python`库为例：注意，需要传入`/v1/`后缀。并且openai库需升级到最新版，老版本传参格式不一样，具体参考官方py库文档。

import os
import openai

\# optional; defaults to \`os.environ\['OPENAI\_API\_KEY'\]\`
openai.api\_key \= "您的APIKEY"

\# all client options can be configured just like the \`OpenAI\` instantiation counterpart
openai.base\_url \= "https://free.v36.cm/v1/"
openai.default\_headers \= {"x-foo": "true"}

completion \= openai.chat.completions.create(
    model\="gpt-3.5-turbo",
    messages\=\[
        {
            "role": "user",
            "content": "Hello world!",
        },
    \],
)
print(completion.choices\[0\].message.content)

\# 正常会输出结果：Hello there! How can I assist you today ?

### OpenAi官方node库

> openai-node

以官网的`node`库为例：注意，需要传入/v1后缀。

const { Configuration, OpenAIApi } \= require("openai");

const configuration \= new Configuration({
  apiKey: "您的apikey",
  basePath: "https://free.v36.cm/v1"
});
const openai \= new OpenAIApi(configuration);

const chatCompletion \= await openai.createChatCompletion({
  model: "gpt-3.5-turbo",
  messages: \[{role: "user", content: "Hello world"}\],
});

console.log(chatCompletion.data.choices\[0\].message.content);

关联项目
----

OpenAI Plus充值
