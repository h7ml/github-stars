---
project: Veloera
stars: 1067
description: null
url: https://github.com/Veloera/Veloera
---

Veloera
=======

优秀的 AI API 网关系统

原汁原味的 New API 体验, 对界面无大改动, 遵循 GPL 3.0 协议, 无商用限制, 承诺不变质.  
添加极多原版不计划添加的特性. 以下只是部分.

Important

我们近期更新了许可证, 查看整个 README 以了解详情

特性
--

-   支持以 `,` 分割的单渠道多 Key, 随机选取.
-   支持礼品码, 全局每用户一次, 可控制总使用次数
-   原生支持 /hf/v1 接口
-   支持正则表达式屏蔽词
-   渠道 Key 不再加密, 发送到前端显示
-   日志支持刷新
-   日志显示渠道名
-   更新加载样式
-   当没有聊天链接可用时, 不显示聊天按钮
-   空回复不计费
-   在日志表增加总/输入/输出 Tokens
-   还有更多...

迁移
--

本程序基于 new-api 二开, 数据库结构基本兼容, 会自动运行迁移.  
其他类似程序不保证支持, 后续有计划做手动迁移指南.

### new-api

除了使用 SQLite, 均可无缝迁移.  
对于 SQLite, 建议将 `one-api.db` 重命名为 `veloera.db`, 系统会尝试自动处理, 但未经过测试.

部署
--

Tip

最新版 Docker 镜像：`ghcr.io/veloera/veloera:latest`

### docker-compose

1.  克隆此仓库

git clone https://github.com/veloera/veloera.git
cd veloera

1.  修改配置文件

nano docker-compose.yml

1.  启动服务

docker-compose up -d

环境变量
----

-   `GENERATE_DEFAULT_TOKEN`：是否为新注册用户生成初始令牌，默认为 `false`
-   `STREAMING_TIMEOUT`：流式回复超时时间，默认 60 秒
-   `DIFY_DEBUG`：Dify 渠道是否输出工作流和节点信息，默认 `true`
-   `FORCE_STREAM_OPTION`：是否覆盖客户端 stream\_options 参数，默认 `true`
-   `GET_MEDIA_TOKEN`：是否统计图片 token，默认 `true`
-   `GET_MEDIA_TOKEN_NOT_STREAM`：非流情况下是否统计图片 token，默认 `true`
-   `UPDATE_TASK`：是否更新异步任务（Midjourney、Suno），默认 `true`
-   `COHERE_SAFETY_SETTING`：Cohere 模型安全设置，可选值为 `NONE`, `CONTEXTUAL`, `STRICT`，默认 `NONE`
-   `GEMINI_VISION_MAX_IMAGE_NUM`：Gemini 模型最大图片数量，默认 `16`
-   `MAX_FILE_DOWNLOAD_MB`: 最大文件下载大小，单位 MB，默认 `20`
-   `CRYPTO_SECRET`：加密密钥，用于加密数据库内容
-   `AZURE_DEFAULT_API_VERSION`：Azure 渠道默认 API 版本，默认 `2024-12-01-preview`
-   `NOTIFICATION_LIMIT_DURATION_MINUTE`：通知限制持续时间，默认 `10`分钟
-   `NOTIFY_LIMIT_COUNT`：用户通知在指定持续时间内的最大数量，默认 `2`

赞助商
---

感谢这些厂商对 Veloera 的支持:

  
CDN acceleration and security protection for this project are sponsored by Tencent EdgeOne.  

成为赞助者:  

⚠️ 法律声明（Legal Notice）
---------------------

Tip

**TL;DR**

-   如果你是普通用户:  
    此更新没有任何影响. 我们会为您处理好合规.
-   如果你在运行二开版本:  
    这是一个重要更新, 如果您希望合规运行 `v0.2.27.1` 以上版本(不含), 则请仔细阅读以下更新.

**更新概要**  
若您以任何形式使用、修改或分发本项目，**除遵循 GPL v3 外，还需遵守以下补充条款**：

1.  **不得移除或遮盖**所有页面页脚或“关于”页面中的 `Powered by Veloera` 标识。
2.  **必须保留**项目根目录下的 `VELOERA_PROJ` 文件，且**不得修改内容**。
3.  **不得更改或移除** `/veloera` 路由及其功能行为。

> 本部分仅用于信息说明，不构成法律意见。如您对许可条款存在疑问或面临合规要求，强烈建议咨询法律专业人士。

自 `v0.3.27.2` 起，本项目更改为 **GPL v3 许可证**，并附加了额外使用条款。详见本文档下方“许可证”部分。

本项目基于 `new-api` 项目，原始许可证 _Apache License 2.0_ 已保留于 `new-api-stuffs/LICENSE.new-api`，截至 fork 时原项目未包含 NOTICE 文件，故无需保留。

截至 commit `c956fd3`（含该提交），项目仍遵循 **Apache 2.0 许可证**，附加条款**不适用**。

本声明仅用于信息说明，**不构成法律建议**。如有法律合规方面疑问，请咨询专业律师。

许可证
---

本项目自版本 `v0.3.27.2` 起，采用 **GNU 通用公共许可证第 3 版（GPL v3）** 授权，并附加以下补充条款：

### 附加条款（Additional Terms）：

除非事先获得书面授权，您在使用、修改、分发本项目时，**必须同时遵守以下附加要求**：

1.  **不得移除或遮盖**所有页面页脚或“关于”页面中的 `Powered by Veloera` 徽标或文字标识。
2.  **必须保留**项目根目录下的 `VELOERA_PROJ` 文件，且不得修改其内容。
3.  **必须保留**并不得修改 `/veloera` 路由路径及其对应的页面行为。

这些附加条款依照 GPL v3 第 7 节的规定添加，并构成本项目许可证的组成部分。

截至 commit `c956fd3`（含），本项目代码仍遵循 Apache License 2.0，附加条款不适用。详情请参阅历史版本与 LICENSE 文件。

> ⚠️ 本声明不构成法律建议。如您对许可证条款有任何疑问，请咨询专业法律顾问。

🌟 Star History
---------------
