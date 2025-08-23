---
project: nonebot2
stars: 6962
description: 跨平台 Python 异步聊天机器人框架 / Asynchronous multi-platform chatbot framework written in Python
url: https://github.com/nonebot/nonebot2
---

NoneBot
=======

_✨ 跨平台 Python 异步机器人框架 ✨_

  
  
  

文档 · 快速上手 · 文档打不开？

简介
--

NoneBot2 是一个现代、跨平台、可扩展的 Python 聊天机器人框架，它基于 Python 的类型注解和异步特性，能够为你的需求实现提供便捷灵活的支持。

特色
--

-   异步优先：基于 Python 的异步特性，即使是非常大量的消息，也能吞吐自如
    
-   易于开发：配合 NB-CLI 脚手架，代码编写上手简单，没有过多的冗余代码，可以让开发者专注于业务逻辑
    
-   生而可靠：100% 类型注解覆盖，配合编辑器的类型推导功能，能将绝大多数的 Bug 杜绝在编辑器中 (编辑器支持)
    
-   社区丰富：社区用户众多，直接和间接用户超过十万人，每天都有大量的活跃用户 (社区资源)
    
-   海纳百川：一个框架，支持多个聊天软件平台，可自定义通信协议
    
    协议名称
    
    状态
    
    注释
    
    OneBot（仓库，协议）
    
    ✅
    
    支持 QQ、TG、微信公众号、KOOK 等平台
    
    Telegram（仓库，协议）
    
    ✅
    
    飞书（仓库，协议）
    
    ✅
    
    GitHub（仓库，协议）
    
    ✅
    
    GitHub APP & OAuth APP
    
    QQ（仓库，协议）
    
    ✅
    
    QQ 官方接口调整较多
    
    Console（仓库）
    
    ✅
    
    控制台交互
    
    Red（仓库，协议）
    
    ✅
    
    QQNT 协议
    
    Satori（仓库，协议）
    
    ✅
    
    支持 Onebot、TG、飞书、微信公众号、Koishi 等
    
    Discord（仓库，协议）
    
    ✅
    
    Discord Bot 协议
    
    DoDo（仓库，协议）
    
    ✅
    
    DoDo Bot 协议
    
    Kritor（仓库，协议）
    
    ✅
    
    Kritor (OnebotX) 协议，QQNT 机器人接口标准
    
    Mirai（仓库，协议）
    
    ✅
    
    QQ 协议
    
    Milky（仓库，协议）
    
    ✅
    
    QQNT 机器人应用接口标准
    
    钉钉（仓库，协议）
    
    🤗
    
    寻找 Maintainer（暂不可用）
    
    开黑啦（仓库，协议）
    
    ↗️
    
    由社区贡献
    
    Ntchat（仓库）
    
    ↗️
    
    微信协议，由社区贡献
    
    MineCraft（仓库）
    
    ↗️
    
    由社区贡献
    
    Walle-Q（仓库）
    
    ↗️
    
    QQ 协议，由社区贡献
    
    Villa（仓库）
    
    ❌
    
    米游社大别野 Bot 协议，官方已下线
    
    Rocket.Chat（仓库，协议）
    
    ↗️
    
    Rocket.Chat Bot 协议，由社区贡献
    
    Tailchat（仓库，协议）
    
    ↗️
    
    Tailchat 开放平台 Bot 协议，由社区贡献
    
    Mail（仓库）
    
    ↗️
    
    邮件收发协议，由社区贡献
    
    黑盒语音（仓库，协议）
    
    ↗️
    
    黑盒语音机器人协议，由社区贡献
    
    微信公众平台（仓库，协议）
    
    ↗️
    
    微信公众平台协议，由社区贡献
    
    Gewechat（仓库，协议）
    
    ❌
    
    Gewechat 微信协议，Gewechat不再维护及可用
    
    EFChat（仓库，协议）
    
    ↗️
    
    恒五聊平台协议，由社区贡献
    
    VoceChat （仓库，协议）
    
    ↗️
    
    VoceChat 平台协议，由社区贡献
    
    B站直播间（仓库，Web API 协议，开放平台协议）
    
    ↗️
    
    B站直播间（Web API/开放平台）协议，由社区贡献
    
-   坚实后盾：支持多种 web 框架，可自定义替换、组合
    
    驱动框架
    
    类型
    
    FastAPI
    
    服务端
    
    Quart（异步 Flask）
    
    服务端
    
    aiohttp
    
    客户端
    
    httpx
    
    客户端
    
    websockets
    
    客户端
    

更多：概览

什么不是 NoneBot2
-------------

NoneBot2 不是某个平台或者协议的具体实现，它只负责和已有协议适配器通信，并处理接收到的事件。所以，“NoneBot 有 blabla 平台的 blabla 功能吗？”这种问题是与 NoneBot2 无关的。请在相应平台的功能文档中确认，或与相应平台的协议适配开发者联系。

NoneBot2 不是 NoneBot1 的替代品。事实上，它们都在被积极的维护着。但是，如果你想尝试一些新功能，或者想要支持更多的平台，可以考虑使用 NoneBot2。

> NoneBot2 和 NoneBot1 的区别，就像是 VisualStudio Code 和 VisualStudio 一样

即刻开始
----

完整文档可以在 这里 查看。

懒得看文档？下面是快速安装指南：

1.  安装 pipx
    
    python -m pip install --user pipx
    python -m pipx ensurepath
    
2.  安装脚手架
    
    pipx install nb-cli
    
3.  使用脚手架创建项目
    
    nb create
    
4.  运行项目
    
    nb run
    

社区资源
----

### 常见问题

-   常见问题解答(FAQ)
-   论坛(Discussion)

### 教程/实际项目/经验分享

-   awesome-nonebot

### 插件

此外，NoneBot2 还有丰富的官方以及第三方现成的插件供大家使用：

-   NoneBot-Plugin-Docs：离线文档至本地项目使用 (别再说文档打不开了！)
    
    在项目目录下执行：
    
    nb plugin install nonebot\_plugin\_docs
    
    或者尝试以下镜像：
    
    -   文档镜像(中国境内)
-   其他插件请查看 商店
    

许可证
---

`NoneBot` 采用 `MIT` 许可证进行开源

```
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

贡献
--

请参考 贡献指南

鸣谢
--

### 赞助者

感谢以下产品对 NoneBot 项目提供的赞助：

         

    

感谢以下赞助者对 NoneBot 项目提供的资金支持：

### 开发者

感谢以下开发者对 NoneBot2 作出的贡献：
