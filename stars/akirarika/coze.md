---
project: coze
stars: 6
description: 🐙 在 JavaScript 中使用 Coze（Coze 是字节跳动的 AI 应用商店）
url: https://github.com/akirarika/coze
---

Coze
====

Coze 是字节跳动的 AI 应用商店，用户可以在上面免费使用各种大语言模型，并使用别人分享的模型。

Coze 也提供了以 API 形式 的调用，开发者可以免费调用。这个库是对 API 的封装。

安装
--

bun i node-coze # or npm i node-coze

初始化
---

const coze \= createCoze({
    accessToken: "你的 access token"
});

使用
--

const result \= await coze.chat({
    bot\_id: "\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*",
    user: "your\_user\_id",
    query: "hello world"
});

if (!result.success) throw new Error(result.msg);

console.log("原始响应", result);
console.log("获取消息", result.getMessages());
console.log("获取回复", result.getAnswers());
console.log("获取最后一条回复", result.getLastAnswer());

使用国际站
-----

Coze 有面向海外用户的站点，可以使用 ChatGPT 等模型。我们可以在初始化时传入 `baseUrl` 选项来使用国际站：

const coze \= createCoze({
    accessToken: "你的 access token",
    baseUrl: "https://api.coze.com"
});
