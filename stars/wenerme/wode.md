---
project: wode
stars: 59
description: Wener Node, Bun, NestJS, React Utils, Hooks & Demos
url: https://github.com/wenerme/wode
---

wode
====

Wener NodeJS Monorepo

-   WODE -> Wener nODE & DEMO
-   apps
    -   web http://apis.wener.me
        -   React, NextJS, Playground for experiments
    -   console https://wode.wener.me
        -   React, ViteJS, Console for Homelab, CRM, etc.
    -   server
        -   wode-api-server
            -   HonoJS, MikroORM, GraphQL, RESTful
            -   backend for web & console
        -   wode-worker
            -   BullMQ worker
    -   wenerme/wode-stub
        -   Template for web + console + server project
-   packages
    -   @wener/reaction
        -   React hooks & utils
    -   @wener/utils
        -   Typescript
        -   Zero Dependencies
    -   @wener/torrent
        -   Bencode codec
    -   @wener/tiptap
        -   TipTap based Google Doc
            -   Extensions
                -   classNames, column-count, margin-{left,right,top,bottom}, line-height, font-size, text-indent, letter-spacing
                -   video, indent
                -   renderMarkdown
                -   parseMarkdown
                -   slash command
    -   @wener/unpkg
        -   Selfhost https://unpkg.com/ , https://cdn.jsdelivr.net/npm/ alternative
    -   @wener/wode
        -   common config
    -   @wener/client
        -   Wechat client
        -   Wecom/Wework client
        -   Xunfei spark client
        -   OpenAI chat client
    -   @wener/nextjs
        -   Nats based RPC service
        -   NextJS utils
        -   mikro-orm utils
    -   ethers - WIP
        -   Web3 utils
    -   @wener/system
        -   hooks to lets systemjs work with npm registry & package.json

TODO
----

-   TipTapWord
    -   媒体资源选中编辑时回显
    -   媒体资源允许配置 URL
    -   TOC
    -   属性编辑器
    -   LineHeight 菜单
    -   print
    -   toolbar memo
-   Typedoc
    -   package multi entryPoints TypeStrong/typedoc#1937
-   Web
    -   i18n need a refresh to works properly

Links
=====

**Summary**

Repository

NPM

Info

@wener/utils

Doc  
  
  

@wener/system

Doc  
  
  

@wener/reaction

Doc  
  
  

@wener/torrent

Doc  
  
  

@wener/unpkg

Doc  
  
  

@wener/wode

Doc  
  
  

-   Site
    -   wener.me
        -   Blog
        -   Github wenerme/wener
    -   wode.vercel.app
        -   Playground
        -   GitHub wenerme/wode
    -   apis.wener.me
        -   APIs playground with docs & stories
        -   GitHub wenerme/apis
-   Library
    -   @wener/reaction - \-
        -   Docs
        -   React hooks, render, logical components
        -   helpful typing
        -   some external minimal helpful utils
            -   reduce packages
    -   @wener/utils - \-
        -   Docs
        -   utils for daily use
        -   zero dependencies
    -   @wener/system - \-
        -   Docs
        -   Utils for systemjs
        -   make systemjs work with npm & package.json
    -   @wener/ui - \-
        -   Storybook
        -   Document
    -   @wener/tinyrpc - \-
        -   Document
    -   rjsf-antd-theme - \-
        -   Ant Design Theme for React Json Schema Form
        -   Storybook
        -   Document
