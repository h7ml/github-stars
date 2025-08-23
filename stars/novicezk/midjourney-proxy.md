---
project: midjourney-proxy
stars: 5131
description: 代理 MidJourney 的discord频道，实现api形式调用AI绘图
url: https://github.com/novicezk/midjourney-proxy
---

midjourney-proxy
================

English | 中文

代理 MidJourney 的discord频道，实现api形式调用AI绘图

主要功能
----

-   支持 Imagine 指令和相关动作
-   Imagine 时支持添加图片base64，作为垫图
-   支持 Blend(图片混合)、Describe(图生文) 指令
-   支持任务实时进度
-   支持中文prompt翻译，需配置百度翻译或gpt
-   prompt 敏感词预检测，支持覆盖调整
-   user-token 连接 wss，可以获取错误信息和完整功能
-   支持多账号配置，每个账号可设置对应的任务队列

**🚀 更多功能请查看 midjourney-proxy-plus**

> -   支持开源版的所有功能
> -   支持 Shorten(prompt分析) 指令
> -   支持焦点移动: Pan ⬅️ ➡️ ⬆️ ⬇️
> -   支持图片变焦: Zoom 🔍
> -   支持局部重绘: Vary (Region) 🖌
> -   支持几乎所有的关联按钮动作和🎛️ Remix模式
> -   支持获取图片的seed值
> -   账号池持久化，动态维护
> -   支持获取账号/info、/settings信息
> -   账号settings设置
> -   支持niji bot机器人
> -   支持InsightFace人脸替换机器人
> -   内嵌管理后台页面
> -   后台支持动态配置
> -   解决token频繁掉线问题
> -   支持弹窗自动验证功能
> -   支持违禁词Action needed to continue自动申诉
> -   支持最新的MidJourney V7 Alpha版本
> -   支持视频生成相关接口

使用前提
----

1.  注册并订阅 MidJourney，创建`自己的服务器和频道`，参考 https://docs.midjourney.com/docs/quick-start
2.  获取用户Token、服务器ID、频道ID：获取方式

快速启动
----

1.  `Railway`: 基于Railway平台，不需要自己的服务器: 部署方式；若Railway不能使用，可使用Zeabur启动
2.  `Zeabur`: 基于Zeabur平台，不需要自己的服务器: 部署方式
3.  `Docker`: 在服务器或本地使用Docker启动: 部署方式

本地开发
----

-   依赖java17和maven
-   更改配置项: 修改src/main/application.yml
-   项目运行: 启动ProxyApplication的main函数
-   更改代码后，构建镜像: Dockerfile取消VOLUME的注释，执行 `docker build . -t midjourney-proxy`

配置项
---

-   mj.accounts: 参考 账号池配置
-   mj.task-store.type: 任务存储方式，默认in\_memory(内存\\重启后丢失)，可选redis
-   mj.task-store.timeout: 任务存储过期时间，过期后删除，默认30天
-   mj.api-secret: 接口密钥，为空不启用鉴权；调用接口时需要加请求头 mj-api-secret
-   mj.translate-way: 中文prompt翻译成英文的方式，可选null(默认)、baidu、gpt
-   更多配置查看 配置项

相关文档
----

1.  API接口说明
2.  版本更新记录

注意事项
----

1.  作图频繁等行为，可能会触发midjourney账号警告，请谨慎使用
2.  常见问题及解决办法见 Wiki / FAQ
3.  感兴趣的朋友也欢迎加入交流群讨论一下，扫码进群名额已满，加管理员微信邀请进群，备注: mj加群

应用项目
----

依赖此项目且开源的，欢迎联系作者，加到此处展示

-   wechat-midjourney : 代理微信客户端，接入MidJourney，仅示例应用场景，不再更新
-   chatgpt-web-midjourney-proxy : chatgpt web, midjourney, gpts,tts, whisper 一套ui全搞定
-   chatnio : 下一代 AI 一站式 B/C 端解决方案, 集成精美 UI 和强大功能的聚合模型平台
-   new-api : 接入Midjourney Proxy的接口管理 & 分发系统
-   stable-diffusion-mobileui : SDUI，基于本接口和SD，可一键打包生成H5和小程序
-   MidJourney-Web : 🍎 Supercharged Experience For MidJourney On Web UI
-   midjourney-captcha-bot : 绕过Midjourney验证码

开放API
-----

提供非官方的MJ/SD开放API，添加管理员微信咨询，备注: api

其它
--

如果觉得这个项目对您有所帮助，请帮忙点个star
