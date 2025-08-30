---
project: Grok-Mirror
stars: 682
description: 🚀 一键部署个人的 Grok 镜像站
url: https://github.com/dairoot/Grok-Mirror
---

Grok Mirror
===========

Grok Mirror 后台是一个 Grok 镜像站，允许多账号共享管理。实现多人同时使用 Grok 服务。

特点
--

-   提供与官网同等的极致体验。
-   提供 聊天 API `/v1/chat/completions` (格式同 Openai)
-   用户无需翻墙，便可轻松访问并使用 Grok 官方网站的所有功能。
-   通过在 `Mirror` 后台录入 `Sso Token`，让用户可以轻松使用 Grok 服务。

在线体验
----

https://grok.dairoot.cn

部署
--

打开命令行终端，执行以下命令

docker run --rm -p 50005:8080 \\
-v grok\_gateway\_db:/app/.cache\_data \\
dairoot/grok-gateway:latest

访问 `http://127.0.0.1:50005` 或访问 `http://外网ip:50005`

配置域名，请点击查看 完整部署流程

环境变量
----

分类

变量名

类型

默认值

描述

API 相关

`ADMIN_PASSWORD`

`String`

`None`

管理后台访问密码

`AUTHORIZATION`

`String`

`None`

用于轮询 多账号 SsoToken 列表，的API访问密钥

`ENABLE_MIRROR_API`

`Boolean`

`true`

是否开启 API 访问

`MIRROR_API_PREFIX`

`String`

`None`

API 访问前缀，建议配置

`API_HATD`

`Boolean`

`true`

API 开启临时聊天（不保存聊天记录）

系统变量

`PROXY_URL_POOL`

`String`

`None`

代理池链接，多个代理用逗号分隔  
`http://username:password@ip:port,`  
`socks5://username:password@ip:port,`  
`socks5h://username:password@ip:port`

`HOST`

`String`

`None`

设置服务的域名地址，用于api 图片显示  
`https://example.com`

`GOOGLEADS`

`String`

`None`

Google Adsense 广告代码

聊天 API 接口
---------

避免滥用限制每日200次

POST: /v1/chat/completions

-   请求头:

字段

类型

默认值

必填

描述

`Authorization`

`string`

`None`

`是`

`Bearer ${ AUTHORIZATION }` 或  
`Bearer ${`Sso Token`}`  
  
推荐使用环境变量中的 AUTHORIZATION，自动轮询 token

-   请求参数:

参数名

类型

是否必须

描述

model

string

是

模型名称  
`grok-3` `grok-3-thinking`  
`grok-3-deepsearch` `grok-3-deepersearch`

messages

array

是

消息内容

stream

boolean

否

是否开启流式返回

聊天接口请求示例：

export Authorization=GrokToken 或者 环境变量的Authorization
export yourUrl=http://127.0.0.1:50005


curl --location "${yourUrl}/v1/chat/completions" \\
--header 'Content-Type: application/json' \\
--header "Authorization: Bearer ${Authorization}" \\
--data '{
     "stream": true,
     "model": "grok-2",
     "messages": \[{"role": "user", "content": "你好呀!"}\]
   }'

更多 API 请点击查看：高阶玩法

加入群聊
----

Telegram

捐赠
--

Buy Me a Coffee

Star History
------------
