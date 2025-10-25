---
project: juejinBooksSpider
stars: 7
description: 掘金小册爬虫
url: https://github.com/dext7r/juejinBooksSpider
---

📚 掘金小册爬虫 👋
============

> 🕷️ 掘金小册爬虫脚本。将小册保存为 markdown，pdf，html 格式

📜 说明
-----

本项目案例使用爬虫爬取的为公开的掘金小册。可在掘金小册/阅读 中查看。本项目仅供学习交流使用，请勿将个人付费小册公开。⚠️ 若公开由此造成的一切后果，与本项目无关。

🛠 使用
-----

### 👥 clone 项目

git clone https://github.com/h7ml/juejinBooksSpider.git
cd juejinBooksSpider

### 📦 install 依赖

pnpm install

# or
# npm install

# or
# yarn install

### 🎲 运行

# 爬取单本小册
# pnpm dev <小册地址>
pnpm dev https://juejin.cn/book/6844723704639782920

# 爬取多本小册 需要配置cookie 并且设置spiderAll为true 到.env文件。然后执行 pnpm start 即可

### 📁 配置文件说明

#### 📋 类型定义

// \\src\\types.d.ts
export type FileFormat \= 'pdf' | 'md' | 'html' | ''

export interface EvConfig {
  log: string | boolean
  storeDirs: string
  cookie: string
  course: string
  spiderAll: string | boolean
  headless: string | boolean
  filetype: FileFormat
  puppeteerOptions: PuppeteerLaunchOptions
}

#### ⚙️ .env

-   `cookie`：掘金网站的 Cookie，用于爬取授权访问的小册。
-   `isLog`：是否输出日志形式，默认为 `true`。开启后将在`dist`目录下产生`log`文件。
-   `storeDir`：小册保存的目录，默认为`docs`。表示当前目录下的`docs`目录。
-   `course`：小册地址，默认为`https://juejin.cn/book/6844723704639782920`。若命令行中传入了小册地址，则以命令行中的地址为准。
-   `spiderAll`：是否爬取所有小册，默认为`false`。若为`true`，则会爬取所有小册，否则只爬取`course`中指定的小册。
-   `filetype`: 保存的文件类型，默认为`md`。可选值为`md`、`pdf`、`html`。
-   `headless`: 是否使用无头浏览器，默认为`true`。若为`false`，则会使用有头浏览器，方便调试。文档参考：puppeteer

#### ⚙️ `puppeteerOptions`

`puppeteerOptions` 为`puppeteer`的启动参数，非必须。文档参考：puppeteer 如需修改。请在config 中配置

-   若你在`wsl` 中使用，需要安装`google-chrome` 然后配置`puppeteerOptions`参数为`{executablePath: 'google-chrome'}` 即可。文档参考install-google-chrome-wsl @croatialu
    
-   感谢 @croatialu @maomao1996 @Dnzzk2 提供了灵感和建议
    

### 🏠 主页

👤 作者
-----

👤 **h7ml**

-   Github: @h7ml

🤝 贡献者
------

贡献、问题和功能请求都受到欢迎！  
欢迎提出问题和建议. 您也可以查阅 贡献指南.

> 📊 Total: **17**

📝 许可协议
-------

版权所有 © 2023 h7ml。  
本项目使用 Apache--2.0 许可协议。

* * *

_此 README 是通过 readme-md-generator ❤️ 生成的_
