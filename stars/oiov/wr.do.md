---
project: wr.do
stars: 1831
description: 一站式域名服务平台，集成短链生成、无限域名邮箱、文件存储和子域名管理，带有管理员面板，支持自部署
url: https://github.com/oiov/wr.do
---

WR.DO
=====

一站式域名服务平台，集成短链服务、临时邮箱、子域名管理、文件存储和开放API接口。

官网 · 部署文档 · 反馈讨论 · English | 简体中文

  
  

截图预览
----

功能列表
----

> Demo: https://699399.xyz (管理员账号: `admin@admin.com`, 密码: `123456`)

**🔗 短链服务** - \[功能列表\]

-   支持自定义短链
-   支持生成自定义二维码
-   支持密码保护链接
-   支持设置过期时间
-   支持访问统计（实时日志、地图等多维度数据分析）
-   支持调用 API 创建短链

**📮 域名邮箱服务** - \[功能列表\]

-   支持创建自定义前缀邮箱
-   支持过滤未读邮件列表
-   可创建无限数量邮箱
-   支持接收无限制邮件 （依赖 Cloudflare Email Worker）
-   支持发送邮件（依赖 Resend）
-   支持 Catch-All 配置
-   支持 Telegram 推送（多频道/群组）
-   支持调用 API 创建邮箱
-   支持调用 API 获取收件箱邮件

**🌐 子域名管理服务** - \[功能列表\]

-   支持管理多 Cloudflare 账户下的多个域名的 DNS 记录
-   支持创建多种 DNS 记录类型（CNAME、A、TXT 等）
-   支持开启申请模式（用户提交、管理员审批）
-   支持邮件通知管理员、用户域名申请状态

**📂 文件存储服务** - \[功能列表\]

-   支持多渠道（S3 API）云存储平台（Cloudflare R2、AWS S3、OSS等）
-   支持单渠道多存储桶配置
-   动态配置文件上传大小限制
-   支持拖拽、批量、粘贴上传文件
-   支持批量删除文件
-   快捷生成文件短链、二维码
-   支持部分文件在线预览内容

**📡 开放接口服务** - \[功能列表\]

-   支持调用 API 获取网站元数据
-   支持调用 API 获取网站截图
-   支持调用 API 生成网站二维码
-   支持调用 API 将网站转换为 Markdown、Text
-   支持生成用户 API Key，用于第三方调用开放接口

**👑 管理员模块** - \[功能列表\]

-   多维度图表展示网站状态
-   域名服务配置（动态配置各项服务是否启用，包括短链、临时邮箱（收发邮件）
-   用户列表管理（设置权限、分配使用额度、禁用用户等）
-   动态配置登录方式 (支持 Google, GitHub, 邮箱验证, 账户密码, LinuxDO)
-   短链管理（管理所有用户创建的短链）
-   邮箱管理（管理所有用户创建的临时邮箱）
-   子域名管理（管理所有用户创建的子域名）

技术栈
---

-   Next.js + React + TypeScript
-   Tailwind CSS 用于样式设计
-   Prisma ORM 作为数据库工具
-   Cloudflare 作为主要的云基础设施
-   Vercel 作为推荐的部署平台
-   Resend 作为邮件服务
-   Next-Intl 作为国际化支持

快速开始
----

查看开发者手把手部署教程文档。

自部署教程
-----

> 注意，任何部署方式都需要先配置环境变量，若部署后修改了环境变量，需要**重新部署**才会生效。

### 使用 Vercel 部署

记得填写必要的环境变量。

### 使用 Docker Compose 部署

在服务器中创建一个文件夹，进入该文件夹并新建 docker-compose.yml、.env 文件：

\- wrdo
  | - docker-compose.yml
  | - .env

在 `.env` 中填写必要的环境变量，然后执行:

docker compose up -d

> 或只创建 docker-compose.yml 文件，环境变量直接填写在yml中，比如将`DATABASE_URL: ${DATABASE_URL}`替换成`DATABASE_URL: your-database-uri`

### 使用 EdgeOne 部署

> 此方法部署目前无法build成功，不建议使用

本地开发
----

将 `.env.example` 复制为 `.env` 并填写必要的环境变量。

git clone https://github.com/oiov/wr.do
cd wr.do
pnpm install

#### 初始化数据库

pnpm postinstall
pnpm db:push

# 在 localhost:3000 上运行
pnpm dev

-   默认账号(管理员)：`admin@admin.com`
-   默认密码：`123456`

> 登录后请及时修改密码

#### 管理员初始化

> 此初始化引导在 v1.0.2 版本后, 不再是必要步骤

访问 https://localhost:3000/setup

环境变量
----

查看 开发者文档.

Fork 仓库同步
---------

本项目配置了与上游仓库 oiov/wr.do 的同步工作流，支持：

-   🔄 **手动触发同步** - 默认关闭自动同步，完全控制同步时机
-   💬 **同步后自动评论** - 在相关 commit 上添加详细的同步信息
-   🚨 **智能错误处理** - 同步失败时自动创建详细的 Issue
-   🧹 **自动清理通知** - 自动关闭之前的同步失败 Issue

前往如何手动触发同步查看详细文档。

社区群组
----

-   Discord: https://discord.gg/AHPQYuZu3m
-   微信群：

贡献者
---

Star History
------------

开源协议
----

MIT
