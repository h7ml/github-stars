---
project: HiveChat
stars: 1107
description: An AI chat bot for small and medium-sized teams, supporting models such as Deepseek, Open AI, Claude, and Gemini. 专为中小团队设计的 AI 聊天应用，支持 Deepseek、Open AI、Claude、Gemini 等模型。
url: https://github.com/HiveNexus/HiveChat
---

中文 ｜ English

专为中小团队设计的 AI 聊天应用，支持 Deepseek、Open AI、Claude、Gemini 等模型。

1\. 功能概览
--------

管理员一人配置，全团队轻松使用各种 AI 模型。

-   支持配置邮箱登录或企业微信、钉钉、飞书登录
    
-   支持分组管理用户
    
    -   针对分组用户设置不同可使用的模型
    -   针对分组用户可分别设置每月 Token 限额
-   支持配置 MCP 服务器（SSE 模式）
    
-   DeepSeek 思维链展示
    
-   LaTeX 和 Markdown 渲染
    
-   图像理解
    
-   AI 智能体
    
-   云端数据存储
    
-   支持的大模型服务商：
    
    -   Open AI
    -   Claude
    -   Gemini
    -   DeepSeek
    -   Moonshot(月之暗面)
    -   火山方舟（豆包）
    -   阿里百炼（千问）
    -   百度千帆
    -   腾讯混元
    -   智谱
    -   Open Router
    -   Grok
    -   Ollama
    -   硅基流动
-   同时支持自定义添加任意 Open AI 风格的服务商
    

### 普通用户端

登录账号，即可对话。

MCP 使用

### 管理后台

-   管理员配置 AI 大模型服务商
-   可手动添加用户，也可开启或关闭账号注册，适用于公司/学校/组织等小型团队
-   查看和管理全部用户

更多图片 用户管理，可以为用户设置分组，针对不同分组设置可见模型和 Token 限额 邮箱以及第三方登录 MCP 配置 搜索设置

2\. 在线演示
--------

注：以下为演示站，数据随时会被清空

-   Cloud 版：https://www.hivechat.net/
    
    -   可自行注册账号体验，支持多租户
-   私有部署用户端：https://chat.yotuku.cn/
    
    -   可自行注册账号体验
-   私有部署管理员端：https://hivechat-demo.vercel.app/
    
    -   Email: admin@demo.com
    -   Password: helloHivechat

3\. 技术栈
-------

-   Next.js
-   Tailwindcss
-   Auth.js
-   PostgreSQL
-   Drizzle ORM
-   Ant Design

4\. 安装和部署
---------

### 方法 1：本地部署

> 注意： 旧版本升级可能会有数据库结构变化，手动执行一下 `npm run initdb`, 进行更新，即使没有更新，也没有副作用

1.  克隆本项目到本地

```
git clone https://github.com/HiveNexus/hivechat.git
```

1.  安装依赖库

cd hivechat
npm install

1.  修改本地配置文件

将样例文件复制到 `.env`

cp .env.example .env

修改 .env 文件

# PostgreSQL 数据库连接 URL，此处为示例，需本地安装或连接远程 PostgreSQL
# 注意，本地安装暂不支持使用 Vercel 或 Neon 提供的 Serverless PostgreSQL
DATABASE\_URL\=postgres://postgres:password@localhost/hivechat

#用于用户信息等敏感信息的加密，可以使用 openssl rand -base64 32 生成一个随机的 32 位字符串作为密钥，此处为示例，请替换为自己生成的值。
AUTH\_SECRET\=hclqD3nBpMphLevxGWsUnGU6BaEa2TjrCQ77weOVpPg=

# 管理员授权码，初始化后，凭此值设置管理员账号，此处为示例，请替换为自己生成的值。
ADMIN\_CODE\=22113344

# 生产环境设置为正式域名，开启飞书等第三方登录时回调时会使用
NEXTAUTH\_URL\=http://127.0.0.1:3000

是否开启邮箱登录，开启值设为 ON，关闭时修改为 OFF，未设置时默认开启
EMAIL\_AUTH\_STATUS\=ON

# 是否开启飞书登录，开启值设为 ON，关闭时修改为 OFF，详细说明见底部附2
FEISHU\_AUTH\_STATUS\=OFF
FEISHU\_CLIENT\_ID\="cli\_xxxxxxxxxxxxxxxx"
FEISHU\_CLIENT\_SECRET\="xxxxxxxxHOEWIoE7eDc1Lhc0042OXXXX"

# 是否开启企业微信登录，开启值设为 ON，关闭时修改为 OFF
WECOM\_AUTH\_STATUS\=OFF
WECOM\_CLIENT\_ID\="ww728c371c2fXXXXXX"
WECOM\_AGENT\_ID\="100XXXX"
WECOM\_CLIENT\_SECRET\="H-7J4jzG0m1axpXLGshaCDlMOZxdjvkX6bIVLuXXXXXX"

# 是否开启钉钉登录，开启值设为 ON，关闭时修改为 OFF
DINGDING\_AUTH\_STATUS\=OFF
DINGDING\_CLIENT\_ID\="dingpcfi2kpuplXXXXXX"
DINGDING\_CLIENT\_SECRET\="3vk9-VFCExNckqNUk\_CL2F-HEgz7qGN-BimH0lZ1gUx6hWO7g\_an2lnkk6XXXXXX"

1.  初始化数据库

npm run initdb

1.  启动程序

```
//测试开发
npm run dev
//正式启动
npm run build
npm run start  
```

1.  初始化管理员账号

访问 `http://localhost:3000/setup` (实际使用的域名和端口号)，即可进入管理员账号设置页面，设置完成后，即可正常使用系统。

### 方法 2：Docker 部署

由于近期更新频繁，暂未提供 Docker 升级数据库的 SQL 脚本，如果是历史版本升级，测试用途的用户可直接删除存储卷下的 `hivechat_postgres_data`，数据库会自动重新初始化。如果正式环境 Docker 部署有升级需求，可联系作者(wechat:wuhaoworld)。 其他部署方式没有此问题。

1.  克隆本项目到本地

```
git clone https://github.com/HiveNexus/hivechat.git
```

1.  修改本地配置文件

将样例文件复制到 `.env`

cp .env.example .env

根据实际情况如下的配置项 修改 `AUTH_SECRET` 和 `ADMIN_CODE`，正式环境务必重新设置，测试用途时可不修改。 修改 .env 文件

# PostgreSQL 数据库连接 URL，Docker 部署时可留空
DATABASE\_URL\=

#用于用户信息等敏感信息的加密，可以使用 openssl rand -base64 32 生成一个随机的 32 位字符串作为密钥，此处为示例，请替换为自己生成的值，测试用途时可不修改。
AUTH\_SECRET\=hclqD3nBpMphLevxGWsUnGU6BaEa2TjrCQ77weOVpPg=

# 管理员授权码，初始化后，凭此值设置管理员账号，此处为示例，请替换为自己生成的值。
ADMIN\_CODE\=22113344

# 生产环境设置为正式域名，开启飞书等第三方登录时回调时会使用
NEXTAUTH\_URL\=http://127.0.0.1:3000

# 是否开启邮箱登录，开启值设为 ON，关闭时修改为 OFF，未设置时默认开启
EMAIL\_AUTH\_STATUS\=ON

# 是否开启飞书登录，开启值设为 ON，关闭时修改为 OFF，详细说明见底部附2
FEISHU\_AUTH\_STATUS\=OFF
FEISHU\_CLIENT\_ID\="cli\_xxxxxxxxxxxxxxxx"
FEISHU\_CLIENT\_SECRET\="xxxxxxxxHOEWIoE7eDc1Lhc0042OXXXX"

# 是否开启企业微信登录，开启值设为 ON，关闭时修改为 OFF
WECOM\_AUTH\_STATUS\=OFF
WECOM\_CLIENT\_ID\="ww728c371c2fXXXXXX"
WECOM\_AGENT\_ID\="100XXXX"
WECOM\_CLIENT\_SECRET\="H-7J4jzG0m1axpXLGshaCDlMOZxdjvkX6bIVLuXXXXXX"

# 是否开启钉钉登录，开启值设为 ON，关闭时修改为 OFF
DINGDING\_AUTH\_STATUS\=OFF
DINGDING\_CLIENT\_ID\="dingpcfi2kpuplXXXXXX"
DINGDING\_CLIENT\_SECRET\="3vk9-VFCExNckqNUk\_CL2F-HEgz7qGN-BimH0lZ1gUx6hWO7g\_an2lnkk6XXXXXX"

1.  启动容器

```
docker compose up -d
```

1.  初始化管理员账号

访问 `http://localhost:3000/setup` (实际使用的域名和端口号)，即可进入管理员账号设置页面，设置完成后，即可正常使用系统。

### 方法 3：在 Vercel 上部署

> 注意： 旧版本升级到 2025 年 4 月 5 日 之后更新的版本，如果遇到升级卡死，请手动登入到 Vercel 数据库管理页面，将 `group` 表下 `daily_token_limit`字段修改为 `monthly_token_limit`，然后重新部署。因为涉及到表结构的调整，脚本执行无法自动确认或跳过，会导致部署卡住，全新部署不存在此问题，详情见这里。

点击下面的按钮，即可开始部署。

默认将代码克隆的自己的 Github 后，需要填写环境变量：

```
# PostgreSQL 数据库连接 URL，Vercel 平台提供了免费的托管服务，详情见下面说明
DATABASE_URL=postgres://postgres:password@localhost/hivechat

#用于用户信息等敏感信息的加密，可以使用 openssl rand -base64 32 生成一个随机的 32 位字符串作为密钥，此处为示例，请替换为自己生成的值。
AUTH_SECRET=hclqD3nBpMphLevxGWsUnGU6BaEa2TjrCQ77weOVpPg=

# 管理员授权码，初始化后，凭此值设置管理员账号，此处为示例，请替换为自己生成的值。
ADMIN_CODE=22113344

# 生产环境设置为正式域名，开启飞书等第三方登录时回调时会使用
# 首次可使用 `https://Vercel中的项目名.vercel.app`
NEXTAUTH_URL=https://hivechat-xxx.vercel.app

是否开启邮箱登录，开启值设为 ON，关闭时设为 OFF
EMAIL_AUTH_STATUS=ON

# 是否开启飞书登录，开启值设为 ON，关闭时修改为 OFF，详细说明见底部附2
FEISHU_AUTH_STATUS=OFF
FEISHU_CLIENT_ID="cli_xxxxxxxxxxxxxxxx"
FEISHU_CLIENT_SECRET="xxxxxxxxHOEWIoE7eDc1Lhc0042OXXXX"

# 是否开启企业微信登录，开启值设为 ON，关闭时修改为 OFF
WECOM_AUTH_STATUS=OFF
WECOM_CLIENT_ID="ww728c371c2fXXXXXX"
WECOM_AGENT_ID="100XXXX"
WECOM_CLIENT_SECRET="H-7J4jzG0m1axpXLGshaCDlMOZxdjvkX6bIVLuXXXXXX"

# 是否开启钉钉登录，开启值设为 ON，关闭时修改为 OFF
DINGDING_AUTH_STATUS=OFF
DINGDING_CLIENT_ID="dingpcfi2kpuplXXXXXX"
DINGDING_CLIENT_SECRET="3vk9-VFCExNckqNUk_CL2F-HEgz7qGN-BimH0lZ1gUx6hWO7g_an2lnkk6XXXXXX"
```

版本升级
----

-   正常通过 npm 在服务器安装或更新时，先手动执行 `npm run initdb`, 检查数据库的更新，即使没有更新，也没有副作用
-   Docker 方式升级到 0.0.25 镜像（2025-06-28 发布版本）时，需要手动更新数据库，手动执行以下 SQL

\-- models 表新增内置工具的能力标识
ALTER TABLE models 
ADD COLUMN built\_in\_image\_gen boolean DEFAULT false,
ADD COLUMN built\_in\_web\_search boolean DEFAULT false;

\-- API 风格新增枚举类型 openai\_response
ALTER TYPE public.api\_style ADD VALUE 'openai\_response';
\-- 设置 api\_style 字段 not null
ALTER TABLE public.llm\_settings 
ALTER COLUMN api\_style SET NOT NULL;

-   Docker 方式升级到 0.0.26 镜像（2025-07-15 发布版本）时，需要手动更新数据库，手动执行以下 SQL

CREATE TYPE message\_send\_shortcut AS ENUM ('enter', 'ctrl\_enter');

ALTER TABLE public."user" 
ADD COLUMN message\_send\_shortcut message\_send\_shortcut NOT NULL DEFAULT 'enter';

#### 附1：Vercel（Neon）PostgreSQL 配置

1.  在 Vercel 平台顶部导航，选择「Storage」标签，点击 Create Databse
2.  选择 Neon(Serverless Postgres)

1.  按照指引完成创建后，复制此处 `DATABASE_URL` 的值，填入到上一步的 `DATABASE_URL` 中

1.  初始化管理员账号

按照以上方法安装部署完成后，访问 `http://localhost:3000/setup` (实际使用的域名和端口号)，即可进入管理员账号设置页面，设置完成后，即可正常使用系统。

#### 附2：第三方登录配置说明

-   企业微信登录配置说明
-   钉钉登录配置说明
-   飞书登录配置说明

### 交流群

群聊过期可加微信 wuhaoworld 拉你入群。
