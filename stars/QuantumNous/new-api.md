---
project: new-api
stars: 9594
description: AI模型接口管理与分发系统，支持将多种大模型转为统一格式调用，支持OpenAI、Claude等格式，可供个人或者企业内部管理与分发渠道使用，本项目基于One API二次开发。🍥 The next-generation LLM gateway and AI asset management system supports multiple languages.
url: https://github.com/QuantumNous/new-api
---

**中文** | English

New API
=======

🍥新一代大模型网关与AI资产管理系统

📝 项目说明
-------

Note

本项目为开源项目，在One API的基础上进行二次开发

Important

-   本项目仅供个人学习使用，不保证稳定性，且不提供任何技术支持。
-   使用者必须在遵循 OpenAI 的使用条款以及**法律法规**的情况下使用，不得用于非法用途。
-   根据《生成式人工智能服务管理暂行办法》的要求，请勿对中国地区公众提供一切未经备案的生成式人工智能服务。

📚 文档
-----

详细文档请访问我们的官方Wiki：https://docs.newapi.pro/

也可访问AI生成的DeepWiki:

✨ 主要特性
------

New API提供了丰富的功能，详细特性请参考特性说明：

1.  🎨 全新的UI界面
2.  🌍 多语言支持
3.  💰 支持在线充值功能（易支付）
4.  🔍 支持用key查询使用额度（配合neko-api-key-tool）
5.  🔄 兼容原版One API的数据库
6.  💵 支持模型按次数收费
7.  ⚖️ 支持渠道加权随机
8.  📈 数据看板（控制台）
9.  🔒 令牌分组、模型限制
10.  🤖 支持更多授权登陆方式（LinuxDO,Telegram、OIDC）
11.  🔄 支持Rerank模型（Cohere和Jina），接口文档
12.  ⚡ 支持OpenAI Realtime API（包括Azure渠道），接口文档
13.  ⚡ 支持Claude Messages 格式，接口文档
14.  支持使用路由/chat2link进入聊天界面
15.  🧠 支持通过模型名称后缀设置 reasoning effort：
    1.  OpenAI o系列模型
        -   添加后缀 `-high` 设置为 high reasoning effort (例如: `o3-mini-high`)
        -   添加后缀 `-medium` 设置为 medium reasoning effort (例如: `o3-mini-medium`)
        -   添加后缀 `-low` 设置为 low reasoning effort (例如: `o3-mini-low`)
    2.  Claude 思考模型
        -   添加后缀 `-thinking` 启用思考模式 (例如: `claude-3-7-sonnet-20250219-thinking`)
16.  🔄 思考转内容功能
17.  🔄 针对用户的模型限流功能
18.  💰 缓存计费支持，开启后可以在缓存命中时按照设定的比例计费：
    1.  在 `系统设置-运营设置` 中设置 `提示缓存倍率` 选项
    2.  在渠道中设置 `提示缓存倍率`，范围 0-1，例如设置为 0.5 表示缓存命中时按照 50% 计费
    3.  支持的渠道：
        -   OpenAI
        -   Azure
        -   DeepSeek
        -   Claude

模型支持
----

此版本支持多种模型，详情请参考接口文档-中继接口：

1.  第三方模型 **gpts** （gpt-4-gizmo-\*）
2.  第三方渠道Midjourney-Proxy(Plus)接口，接口文档
3.  第三方渠道Suno API接口，接口文档
4.  自定义渠道，支持填入完整调用地址
5.  Rerank模型（Cohere和Jina），接口文档
6.  Claude Messages 格式，接口文档
7.  Dify，当前仅支持chatflow

环境变量配置
------

详细配置说明请参考安装指南-环境变量配置：

-   `GENERATE_DEFAULT_TOKEN`：是否为新注册用户生成初始令牌，默认为 `false`
-   `STREAMING_TIMEOUT`：流式回复超时时间，默认120秒
-   `DIFY_DEBUG`：Dify渠道是否输出工作流和节点信息，默认 `true`
-   `FORCE_STREAM_OPTION`：是否覆盖客户端stream\_options参数，默认 `true`
-   `GET_MEDIA_TOKEN`：是否统计图片token，默认 `true`
-   `GET_MEDIA_TOKEN_NOT_STREAM`：非流情况下是否统计图片token，默认 `true`
-   `UPDATE_TASK`：是否更新异步任务（Midjourney、Suno），默认 `true`
-   `COHERE_SAFETY_SETTING`：Cohere模型安全设置，可选值为 `NONE`, `CONTEXTUAL`, `STRICT`，默认 `NONE`
-   `GEMINI_VISION_MAX_IMAGE_NUM`：Gemini模型最大图片数量，默认 `16`
-   `MAX_FILE_DOWNLOAD_MB`: 最大文件下载大小，单位MB，默认 `20`
-   `CRYPTO_SECRET`：加密密钥，用于加密数据库内容
-   `AZURE_DEFAULT_API_VERSION`：Azure渠道默认API版本，默认 `2025-04-01-preview`
-   `NOTIFICATION_LIMIT_DURATION_MINUTE`：通知限制持续时间，默认 `10`分钟
-   `NOTIFY_LIMIT_COUNT`：用户通知在指定持续时间内的最大数量，默认 `2`
-   `ERROR_LOG_ENABLED=true`: 是否记录并显示错误日志，默认`false`

部署
--

详细部署指南请参考安装指南-部署方式：

Tip

最新版Docker镜像：`calciumion/new-api:latest`

### 多机部署注意事项

-   必须设置环境变量 `SESSION_SECRET`，否则会导致多机部署时登录状态不一致
-   如果公用Redis，必须设置 `CRYPTO_SECRET`，否则会导致多机部署时Redis内容无法获取

### 部署要求

-   本地数据库（默认）：SQLite（Docker部署必须挂载`/data`目录）
-   远程数据库：MySQL版本 >= 5.7.8，PgSQL版本 >= 9.6

### 部署方式

#### 使用宝塔面板Docker功能部署

安装宝塔面板（**9.2.0版本**及以上），在应用商店中找到**New-API**安装即可。 图文教程

#### 使用Docker Compose部署（推荐）

# 下载项目
git clone https://github.com/Calcium-Ion/new-api.git
cd new-api
# 按需编辑docker-compose.yml
# 启动
docker-compose up -d

#### 直接使用Docker镜像

# 使用SQLite
docker run --name new-api -d --restart always -p 3000:3000 -e TZ=Asia/Shanghai -v /home/ubuntu/data/new-api:/data calciumion/new-api:latest

# 使用MySQL
docker run --name new-api -d --restart always -p 3000:3000 -e SQL\_DSN="root:123456@tcp(localhost:3306)/oneapi" -e TZ=Asia/Shanghai -v /home/ubuntu/data/new-api:/data calciumion/new-api:latest

渠道重试与缓存
-------

渠道重试功能已经实现，可以在`设置->运营设置->通用设置`设置重试次数，**建议开启缓存**功能。

### 缓存设置方法

1.  `REDIS_CONN_STRING`：设置Redis作为缓存
2.  `MEMORY_CACHE_ENABLED`：启用内存缓存（设置了Redis则无需手动设置）

接口文档
----

详细接口文档请参考接口文档：

-   聊天接口（Chat）
-   图像接口（Image）
-   重排序接口（Rerank）
-   实时对话接口（Realtime）
-   Claude聊天接口（messages）

相关项目
----

-   One API：原版项目
-   Midjourney-Proxy：Midjourney接口支持
-   chatnio：下一代AI一站式B/C端解决方案
-   neko-api-key-tool：用key查询使用额度

其他基于New API的项目：

-   new-api-horizon：New API高性能优化版

帮助支持
----

如有问题，请参考帮助支持：

-   社区交流
-   反馈问题
-   常见问题

🌟 Star History
---------------
