---
project: access-counter
stars: 23
description: 🌈 超级简单好用的 github profile 访问计数器。  使用 Vercel KV for Redis 记录浏览量。
url: https://github.com/wangrongding/access-counter
---

Access Counter
==============

> 一个 github profile 访问计数器，基于 moe-counter。

使用 Vercel KV for Redis 记录浏览量。

Website
-------

access-counter

How to Use
----------

Demo: 点击：→ 查看示例

在你的 github profile 中插入 img 或者 markdown 即可。

SVG address:

```
https://access-counter.vercel.app/api/counter?name=github-username
```

Img tag:

<img src\="https://access-counter.vercel.app/api/counter?name=github-username" />

Markdown:

!\[\](https://access-counter.vercel.app/api/counter?name=github-username)

请求参数

\-

name

github 用户名

theme

主题（001-006）

length

长度（显示几个图）

默认：

```
https://access-counter.vercel.app/api/counter?name=access-counter&theme=001&length=7
```

### One-Click Deploy

目前使用的是免费的 `Vercel KV for Redis`，每天只有 3000 次请求，你可以将此项目自己部署到 `vercel` ，点击下面按钮，快速部署。

设置好名称后，创建一个 KV Database

然后就可以了。

### Clone and Deploy

Clone the repository:

git clone

Install the dependencies:

pnpm install

Install Vercel CLI:

pnpm i -g vercel

Link your project to Vercel:

vercel link

Download your KV environment variables:

vercel env pull .env.development.local

Or open `.env.development.local` and set the environment variables to match the ones in

cp .env.example .env.development.local

Next, run Next.js in development mode:

pnpm dev

Deploy it to the cloud with Vercel (Documentation).
