---
project: cloudflare_temp_email
stars: 3206
description: CloudFlare free temp domain email 免费收发 临时域名邮箱 支持附件 IMAP SMTP TelegramBot
url: https://github.com/dreamhunter2333/cloudflare_temp_email
---

使用 cloudflare 免费服务，搭建临时邮箱
=========================

> 本项目仅供学习和个人用途，请勿将其用于任何违法行为，否则后果自负。

查看部署文档
------

Github Action 部署文档

English Docs

CHANGELOG
---------

在线演示
----

Backend

Frontend

-   使用 cloudflare 免费服务，搭建临时邮箱
    -   查看部署文档
    -   CHANGELOG
    -   在线演示
    -   功能/TODO
    -   Reference
    -   Join Community

功能/TODO
-------

-   使用 `password` 重新登录之前的邮箱
-   获取自定义名字的邮箱，`admin` 可配置黑名单
-   支持多语言
-   增加访问密码，可作为私人站点
-   增加自动回复功能
-   增加查看 `附件` 功能
-   使用 `rust wasm` 解析邮件
-   支持发送邮件
-   支持 `DKIM`
-   `admin` 后台创建无前缀邮箱
-   添加 `SMTP proxy server`，支持 `SMTP` 发送邮件, `IMAP` 查看邮件
-   添加完整的用户注册登录功能，可绑定邮箱地址，绑定后可自动获取邮箱JWT凭证切换不同邮箱
-   `Telegram Bot` 使用，以及 `Telegram` 推送

Reference
---------

-   Cloudflare D1 作为数据库
-   使用 Cloudflare Pages 部署前端
-   使用 Cloudflare Workers 部署后端
-   email 转发使用 Cloudflare Email Routing

Join Community
--------------

-   Discord
-   Telegram
