---
project: awesome-nodejs
stars: 1287
description: Node.js 资源大全中文版。An awesome Node.js packages and resources
url: https://github.com/huaize2020/awesome-nodejs
---

> 该项目受 awesome-nodejs 启发
> 
> 因库收录较多，全部同步star数会影响加载速度，因此只展示 > 100 的仓库
> 
> 同时推荐你查看我正在维护的其他仓库
> 
> -   awesome-nodejs
>     -   awesome-koa
>     -   awesome-egg
> -   awesome-frontend
>     -   awesome-react
>     -   awesome-react-native
>     -   awesome-electron
> -   awesome-rust

English | 简体中文

目录
--

-   目录
-   官方资源
-   资源
    -   工具
    -   书籍
    -   教程
        -   免费教程
        -   付费教程
    -   视频
        -   付费视频
    -   面试题
-   GIT 仓库
    -   文本/字符串
    -   数字
    -   数学运算
    -   日期 和 时间
    -   正则/通配符匹配
    -   URL
    -   对象 / JSON / JSON Schema
    -   元编程
    -   图像处理
        -   SVG
    -   画布（Canvas）
    -   音频 / 视频处理
    -   字体
    -   颜色
    -   加解密
    -   流
    -   检测/判断
    -   数据校验
    -   函数式编程
    -   流程控制
    -   控制反转/依赖注入
    -   Shell
    -   环境
    -   事件
    -   命令行工具
    -   Node.js 管理工具
    -   NPM
    -   Monorepo
    -   文件系统
    -   解析工具
    -   Git
    -   日志
    -   进程管理
    -   代码校验 和 格式化工具
    -   配置工具
    -   构建工具
    -   模板引擎
    -   Web 框架
    -   GraphQL
    -   内容管理系统 (CMS)
    -   静态网站生成 & 博客
    -   文档生成
    -   接口管理
    -   桌面应用程序
    -   实时通信
    -   任务队列
    -   定时任务
    -   调试
    -   性能分析/诊断
    -   性能优化
    -   应用性能监控 (APM)
    -   论坛
    -   数据库
    -   缓存
    -   搜索引擎/分词
    -   Serverless
    -   自动化 & 机器人流程自动化 - RPA
    -   测试相关
    -   办公软件
    -   操作系统识别
    -   文件压缩解压
    -   最小化
    -   源码混淆/保护
    -   邮箱
    -   网络
    -   HTTP
    -   限流
    -   验证
    -   授权 / 鉴权
    -   分布式
    -   序列化
    -   RPC
    -   服务端 DOM
    -   爬虫
    -   AST
    -   WebAssembly
    -   设计稿转代码（D2C）
    -   沙箱
    -   硬件
    -   物联网 IoT
    -   机器学习 和 神经网络
    -   自然语言处理
    -   GPT
    -   OCR
    -   比特币
-   场景
    -   低代码（Lowcode）
    -   云 IDE

官方资源
----

-   官网
-   文档
-   仓库
-   文章教程

资源
--

### 工具

-   openbase - 让你每次都要找到合适的包。目前支持 JavaScript，即将推出更多语言。
-   npm.devtool - 找到最适合您的包，分析您的项目技术栈。

### 书籍

-   狼书（卷3）：Node.js高级技术 - 2022-12-01 - @狼叔
    -   本书聚焦于Node.js高级技术。第1章介绍如何编写npm模块，其中涉及对许多常用模块的解析。第2章介绍如何编写企业级Web开发框架，主要剖析了开发框架的流程。第3章介绍如何构建具有Node.js特色的服务，着重讲解了页面即服务的概念。第4章介绍服务器部署与性能调优的相关知识。第5章介绍TDD和BDD理念，以及如何编写测试用例，同时分享了笔者关于开源和自学的看法。
-   狼书（卷2）：Node.js Web应用开发 - 2020-01-01 - @狼叔
    -   本书主要讲解Node.js Web应用开发涉及的HTTP基础知识、常用开发框架、源码原理、数据库和项目实战，旨在向读者展示如何通过Node.js和Koa编写出更具前端特色的Web应用。本书还讲解了Koa中的核心中间件原理，展望了未来Web应用开发的发展方向。
-   狼书（卷1）：更了不起的Node.js - 2019-07-01 - @狼叔
    -   本书以Node.js为主，讲解了Node.js的基础知识、开发调试方法、源码原理和应用场景，旨在向读者展示如何通过新的Node.js和npm编写出更具前端特色、更具工程化优势的代码。
-   Node.js：来一打 C++ 扩展 - 2018-06-01 - @死月
    -   Node.js 作为近几年新兴的一种编程运行时，托 V8 引擎的福，在作为后端服务时有比较高的运行效率，在很多场景下对于我们的日常开发足够用了。不过，它还为开发者开了一个使用C++ 开发 Node.js 原生扩展的口子，让开发者进行项目开发时有了更多的选择。
-   深入浅出Node.js - 2013-12-01 - @朴灵
    -   初版时间《深入浅出Node.js》从不同的视角介绍了 Node 内在的特点和结构。由首章Node 介绍为索引，涉及Node 的各个方面，主要内容包含模块机制的揭示、异步I/O 实现原理的展现、异步编程的探讨、内存控制的介绍、二进制数据Buffer 的细节、Node 中的网络编程基础、Node 中的Web 开发、进程间的消息传递、Node 测试以及通过Node 构建产品需要的注意事项。附录介绍了Node 的安装、调试、编码规范和NPM 仓库等事宜。

### 教程

#### 免费教程

-   Node.js Best Practices - Node.js 最佳体验列表。
-   Nodejs 包教不包会 - 经典 Nodejs 教程。
-   Nodejs 技术栈 - 包含很多 nodejs 相关文章。
-   七天学会 NodeJS - 经典 Nodejs 教程。
-   understand-nodejs - 通过源码分析 nodejs 原理。
-   Nodejs-Roadmap - 本文档是作者 @五月君 从事 Node.js 开发以来的学习历程。
-   Node.js 应用故障排查手册 - 本手册主要的目的是帮助广大的 Node.js 开发者应对开发和线上部署中遇到的问题。

#### 付费教程

> 仅做整理，不代表编者意图和推荐，请自行判断

-   深入剖析 Node.js 底层原理 - 掘金小册 - theanarkh 字节跳动 Node.js 工程师
    -   从源码角度解读 Node.js 底层设计，并实现一个简单的 JS 运行时。

### 视频

#### 付费视频

> 仅做整理，不代表编者意图和推荐，请自行判断

-   Node.js 开发实战 - 极客时间 - 杨浩 腾讯高级工程师
    -   本课程站在一个前端工程师的角度，讲解如何基于 Node.js 开发一个完整的项目，从一开始的技术预研再到实际开发、性能优化以及最终的框架架构搭建和工程化建设，带你完整体验一遍前端工程师使用 Node.js 进行项目开发会碰到的各种常见场景和技术难点，学完课程之后，你将能够熟练运用 Node.js 进行大型项目的设计和开发。
-   构建千万级高可用企业级Node.js应用 - 慕客网 - 进阶
    -   即使你会用 Node.js 开发小型项目后端系统，也只能说你掌握了它最基本的用法，并不足以打动大厂招聘官。因为，很多大厂选择 Node.js来承接服务端（BFF层），涉及的项目更为复杂，要求也更加精细，这需要前端既非常懂 Node.js 本身，也要懂其相关的服务端知识，才能更好地支撑大规模线上业务。本课程就带你学习BAT级别的 Node.js 用法，快速提升你在前端市场的区分度和竞争力。
-   Node.js工程师养成计划 - 慕客网 - 初级 - 北瑶 - 系统架构师
    -   保姆级教程，手把手带你完成工具、服务器、中间层等多类应用开发实战

### 面试题

-   饿了么 Node.js 面试题及实战教程 - 由饿了么前端团队分享的 node.js 实战经验，非常实用。

GIT 仓库
------

### 文本/字符串

-   通用
    
    -   humps - 将字符串 或 对象的Key 从下划线转化为驼峰。
    -   dedent - ES6 模板字符串函数，用于去除多行字符串的缩进。
    -   camelcase - 将破折号/点号/下划线/空格分隔的字符串转换为驼峰式, 案例：foo-bar→fooBar。
    -   string-width - 获取字符串的可视宽度-显示字符串所需的列数。
    -   decamelize - 将驼峰式字符串转化成小写带分隔符带字符串, 案例：unicornRainbow → unicorn\_rainbow。
    -   detect-indent - 检查代码缩进。
    -   string-length - 获取字符串的真实长度 - 通过正确计算星号并忽略 ansi 转义码。
    -   strip-indent - 将字符串每一行中前置的空格删除。
    -   strip-bom - 从字符串中删除 UTF-8 字节顺序标记（BOM）。
    -   indent-string - 将字符串每一行缩进。
    -   redent - 去除多余的缩进并缩进字符串。
    -   normalize-newline - 将字符串中的换行符规范化为 `\n`。
    -   min-indent - 取每一行最少前置空格数。
    -   trim-right - 与 String#trim() 类似，但仅删除右侧的空格。
    -   splice-string - 移除或替换字符串的一部分。类似`Array#splice`.
-   国际化
    
    -   i18next - 国际化框架。
    -   i18n-node - 具有动态 JSON 存储的简单翻译模块。
    -   babelfish - 适用于 JavaScript 的人性化 i18n（node.js +浏览器）。
-   唯一 ID
    
    -   nanoid - 小巧、安全、URL 友好、唯一的字符串 ID 生成器。
    -   uuid - 在 JavaScript 中生成符合 RFC 规范的 UUID。
    -   shortid - 短 ID 生成器。 网址友好。 不可预测的。 集群兼容。
    -   cuid - 针对水平扩展和性能优化的抗冲突 ids。
    -   ulid - 通用唯一词典分类排序标识符。
    -   short-uuid - 将标准 UUID 转换为更短的格式并返回。
    -   uuid-js - 用于生成和解析 UUID、TimeUUID 并根据日期生成 TimeUUID 以供范围选择。
    -   pure-uuid - 基于纯 JavaScript 全局唯一 ID(UUID)。
    -   lsp-uuid - 一个基于 SnowFlake 的 uuid 生成器，用于浏览器和 Nodejs。 保持序列并且可以反序列化。
-   编码/解码
    
    -   he - HTML 实体编码器/解码器。
    -   iconv-lite - 转换字符编码。
    -   html-entities - 最快的 HTML 实体编码/解码库.
    -   jschardet - JavaScript 编码自动识别 (Python 版 chardet 的实现)。
-   差异对比
    
    -   jsdiff - 一种 JavaScript 文本差异实现。
    -   recursive-diff - 查找两个 JavaScript 对象的差异，支持数组、数字、日期和其他原始数据类型。
    -   json0-ot-diff - 查找两个 JSON 对象之间的差异，并根据 JSON0 OT Type 生成将第一个对象转换为第二个对象的操作转换/值(OT)操作。
-   随机字符串
    
    -   generate-password - 用于生成加密安全密码的 NodeJS 库。
    -   randomatic - 使用简单的选项来指定长度和使用数字、字母数字、字母、特殊或自定义字符的模式，轻松生成密码等随机字符串。(源自`generate-password`)
-   其他
    
    -   StegCloak - 基于纯 JavaScript 开发的隐写功能模块，StegCloak 可以对文本中的机密信息进行压缩和加密，然后再使用特殊的 Unicode 不可见字符来隐藏它。
    -   unhomoglyph - 规范视觉上相似的 unicode 字符。

### 数字

-   Numeral.js - 格式化和操作数字。
-   bignumber.js - 用于任意精度十进制和非十进制算术的 JavaScript 库。
-   decimal.js - JavaScript 的任意精度的十进制类型。
-   big.js - 一个小型，快速的 JavaScript 库，用于任意精度的十进制算术运算。
-   random-js - 一个 JavaScript 随机数生成库。
-   round-to - 将数字四舍五入到指定的小数位数：`1.234`→`1.2`。
-   unique-random - 生成连续唯一的随机数。
-   random-int - 生成随机整数。
-   random-float - 生成随机浮点数。 label=Star)

### 数学运算

-   mathjs - 广泛的数学运算库。
-   ndarray - 多维数组。
-   algebra - 代数结构。
-   multimath - 在 WebAssembly 和 JS 中进行快速图像数学运算。

### 日期 和 时间

-   moment - 解析、校验、操作和显示日期。
-   dayjs - 仅 2KB，不可变的日期时间库。使用与 Moment.js 同样的 API，Moment.js 的替代库。
-   date-fns - 现代 JavaScript 日期工具库。
-   luxon - 用于处理日期和时间的库。
-   timeago.js - timeago.js 是一个很小的（2.0 kb）库，用于使用 \*\*\* time ago 语句格式化日期。
-   ms - 毫秒转换工具。
-   dateformat - 日期格式化。
-   pretty-ms - 将毫秒转换为人类可读的字符串，如: `1337000000` → `15d 11h 23m 20s`。
-   strftime - JavaScript 版时间格式化 Strftime。
-   node-microtime - 以微秒为单位获取当前时间。
-   date-utils - 用于 Node.js 和浏览器的日期垫片（Polyfills）。
-   pretty-hrtime - 将 process.hrtime()的结果转换为人可读性的字符串。
-   humanize-ms - 对人友好可读的时间格式转换为毫秒。

### 正则/通配符匹配

-   path-to-regexp - 将路径字符串（如`/user/:name`）转化为正则。
-   minimatch - 最小匹配工具。
-   micromatch - 高度优化的通配符和全局匹配库。更快，直接替换到 minimatch 和 multimatch。由 webpack、babel core、yarn、jest、browser-sync、documentation.js、stylelint、nyc、ava 以及许多其他资源使用！
-   randexp.js - 根据给定的正则表达式，生成随机字符串。
-   safe-regex - 检测可能是灾难性的、指数时间的正则表达式。
-   matcher - 简单通配符匹配。
-   escape-string-regexp - 转义特殊正则字符。
-   multimatch - 扩展 minimatch.match() 以支持多种模式。
-   execall - 在字符串中查找多个 RegExp 匹配项。

### URL

-   URI.js - URL 转换库。
-   qs - 请求字符串解析器。
-   query-string - 解析和字符串化 URL 查询字符串。
-   url-parse - 轻量 URL 解析器，可跨 Node.js 和浏览器环境无缝运行。
-   normalize-url - 规范化 URL.
-   url-pattern - 比正则表达式更易匹配 URL 和其他字符串，将字符串转化成数据 或 将数据转换成字符串。
-   native-url - 使用内建 URL API 实现的 NodeJS URL 模块。
-   url-join - 将所有参数连接在一起，并将结果 url 规范化。
-   humanize-url - 使 URL 更可读: http://sindresorhus.com → sindresorhus.com。
-   parseurl - 使用记忆化方式解析 URL.
-   file-url - 将文件路径转化为文件 URL: `unicorn.jpg` → `file:///Users/sindresorhus/unicorn.jpg`。
-   encodeurl - 将 URL 编码为"百分比"形式，不编码已编码部分。

### 对象 / JSON / JSON Schema

-   json5 - JSON5 是对 JSON 的扩展，其目的是能够更加容易的阅读和编写。
-   jsondiffpatch - 对比 JSON 对象，并生成差异和 Patch 信息。
-   json-schema-faker - JSON-Schema + 假数据生成器。
-   fast-json-stringify - 比 JSON.stringify()快 2 倍。
-   humps - 将字符串 或 对象的Key 从下划线转化为驼峰。
-   jsonfile - 轻松读写 JSON 文件。
-   bson - Node.js 和浏览器的 BSON 解析器，BSON 是“Binary JSON”的缩写，是类 JSON 文档的二进制编码序列化。
-   jsonata - JSONata 查询和转换语言 - http://jsonata.org
-   json-stable-stringify - 具有自定义排序功能的确定性 JSON.stringify(), 可以从字符串化结果中获取确定性哈希值。
-   json-diff - 结构化对比 JSON 文件差异。
-   json-mask - 用于选择 JS 对象特定部分，而隐藏其余部分的微型语言和引擎。
-   strip-json-comments - 去除 JSON 文件中的注释。让你可以在 JSON 中使用注释。
-   json-stringify-safe - 类似于 JSON.stringify，但不会引发循环引用。
-   dottie.js - 快速安全的访问和操作嵌套对象。
-   load-json-file - 读取并解析 JSON 文件。
-   jsonc-parser - 带注释的 JSON 扫描器和解析器。
-   parse-json - 解析 JSON，如果解析失败带有更有帮助的错误信息。
-   write-json-file - 序列化并写入 JSON 文件。
-   fast-json-stable-stringify - 确定性 JSON.stringify() - 比 @substack 的 json-stable-stringify 更快的版本，不带 jsonify。
-   jsonuri - 使用”URI 样式“的方法来操作数据。

### 元编程

-   reflect-metadata - ECMAScript 元数据反射 API 的原型。

### 图像处理

-   sharp - 调整 JPEG，PNG，WebP 和 TIFF 格式图像大小的最快模块。
-   jimp - 纯 JavaScript 中的图像处理。
-   satori - html 转 svg.
-   gm - GraphicsMagick 和 ImageMagick 封装。
-   qrcode - 二维码和条形码生成器。
-   pixelmatch - 最小、最简单、最快的 JavaScript 像素级图像比较库。
-   Resemble.js - 图像分析和比较。
-   pica - 使用纯 JS 中的高质量和快速调整大小（lanczos3）。 当不允许像素化时替代 canvas drawImage()。
-   jsQR - 一个纯 javascript 的二维码读取库。 该库接收原始图像，并将定位、提取和解析其中发现的任何二维码。
-   lwip - 不需要 ImageMagick 的轻量级图像处理器。
-   gifski - 基于 libimagequant (pngquant) 的 GIF 编码器。 从糟糕的 GIF 格式中挤出最大可能的质量。
-   probe-image-size - 无需完全下载即可获取大多数图像格式的大小.
-   omggif - GIF 89a 编码解码器。
-   jpeg-js - 使用纯 JavaScript 的 JPEG 编码和解码器。
-   pngjs - 简单的 PNG 编码解码器。
-   get-pixels - 将图像读入 ndarray。
-   gifencoder - Node.js 服务器端动画 gif 生成。
-   ImageScript - 零依赖的JavaScript图片操作库。
-   image-type - 检测 Buffer / Uint8Array 的图像类型。
-   node-pngquant - pngquant 作为可读/可写流操作 png。
-   node-bitmap - 纯 JavaScript Bitmap 库。

#### SVG

-   svgo - 一个优化 SVG 文件的工具。
-   svg-captcha - Node.js 中生成 SVG 验证码。

### 画布（Canvas）

-   node-canvas - Node canvas 是一个由 Cairo 支持的 NodeJS 的 Canvas 实现。
-   skia-canvas - Canvas 环境。

### 音频 / 视频处理

-   fluent-ffmpeg - FFMPEG 的流畅 API (http://www.ffmpeg.org)
-   FFCreator - 一个基于 node.js 的高速短视频加工库。
-   node-ffmpeg - Nodejs 版 Ffmpeg 模块。

### 字体

-   font-spider - 字蛛是一个智能 WebFont 压缩工具，它能自动分析出页面使用的 WebFont 并进行按需压缩。
-   svg2ttf - 字体转换器, SVG 格式转化为 TTF。
-   ttf2woff - 字体转换器, TTF 格式转化为 WOFF。
-   svgicons2svgfont - 连接 SVG 图标并输出 SVG 字体。
-   webfont - 很棒的网页字体生成器。
-   ttf2eot - 字体转换器, TTF 格式转化为 EOT。
-   wawoff2 - 使用 WebAssembly 构建 Google 的 woff2。

### 颜色

-   chroma - JavaScript 库，用于各种颜色处理。
-   randomColor - 一个小型脚本，用于优雅的生成颜色。
-   rgbaster - 🎨一个简单的库，用于从图像中提取主色。
-   TinyColor - 快速、小型的颜色操作和转换库。
-   onecolor - 面向对象的 JavaScript 颜色解析器/计算工具包，支持 RGB，HSV，HSL，CMYK 和 alpha 通道。 颜色空间之间的转换是隐式进行的，并且所有方法都返回新对象，而不是对现有实例进行突变。 可在浏览器和 Node.js 中使用。

### 加解密

-   crypto-js - JavaScript 加密标准库。
-   sjcl - 斯坦福 Javascript 加密库。
-   bcrypt - Node.js 版 Bcrypt。
-   jsencrypt - 用于执行 OpenSSL RSA 加密、解密和密钥生成的 Javascript 库。
-   bcrypt.js - 经过优化 bcrypt 库，使用纯 JavaScript 且零依赖。
-   jsrsasign - "jsrsasign"（RSA Sign JavaScript 库）是一个开源的免费加密库，支持纯 JavaScript 中的 RSA/RSAPSS/ECDSA/DSA 签名/验证、ASN.1、PKCS#1/5/8 私钥/公钥、X.509 证书、CRL、OCSP、CMS SignedData、TimeStamp、CAdES JSON Web 签名/令牌。
-   node-rsa - Node.js RSA 库。
-   aes-js - AES 的纯 JavaScript 实现。
-   object-hash - 基于 javascript 对象生成对应哈希。
-   node-md5 - 一个 JavaScript 函数，用于使用 MD5 对消息进行哈希处理。
-   crypto-hash - 微型哈希模块，在 Node.js 和浏览器中使用原生 crypto API。
-   hash.js - 使用纯 JavaScript 的哈希实现。
-   crc - 在 Node.js 和浏览器的超快 CRC 实现。
-   sm-crypto - sm2, sm3, sm4 的 JavaScript 实现。
-   sha.js - 使用纯 JavaScript 中的流式 SHA 哈希。
-   hash-sum - 极快的唯一哈希生成器。
-   cryptr - 非常基础的加密和解密 Node.js 模块。
-   pbkdf2 - 在 Node 中具有任何受支持的哈希算法 PBKDF2。
-   node-object-hash - Node.js 对象哈希库，具有属性/数组排序以提供常量哈希。它还提供了一种返回排序对象字符串的方法，可用于不使用哈希的对象比较。
-   bcrypt-pbkdf - POpenBSD `bcrypt_pbkdf` Javascript 实现。

### 流

-   event-stream - EventStream 就像函数式编程遇到 IO。
-   through2 - 基于 Node stream2 的封装进行转换以避免显式的子类化噪声。
-   JSONStream - 流 JSON.parse 和 stringify。
-   mississippi - 有用的流实用程序模块的集合，用于更好编写的使用流的代码。
-   readable-stream - 可读流。
-   pump - 将流连接在一起，如果其中一个关闭，则关闭所有流。
-   concat-stream - 可写流，它将字符串或数据连接起来并执行回调。
-   stream-json - stream-json 是用于创建自定义标准兼容 JSON 处理器的 nod​​e.js 流组件的集合，该组件所需的内存占用最少。它可以解析远远超出可用内存的 JSON 文件。甚至单个原始数据项（键，字符串和数字）也可以分段流式传输。还包括流式 SAX 启发式的基于事件的 API。
-   split - 分解流并重新组装它，以便每一行都是一块。匹配器可以是字符串，也可以是正则表达式。
-   tar-stream - tar-stream 是一个流式 tar 解析器和生成器。
-   node-byline - 逐行流阅读器。
-   ndjson - 流逐行分隔的 json 解析器 + 序列化器。
-   oppressor - 流 HTTP 压缩响应协商程序。
-   multistream - 一种流，一个接一个地发出多个其他流（streams2）。
-   get-stream - 以字符串，缓冲区或数组的形式获取流。
-   node-stream-buffer - 使用缓存的可读和可写流。
-   split2 - 拆分 stream3 样式。
-   fstream - 高级的 Node.js 文件操作流。
-   pumpify - 使用泵和全双工，将一系列流合并为单个双工流。
-   progress-stream - 读取流的进度。
-   merge-stream - 将多个流合并为一个交错流。
-   duplexify - 将可写和可读流转换为具有异步初始化和 stream1/streams2 输入支持的 stream2 双工流。
-   into-stream - 将缓存/字符串/数组/对象转换为流。
-   merge2 - 按顺序或并行的方式将多个流合并为一个流。
-   end-of-stream - 当可读/可写/双工流已完成或失败时，调用回调。
-   stream-to-promise - 将流（可读或可写流）转换为 Promise。
-   node-streamifier - 将 Buffer/String 转换为可读流。
-   stream-spec - Stream 的可执行规范（让测试流变得更容易）。
-   from2 - ReadableStream 的便捷封装，其灵感来自 through2。
-   dmap-stream - 基于 Event-stream 事件流重构。
-   emit-stream - 将 event-emiiters 转换为流 和 将流转换为 event-emiiters。
-   stream-combiner - 将管道变成单个流。合并返回的流，写入第一个流并从最后一个流读取的流。
-   duplexer - 创建一个双工流。
-   promise-streams - Node.js 流的集合，可以很好地与 Promises (through, map, reduce 等）一起使用。
-   stromjs - 无依赖的流实用程序。流的 Lodash。
-   cloneable-readable - 安全地克隆可读流。
-   binary-split - 快速的换行符（或任何分隔符）分隔符流。
-   stream-combiner2 - stream3 的 stream-combiner。
-   through2-concurrent - 简单的 Node.JS 流（streams2）转换，可并行执行转换功能（可设置的最大并发数）。
-   destroy - 如果可能，销毁流。
-   peek-stream - 转换流，可让您在决定如何解析前先窥视第一行。
-   resumer - 通过流开始暂停，并在下一个 tick 恢复。
-   stream-each - 迭代流中的所有数据。
-   flush-write-stream - 一种写入流构造函数，支持流完成之前调用的 flush 函数。
-   multi-write-stream - 创建一个可写流，其可写入多个其他可写流。
-   first-chunk-stream - 缓冲并转换流的前 n 个字节。
-   multi-read-stream - 可读流，它同时从多个可读流中读取。
-   node-stream-reduce - 将流数据减少为单个值。
-   stream-shift - 返回流可读队列中的下一个缓冲区/对象。
-   stream-assert - 流的断言库。
-   stream-from-promise - 根据 Promise 创建流。
-   exec-stream - 将流传入到子进程。
-   stream-callback – 将流转换为一个回调函数。

### 检测/判断

-   is.js - 微型检查库。
-   is-promise - 测试对象是否看起来像一个 Promises-a+ promise。
-   is-ci - 判断当前环境是否为 CI 服务器。
-   is - JavaScript 类型测试库。
-   is-type-of - Node.js 完整类型判断。
-   is-stream - 判断对象是否为流对象。
-   is-utf8 - 判断 Buffer 对象是否 UTF8 编码。
-   core-util-is - Node.js 核心工具 util.is\* 函数。
-   is-ip - 检查字符串是否为 IP 地址。
-   isstream - 判断对象是否为流对象。
-   is-class - 判断函数是否为 ES6 类(class) 类型。
-   isexe - 检查文件是否可执行文件。
-   is-type - Node.js 核心类型判断。
-   is-core-module - 判断一个说明符 是否为 Node.js 核心模块。
-   is-md5 - JavaScript 实用程序，用于检查字符串是否为 md5 加密。

### 数据校验

-   zod - TypeScript 优先的 Schema 校验
-   validator.js - 字符串校验库。
-   joi - 基于 JavaScript 对象的对象模式描述语言和验证器。
-   yup - 受 joi 启发的极简的对象 Schema 校验。
-   async-validator - 异步校验。
-   class-validator - 基于装饰器属性校验的类校验器。
-   ajv - 最快的 JSON Schema 验证器。支持 JSON Schema draft-04/06/07/2019-09/2020-12 and JSON 类型定义(RFC8927)。
-   Superstruct - 用简单和可组合的方式在 JavaScript 和 TypeScript 中校验数据。
-   v8n - 流畅的 JavaScript 校验库。
-   forgJs - 轻量的 JavaScript 对象校验器。
-   jsonschema - JSON Schema 校验器.
-   validatorjs - 受 Laravel 的校验器启发，在浏览器和 Node.JS 上的数据校验库。
-   is-my-json-valid - 极快的 JSON Schema 校验工具。
-   parameter - 参数校验工具。
-   schema-inspector - 用于净化和验证 JS 对象的强大工具。
-   property-validator - 用于 JavaScript、Node 和 Express 的易用的属性校验工具。

### 函数式编程

-   lodash - 可提供一致性、自定义、性能和其他功能的实用程序库，比 Underscore.js 更好更快。
-   immutable - 不可变的数据集合。
-   RxJS - 用于转换、组合和查询各种数据的函数式响应式库。
-   Ramda - 实用程序库着重于通过自动计算和相反的参数顺序实现的灵活功能组合，避免数据变化。
-   immer - 函数式响应式编程。
-   Bacon.js - 函数式响应式编程。
-   Lazy.js - 类似于 lodash/underline 的工具库，但具有惰性计算，在许多情况下可以转换为卓越的性能.
-   Folktale - 一套用于 JavaScript 中的通用函数编程的库，它允许您编写优雅的、模块化的应用程序，并且 bug 更少及更强的重用性。
-   Kefir.js - 响应式库，专注于高性能和低内存使用。
-   Mout - 该库与其他现有解决方案之间最大的区别是，您可以选择只加载需要的模块/函数，而不需要额外开销。.

### 流程控制

-   Promises
    
    -   Bluebird - Bluebird 是一个功能齐全的 Promise 库，专注于创新功能和性能。
    -   co - 拥有流程控制优势的 Nodejs 终极生成器（支持 thunks、promises 等）。
    -   pify - 将回调式的函数 Promisify 化。
    -   p-map - 并发的 Map 执行 Promise 。
    -   delay - 将 Promise 延迟指定的时间。
    -   thenify - 将一个基于回调的函数 Promise 化。
    -   thenify-all - 将一个对象中所有选中的方法全部 Promise 化。
    -   promise-memoize - 记忆化 Promise 返回函数，带过期和 prefetch 预取功能。
    -   valvelet - 限制 Promise 返回函数的执行率(限流)。
-   可观察对象
    
    -   RxJS - 响应式编程。
    -   zen-observable - 可观察对象的实现。
    -   observable-to-promise - 将可观察对象转化为 Promise.
-   回调函数
    
    -   async - 提供直接、强大的函数们来处理异步问题。
-   管道
    
    -   js-csp - 用于 JavaScript 的顺序通信进程 CSP（如 ClojureScript core.async 或 Go）。
-   其他
    
    -   mz - 将 Node.s Api 现代化转化为当前 ECMAScript 标准（将 child\_process、crypto、dns、fs、readline、zlib 等 Promise 化）。
    -   mz-modules - 与 `mz` 类似，但在世界中封装模块而不是核心 API。

### 控制反转/依赖注入

-   InversifyJS - 功能强大且轻便的控制反转容器。
-   injection-js - 5.1K 中的 JavaScript 和 TypeScript 的依赖注入库。它提取自 Angular 的 ReflectiveInjector，这意味着它设计合理，功能完整、快速、可靠且经过良好测试。
-   power-di - 轻量的依赖注入库。
-   @opensumi/di - 依赖注入工具。

### Shell

-   zx - 用于编写更好脚本的工具。
-   shelljs - 跨平台 Unix shell 命令。
-   execa - 跨平台实现子进程执行 `child_process.{execFile,exec}`。
-   node-windows - Node.js 上支持的 Windows 脚本。如(daemons, eventlog, UAC 等)。
-   shx - Node 的可移植 Shell 命令。
-   clipboardy - 跨平台的复制/粘贴。
-   cross-spawn - 跨平台实现 `child_process.spawn()`。
-   parallelshell - 并行运行多个 shell 命令。
-   clipboard-cli - 跨平台的复制/粘贴。
-   gulp-execa - 在 Gulp 中跨平台命令执行。
-   runscript - 更容易的运行脚本命令。
-   cross-spawn-promise - Promise 化的 cross-spawn。
-   shell-exec - 通过系统 Shell 执行命令。

### 环境

-   dotenv - 从 .env 文件 加载用于 nodejs 项目的环境变量。
-   cross-env - 跨平台设置环境变量。
-   envinfo - 生成关于您的开发环境的报告，用于调试和问题报告。
-   which - 跨平台实现的 Unix `which`.
-   user-home - 跨平台获取用户 home 目录路径。
-   username - 获取当前用户名。
-   osenv - 跨平台环境变量。
-   is-elevated - 检查进程是否以提升的权限运行。

### 事件

-   eventemitter3 - 高性能 EventEmitter.
-   tiny-emitter - 小型 EventEmitter 库 (小于 1k) event emitter library.
-   ee-first - 获取一组 EventEmitter 和 Event 对中的第一个事件，然后对其进行清理。

### 命令行工具

-   框架/解决方案
    
    -   Commander.js - Node.JS 命令行界面完整解决方案。
    -   yargs - 通用可交互命令行工具集合。
    -   oclif - 基于 Heroku 开源 Node.js CLI 框架。
    -   meow - CLI 应用助手。
    -   cac - 用于构建命令行应用的强大框架。
    -   clipanion - 无运行时依赖的类型安全的 CLI 库。
    -   Cliffy - 可交互命令行框架。
    -   common-bin - 基于 yargs 的命令行工具抽象，提供更方便的使用，支持 async/generator。
-   命令行参数解析
    
    -   minimist - 命令行参数解析引擎。
    -   arg - 简单的参数解析。
    -   nopt - Node/npm 参数解析。
    -   argparse - Node.js CLI 参数解析。
    -   yargs-parser - yargs 在使用，优雅参数解析库.
-   Prompt 提示
    
    -   Inquirer.js - 通用可交互命令行工具集合。
    -   prompts - 轻量、美观、用户友好的交互式命令行提示。
    -   Enquirer - 用户友好、直观且易于创建的时尚 CLI 提示。
    -   node-promptly - 简单命令行提示实用程序。
-   进度条
    
    -   progress - Node.js 的灵活 ascii 进度条。
    -   progress-estimator - 打印进度条并估计完成 Promise 所需的时间。
    -   cli-progress - 在命令行/终端应用中轻松的使用进度条。
-   样式
    
    -   chalk - 命令行字符串样式美化工具。
    -   ora - 优雅的命令行 loading 效果。
    -   colors.js - 获取 Node.js 控制台的颜色。
    -   listr - 命令行任务列表。
    -   figlet.js - 用 JavaScript 编写的 FIG，旨在完全实现 FIGfont 规范。
    -   kleur - 使用 ANSI 颜色格式化命令行文本的最快的 Node.js 库。
    -   colorette - 在终端中轻松设置文本的颜色和样式。
    -   qrcode-terminal - 命令行中显示二维码。
    -   boxen - 控制台中创建盒子。
    -   terminal-image - 在终端中展示图片。
    -   log-symbols - 为不同日志级别添加色彩图标。
    -   gradient-string - 终端输出中漂亮的颜色渐变。
    -   figures - Windows 兜底的 Unicode 符号。
    -   terminal-link - 在终端中创建可点击的链接。
    -   snazzy - 将 JavaScript 标准样式格式化为时尚（即时髦）输出。
    -   columnify - 创建适合控制台输出的基于文本的列。 支持单元格。
    -   cli-table3 - 命令行的漂亮 unicode 表。
    -   easy-table - 漂亮的文本表格。
    -   cli-highlight - 终端的语法高亮显示💻✨
    -   treeify - 将 javascript 对象漂亮地打印为树。
    -   kolorist - 使用输入和输出色彩化的小工具。
    -   console-png - 在命令行输出中打印 PNG 图片。
-   编辑器
    
    -   slap - 基于命令行终端的类 Sublime 文本编辑器。
-   其他
    
    -   commitizen - Commitizen 命令行实用程序。
    -   plop - 微型代码模板生成工具，可让整个团队轻松创建具有统一的文件。
    -   update-notifier - 为你的 CLI 应用提供的更新提示。
    -   console-stamp - 为 NodeJS console 方法添加布丁，使其按模式添加时间戳信息。
    -   didyoumean - 简单、优化的 JS 库 和 Node.JS 模块，用于将简短的人为的输入匹配到一个可能性列表中。
    -   console-clear - 跨平台清空控制台。

### Node.js 管理工具

-   nvm - Node.js 版本管理工具。
-   nvm for Windows - Node.js 版本管理工具 Windows 版。
-   n - Node.js 版本管理工具。
-   fnm - 🚀 快速、轻量的 Node.js 版本管理工具，由 Rust 构建。
-   nodenv - 版本管理工具（类似 Ruby 的 rbenv ），它支持自动切换。
-   nave - Node.js 虚拟环境。
-   nvs - Node Version Switcher - 一个跨平台的工具，用于在 Node.js 的版本之间切换。
-   nodeenv - 与 Python 的 virtualenv 兼容的 Node.js 虚拟环境。

### NPM

-   NPM 管理工具
    
    -   pnpm - 快速、节省磁盘空间高效的包管理器。
    -   npm - JavaScript 包管理工具。
    -   yarn - 现代包管理工具，拆分成多个不同的包。
    -   yalc - 更适用的前端 link 工具。
    -   nrm - 快速切换 npm 注册服务商，如 npm、cnpm、nj、taobao。
    -   cnpm - NPM 中国区镜像客户端。
-   package.json
    
    -   read-pkg-up - 读取最近的 package.json 文件。
    -   node-pkginfo - 从 package.json 读取属性的简单方法。
    -   pkg-dir - 查找 npm 包的根目录。
    -   read-pkg - 读取 package.json 文件。
    -   write-pkg - 写入 package.json 文件。
    -   read-package-json-fast - 类似 read-package-json, 但更快。
-   语义化版本
    
    -   semver - NPM 使用的 JavaScript 语义化版本号解析器。
    -   compare-versions - 比较 semver 版本字符串，找出哪个更大，哪个相等，哪个更小。
    -   semver-diff - 获取两个 semver 版本号的区别类型：0.0.1 0.0.2 → patch.
-   NPM 私有部署
    
    -   verdaccio - 私有轻量级的 NPM 镜像。
    -   cnpmjs.org - 企业级私有 NPM 镜像和 Web 界面。
-   工具
    
    -   npm-check-updates - 查找当前 package.json 依赖允许的更新的版本。
    -   concurrently - 并行执行命令，类似 `npm run watch-js & npm run watch-less`但更优。
    -   npm-run-all - 命令行工具，同时运行多个 npm 脚本（并行或串行）。
    -   depcheck - 检查你的 NPM 模块未使用的依赖。
    -   npminstall - 使 `npm install` 更快更容易。
    -   validate-npm-package-name - 校验给定的字符串 是否为 可接受的 npm 包名称。
    -   npm-home - 打开 npm 包页面。
    -   npm-name - 在 npm 上检查软件包名称的可用性。
    -   pacote - 从 npm 注册商下载 tar 压缩文件，并获取包的资源信息。
    -   npm-package-arg - 根据包名解析信息。
    -   npm-registry-fetch - 类型 fetch()函数，但用于 npm 仓库。
    -   npm-updater - 检查 npm 包的更新。

### Monorepo

_(你也许喜欢 awesome-monorepo)_

-   lerna - 用于管理具有多个包的 JavaScript 项目的工具。
-   rush - 可伸缩的 monorepo 构建管理工具。
-   manypkg - ☔️ 为您的 monorepo 提供保护伞

### 文件系统

-   通用
    
    -   fs-extra - 为 `fs` 模块提供额外方法。
    -   graceful-fs - graceful-fs 可以替代 fs 模块，并做了各种改进。
    -   filesize.js - 生成人类可读的文件大小字符串。
    -   memfs - Node.js API 内存文件系统。
    -   fs-jetpack - 完全重新设计的文件系统 API，方便日常使用。
    -   make-dir - 递归创建文件夹，类似 `mkdir -p`。
    -   filenamify - 将字符串转换为有效的文件名。
    -   move-file - 移动文件，甚至可以跨设备工作。
    -   proper-lockfile - 进程间和机器间文件锁实用工具。
    -   istextorbinary - 检查文件是文本文件还是二进制文件。
    -   mkdirp - 递归创建文件夹，类似 `mkdir -p`。
    -   dir-compare - Node JS 文件夹对比。
    -   folder-hash - 为 文件夹或文件 上创建哈希检验码。
    -   lnfs - 强制创建符号链接。类似`ln -fs`.
    -   vinyl-fs - 文件系统的 `Vinyl` 适配器.
-   复制
    
    -   ncp - 使用 Node.js 进行异步递归文件复制。
    -   cpy - 文件拷贝。
    -   copyfiles - 在命令行中复制文件。
-   删除
    
    -   rimraf - 递归删除文件，类似 `rm -rf`。
    -   del - 删除文件/文件夹。
-   临时
    
    -   temp - Node.js 临时文件、文件夹、流。
    -   tempy - 获取随机的临时文件或目录路径。
    -   temp-dir - 获取系统临时文件夹的真实路径。
-   监控
    
    -   watchman - 监视文件和记录，或在更改时触发操作。
    -   chokidar - 最小且高效的跨平台 Watch 库。
    -   watchpack - Watch 文件和文件夹。
-   查找
    
    -   glob - Node.js 版 glob 功能。
    -   globby - 基于 fast-glob，但添加了很多有用的特性。
    -   fast-glob - 非常快速且高效的 Node.js glob 库。
    -   find-up - 通过上级父目录查找文件或目录。
    -   filehound - 灵活流畅的文件系统搜索接口。
    -   node-sync-glob - 通过 glob 模式在本地同步文件和文件夹，包括 watch 选项。

### 解析工具

-   Markdown
    
    -   marked - Markdown 解析器和编译器，专为提高速度而设计。
    -   markdown-it - 支持 100%通用 Markdown 标签解析的扩展&语法插件。
    -   showdown - Markdown 到 HTML 的双向转换器。
    -   remark - Markdown 处理工具。
    -   turndown - 用 JavaScript 编写的 HTML 到 Markdown 转换器。
    -   remove-markdown - 从文本中删除 Markdown 内容。
-   CSV
    
    -   PapaParse - 快速而强大的 CSV（分隔文本）解析器，可以优雅地处理大文件和格式错误的输入。
    -   node-csv - 具有简单 api 的全功能 CSV 解析器，并针对大型数据集进行了测试。
    -   csv-parser - 旨在比其他任何人都快的流式 CSV 解析器。
    -   neat-csv - 快速的 CSV 解析器。
-   YAML
    
    -   js-yaml - 快速的 YAML 解析器。
    -   yaml - YAML 的 JavaScript 解析器和字符串化。
-   XML
    
    -   xml2js - 将 XML 转换为 JavaScript 对象的转换器。
    -   fast-xml-parser - 验证&解析 XML。
    -   xmlbuilder - XML 构建器。
    -   js2xmlparser - 用于将 JavaScript 对象解析为 XML 的流行 Node.js 模块。
-   HTML
    
    -   htmlparser2 - 宽容的 HTML 和 XML 解析器。
    -   parse5 - 用于 Node.js 的 HTML 解析/序列化工具集。 WHATWG HTML 标准（又名 HTML5）兼容。
    -   sanitize-html - 清理用户提交的 HTML，在每个元素的基础上保留列入白名单的元素和属性。 建立在 htmlparser2 上，以提高速度和容忍度。
    -   himalaya - 将 HTML 转化为 JSON 的解析器。
-   CSS
    
    -   PostCSS - CSS 解析工具。
    -   less - Less 动态样式表语言。
-   SQL
    
    -   pgsql-ast-parser - 简单的 Postgres SQL 解析器。
    -   dt-sql-parser - 大数据的 SQL 解析器，用 antlr4 构建。
-   Plist
    
    -   node-bplist-parser - 二进制 plist 文件解析。
-   ini
    
    -   ini - ini 文件解析和序列化。
-   MathJax
    
    -   mathjax-node - MathJax 解析。
-   其他
    
    -   readability - 可读内容提取库，用于 Firefox Reader View 的独立提取版本。

### Git

-   husky - 现代化的本地 Git 钩子使操作更加轻松！
-   isomorphic-git - 用于 Node.js 和浏览器的 纯 JavaScript git 实现！
-   nodegit - libgit2 的 Node.js 绑定版本。
-   js-git - Git 的 JavaScript 实现。
-   degit - Degit 制作 git 存储库的副本。用于构建简单的项目脚手架。
-   simple-git - 一个轻量级的接口，用于在任何 node.js 应用程序中运行 git 命令。
-   gitgraph-node - 在 Terminal 绘制 git 流程图（支持浏览器、React）。
-   pre-commit - 自动在您的 git 储存库中安装 git pre-commit 脚本，该脚本在 pre-commit 上运行您的`npm test`。
-   yorkie - husky 的 Fork，让 Git 钩子变得简单(在 vue3 中使用)
-   git-url-parse - 高级别 git 解析。
-   git-promise - 简单的封装，可运行任何 git 命令，并使用 promise 处理其输出。
-   gittar - 下载/提取 git 仓库 (GitHub, GitLab, BitBucket)，跨平台和优先离线。
-   parse-git-config - 将 `.git/config` 解析为 JavaScript 对象。 同步或异步。
-   remote-git-tags - 从远程仓库中获取标签。
-   giturl - 将 Git 链接转化成 Web 链接。
-   download-git-repo - 下载和提取 Git 仓库 (支持 GitHub, GitLab, Bitbucket)。

### 日志

-   winston - 多传输异步日志记录库。
-   pino - 受 Bunyan 启发的超快日志记录库。
-   signale - 高度可配置的日志工具。
-   bunyan - 一个用于 Node.js 服务的简单快速的 JSON 日志模块。
-   log4js-node - 不同于 Java log4j 的日志记录库。
-   consola - 优雅的 Node.js 和浏览器日志记录库。
-   loglevel - 小巧的轻量级日志记录，添加可靠的日志级别方法来封装任何可用的 console.log 方法。
-   roarr - JSON 日志。
-   storyboard - 一个 Chrome 浏览器插件，用于查看日志。
-   cabin - 提供日志服务和 NPM 包。
-   caterpillar - Caterpillar 是 Deno、Node.js 和 Web 浏览器的终极日志系统。日志级别实现了 RFC 标准。日志条目可以过滤并通过管道传输到各种流，包括多色输出到终端、浏览器的控制台和调试文件。你甚至可以编写自己的转换。
-   fancy-log - 带上时间前缀的日志记录库。
-   captains-log - 通过简单的配置就可以使用的轻量日志记录库。

### 进程管理

-   PM2 - 高级进程管理工具。
-   nodemon - 监视应用程序中的更改并自动重新启动服务器。
-   forever - 简单的 CLI 工具，用于确认提供的代码持续运行。
-   supervisor - 当脚本崩溃时重新启动脚本，或者当\`\*.js'文件更改时重新启动脚本。
-   node-windows - 将脚本作为本机 Windows 服务运行，并登录到事件查看器。
-   node-mac - 将脚本作为本机 Mac 守护进程运行，并登录到控制台应用程序。
-   node-linux - 将脚本作为本机系统服务运行，并登录到 syslog。
-   current-processes - 可获取当前正在运行的进程快照（操作系统无关）。

### 代码校验 和 格式化工具

-   prettier - ❤"有主见"的多语言代码格式化程序。
-   standard - JavaScript 代码规范，自带 linter & 代码自动修正。
-   eslint - 插件化并且可配置的 JavaScript 语法规则和代码风格的检查工具。
-   stylelint - 功能强大现代风格检查工具，帮助你避免错误和强制约定样式风格。
-   lint-staged - 在 Git 暂存文件上运行风格检查工具。
-   commitlint - Git 提交信息风格检查工具。
-   js-beautify - Javascript 美化工具。
-   xo - 带出色默认配置的 JavaScript/TypeScript 代码校验 (基于 ESLint 封装)
-   markdownlint - Markdown/CommonMark 风格检查工具。
-   textlint - Text 和 Markdown 校验和格式化。
-   pretty-quick - 快速美化。
-   dtslint - 基于 TSLint 构建的实用程序，用于对 TypeScript 声明 (.d.ts) 文件进行 linting。
-   lint-md - 用于检查中文 markdown 编写格式规范的核心模块，基于 AST 开发。
-   cz-customizable - 用于 (cz-cli)\[https://github.com/commitizen/\]（或独立 util）的可定制 commitizen 适配器。

### 配置工具

-   node-config - Node.js 应用程序配置。
-   nconf - 可通过文件、环境变量、命令行参数和对象 合并的分层 Node.js 配置。
-   convict - Convict 扩展了配置 node.js 应用程序的标准模式，提供了更健壮且易于访问。
-   rc - 懒人的配置加载器。

### 构建工具

-   webpack - 打包浏览器的模块和资产。
    
-   parcel - 快速，零配置的 Web 应用构建工具。
    
-   gulp - 流式快速构建系统，支持代码而不是配置。
    
-   esbuild - 极快的 JavaScript 打包压缩工具。
    
-   rollup - 新一代的 ES2015 打包构建工具。
    
-   pkg - 将 Node.js 项目打包成可执行文件。
    
-   Grunt - JavaScript 任务执行器。
    
-   Brunch - 前端 web 应用程序构建工具，具有简单的声明性配置、快速的增量编译和自定的工作流。
    
-   FuseBox - 快速构建系统，结合了 webpack，JSPM 和 SystemJS 的强大功能，并具有一流的 TypeScript 支持。
    
-   Broccoli - 快速、可靠的资产管道，支持固定时间重建和紧凑的构建定义。
    
-   ESM
    
    -   Vite - 新一代前端构建工具。
    -   snowpack - 由 ESM 支持的前端构建工具。 即时，轻量级，无捆绑开发。

### 模板引擎

-   Pug - 受 Haml 启发的高性能模板引擎。
-   handlebars.js - Mustache 模板的超集，添加了强大的功能，如 helper 和更高级的 block。
-   mustache.js - 轻量的 JavaScript 模板引擎{{八字须}}。
-   marko - 基于 HTML 的模板引擎，编译成 CommonJS 模块，支持流、异步渲染和自定义标签。
-   art-template - 高性能 JavaScript 模板引擎。
-   nunjucks - 具有继承，异步控制等功能的模板引擎（受 Jinja2 启发）。
-   EJS - 超级简单的模板语言。
-   hogan.js - {{八字须}} 样式的模板语言。
-   doT - 最快简洁的 JavaScript 模板引擎。
-   dustjs - 用于浏览器和服务器的异步 Javascript 模板。
-   jsrender - 轻巧，功能强大且高度可扩展的模板引擎。
-   Twig.js - Twig 模板语言的 JavaScript 实现。
-   hbs - Handlebars 的 Express 版本封装。
-   Juicer - 轻量级 JavaScript 模板引擎。
-   tempo - Tempo 是一个简单，直观的 JavaScript 渲染引擎，使您能够以纯 HTML 格式制作数据模板。
-   xtemplate - 用于浏览器和 Node.js 上的高速，可扩展模板引擎库。支持异步控制，继承，包含，逻辑表达式，自定义函数等。

### Web 框架

-   Express - Web 应用程序框架，为构建单页和多页以及混合 Web 应用程序提供了一组强大的功能。
-   Next.js - React 服务端渲染框架。
    -   blitz - 全栈 React 框架——建立在 Next.js 之上。
-   Meteor - 超简单，无处不在的数据库，在线数据，纯 Javascript Web 框架。 _（你也许会喜欢 awesome-meteor)_
-   Nuxt.js - Vue 服务端渲染框架。
-   Nest -受 Angular 启发的框架，用于构建高效且可扩展的服务器端应用程序。_(你也许会喜欢 awesome-nestjs)_
-   Koa - 由 Express 背后的团队设计的框架，旨在为 Web 应用程序和 API 提供更小，更富表现力和更强大的基础。
    -   _(你也许喜欢 awesome-koa)_
-   sails - Node.js 实时 MVC 框架。
-   Fastify - 快速和低开销的 Web 框架。
-   Hapi - 用于创建应用和服务的框架。
-   Egg - 为企业级框架和应用而生。
    -   _(你也许喜欢 awesome-egg)_
-   Feathers - 基于 Express 精神构建的微服务框架。
-   AdonisJs - 基于依赖注入和 IoC 容器的坚实基础构建的 Node.js 的真正 MVC 框架。
-   LoopBack - 用于创建 REST API 并轻松连接到后端数据源的强大框架。 v4 - v3 -
-   Restify - 使你能够构建正确的 REST Web 服务。
-   ThinkJS - 支持 ES2015 +的框架，WebSockets，REST API。
-   total.js - 使用纯 JavaScript 编写的 Node.js 框架，类似 PHP's Laravel 或 Python's Django 或 ASP.NET MVC
-   Micro - 具有异步方法的简约微服务框架。
-   Midway - 一个面向未来的云端一体 Node.js 框架。
-   Moleculer - 快速而强大的微服务框架。
-   seneca - 编写微服务的工具包。
-   server - 简单而强大的 Node.js 服务器。
-   beidou - NodeJS & React 同构框架，基于 Egg.js 开发。
-   Marble.js - 基于 TypeScript 和 RxJS，用于构建服务端应用的函数响应式框架。
-   ActionHero - 用于为 TCP 套接字，WebSocket 和 HTTP 客户端制作可重用和可扩展的 API 的框架。
-   lad - 最好的 Node.js 框架，由前 Express 和 Koa 团队成员创建。
-   Tinyhttp - 类 Express 更现代更快的 Web 框架。
-   daruk - 基于 typescript 的 Node.js web 框架。
-   Hemera - 使用以下工具编写可靠且容错的微服务 NATS。
-   diet - 一个小巧、快速、模块化的 node.js web 框架。适用于制作快速、可扩展的应用程序和 API。
-   restana - 用于构建 REST 微服务的超快速和简约的框架。
-   CabloyJS - 一款自带工作流引擎的 Node.js 全栈框架。
-   malagu - Malagu 是基于 TypeScript 的 Serverless First、可扩展和组件化的应用框架。
-   Zeronode - 最小的构建块，可实现可靠且容错的微服务。
-   hyper-express - 高性能 web 服务器，具有简单易用的 API，基于 uWebsockets.js。

### GraphQL

-   _(你也许喜欢 awesome-graphql)_

### 内容管理系统 (CMS)

-   Ghost - 用于专业发布的无头 Node.js CMS。
-   Strapi - 用于构建强大 API 的内容管理框架 (headless-CMS)。
-   KeystoneJS - 基于 Express 和 MongoDB 的 CMS 和 Web 应用程序平台。
-   AdminBro - 为您的所有模型自动生成带有 增删查改(CRUD) 的管理面板。
-   ApostropheCMS - 基于 Express 和 MongoDB，拥有直观的内容编辑和管理的内容管理系统。
-   Tipe - 面向开发人员的下一代 API 优先 CMS。使用离线原型和内置编辑器从 GraphQL Schema 中 生成 API 优先 的 CMS。
-   Factor - Vue.js 仪表板框架 和 无头 CMS。

### 静态网站生成 & 博客

-   gatsby - 使用 React 构建快速、现代的应用程序和网站。
-   hexo - 使用 Node.js 的快速，简单，强大的博客框架。
-   vuepress - 极简的 Vue 静态网站生成工具。
-   netlify-cms - 基于 Git 的静态网站生成工具。
-   react-static - 渐进式的 React 静态网站生成工具。
-   gridsome - Vue.js 静态网站生成工具。
-   vitepress - Vite & Vue.js 静态网站生成工具。
-   scully - Angular 应用程序的静态站点生成器。

### 文档生成

-   Docusaurus - 使用 React 和 Markdown 并具有翻译和版本控制功能的文档站点生成器。
-   docsify - API 文档生成器。
-   JSDoc - API 文档生成器，类似于 JavaDoc 或 PHPDoc。
-   documentation.js - API 文档生成器，支持 ES2015+和流程注释。
-   Docco - 文档生成器，该生成器生成一个 HTML 文档，该文档显示与代码混合的注释。
-   docute - 毫不费力的文档，做就对了。
-   ESDoc - 针对 ES2015 的文档生成器，附加测试代码并衡量文档覆盖范围。
-   groc - 文档生成，本着文学编程的精神。

### 接口管理

-   yapi - YApi 是一个可本地部署的、打通前后端及 QA 的、可视化的接口管理平台。
-   swagger - Swagger NodeJS 版。将符合 Swagger 规范 的 API 动态生成精美的文档。
-   rap2 - 阿里妈妈前端团队出品的开源接口管理工具 RAP 第二代。

### 桌面应用程序

-   Electron - 使用 Web 技术构建跨平台的桌面应用程序。 _(你也许喜欢 awesome-electron)_
-   nw.js - 使用 Web 技术编写应用程序的新方法，并直接从 DOM/WebWorker 调用所有 Node.js 模块。

### 实时通信

-   Socket.io - 实现基于事件的实时双向通信。
-   ws - 简单易用，速度极快，经过全面测试的 WebSocket 客户端和服务器 Node.js 通信库。
-   µWebSockets - 高度可扩展的 WebSocket 服务器和客户端库。
-   MQTT.js - MQTT 客户端-基于 Pub-sub 的消息协议，用于 TCP / IP。
-   SocketCluster - 可扩展的 HTTP + WebSocket 引擎，可以在多个 CPU 内核上运行。
-   Faye - 基于 Bayeux 协议的实时客户端-服务器消息总线。
-   Primus - 实时框架的抽象层，以防止模块锁定。
-   sockette - 最可爱 WebSocket封装。 🧦
-   engine.io - 基于传输的跨浏览器/跨设备双向通信层的实现 Socket.IO。
-   SockJS-node - WebSocket Node.js 服务端实现。
-   Aedes - 可以在任何流服务器上运行的准系统 MQTT 服务器。
-   nodejs-websocket - 一个 Websocket 服务端和客户端模块。
-   rpc-websockets - 通过 WebSocket 实现 JSON-RPC 2.0。
-   deepstream.io - 可扩展的实时通信微服务框架。
-   isomorphic-ws - WebSocket 的同构实现。
-   Kalm - 低级套接字路由器和中间件框架。

### 任务队列

-   bull - 持久作业和消息队列。
-   amqp\- AMQP 0-9-1 rabbit 消息队列连接库。
-   kafka-node\- Apache Kafka 0.8 kafka 客户端。
-   bee-queue - 高性能的 基于 Redis 的任务队列。
    -   arena - bee-queue 的交互式 UI 仪表盘。
-   kafkajs - A modern Apache Kafka client for node.js.
-   bullmq - BullMQ - 基于 Redis 的 NodeJS 的高级消息队列。
-   rsmq - 基于 Redis 的消息队列.
-   sqs-consumer - 在没有样板文件的情况下构建基于 Amazon 简单队列服务（SQS）的应用程序.
-   node-resque - Redis 支持的作业队列.
-   better-queue - 当你无法使用 Redis 时，简单高效的作业队列.
-   RedisSMQ - 具有实时监控功能的简单高性能 Redis 消息队列.
-   idoit - 具有高级作业控制的 Redis 支持的作业队列引擎.

### 定时任务

-   node-schedule - 类 Cron 和不类似 Cron 的 Node.js 定时任务。
-   agenda - Node.js 轻量级定时任务。
-   node-cron - 允许执行定时任务的工具。
-   cron-parser - 用于解析 crontab 指令的 Node.js 库。

### 调试

-   node-inspector - 基于 Blink 开发者工具的调试器。
-   ndb - Chrome DevTools 调试体验改进工具。
-   debug - 轻量调试工具。
-   ironNode - 支持 ES2015 的 Node.js 开箱即用的调试器。
-   why-is-node-running - 当 Node 因不明原因继续运行时，使用的分析工具。
-   llnode - 事后分析工具，使您可以检查对象并从崩溃的 Node.js 进程中获取信息。
-   njsTrace - 检测和跟踪您的代码，查看所有函数调用、参数、返回值以及在每个函数中花费的时间。
-   locus - Locus 是一个调试模块，它允许您通过 REPL 在运行时执行命令。
-   stackman - 使用代码摘录和其他优点增强错误堆栈跟踪。
-   NiM - 管理 DevTools 调试工具流。
-   ctrace - 将系统调用信息和信号，以更良好的格式显示和扩展。
-   vstream - 检测流。

### 性能分析/诊断

-   Clinic.js - Clinic.js 诊断 Node.js 性能问题。
-   0x - 火焰图分析。
-   node-heapdump - 存储 V8 内存堆使用情况，以供以后诊断。
-   leakage - 内存写入泄漏测试。
-   flamebearer - V8 和 Node 的快速火焰图工具🔥。
-   v8-profiler - V8 性能探测器。
-   node-memwatch - 一个 NodeJS 库，用于监视您的内存使用情况，并发现和隔离泄漏。
-   pidusage - 通过 PID 获取 CPU 使用百分比和内存用量。
-   v8-analytics - V8 引擎 CPU 和 堆内存分析。
-   thetool - 以 Chrome DevTools 友好格式为您的应用捕获不同的 CPU，内存和其他配置文件。
-   flamegraph - 在 Node.js 或浏览器中生成火焰图。
-   v8-profiler-next - V8 性能探测器。
-   cpu-memory-monitor - CPU 和内存监视器，自动转储。

### 性能优化

-   v8-compile-cache - 将 require 的 V8 编译的结果自动持久缓存化。

### 应用性能监控 (APM)

-   解决方案
    
    -   easy-monitor - 企业级 Node.js 应用性能监控和在线故障定位解决方案。
    -   webfunny\_monitor - Webfunny 是一款轻量级的前端监控系统，也是一款前端性能监控系统，无埋点监控前端日志，实时分析前端健康状态。
-   中间件
    
    -   swagger-stats - 跟踪 API 调用并监控 API 性能、运行状况和使用指标。
-   客户端
    
    -   prom-client - Prometheus 代理。
    -   apm-agent-nodejs - Elastic APM Node.js 代理。
    -   dd-trace-js - Datadog APM 客户端。
    -   skywalking-nodejs - Apache SkyWalking Node.js 代理

### 论坛

-   NodeBB - 基于 Node.js 的现代 Web 论坛。
-   nodeclub - Nodeclub 是使用 Node.js 和 MongoDB 开发的社区系统

### 数据库

-   驱动
    
    -   MySQL - MySQL 客户端。
    -   redis - 高性能的 Node.js Redis 客户端。
    -   PostgreSQL - PostgreSQL 客户端。
    -   MongoDB - 官方 MongoDB 驱动。
    -   ioredis - Redis 客户端。
    -   LevelUP - LevelDB 客户端。
    -   mysql2 - 快速 兼容 mysqljs/mysql 库 的 mysql 驱动程序。
    -   rethinkdbdash - RethinkDB 的高级 Node.js 驱动程序，带有连接池、支持流等。
    -   couchdb-nano - 官方 CouchDB 客户端。
    -   Couchbase - Couchbase 客户端（官方）。
    -   mariadb - MariaDB Connector/Node.js 用于将在 Node.js 上开发的应用程序连接到 MariaDB 和 MySQL 数据库。
    -   Aerospike - Aerospike 客户端。
-   ODM / ORM
    
    -   Sequelize - 多方 ORM。 支持 PostgreSQL，SQLite，MySQL。
        -   sequelize-typescript - Sequelize 装饰器和一些其他功能。
    -   TypeORM - PostgreSQL，MariaDB，MySQL，SQLite 等的 ORM。
    -   Mongoose - 优雅的 MongoDB 对象建模。
        -   typegoose - Typegoose - 使用 TypeScript 类定义 Mongoose 模型。
    -   Prisma - 支持 PostgreSQL, MySQL & SQLite，自动生成、类型安全的 query builder。
    -   Neuledge - 为数据建模、业务逻辑表示和模式验证提供最先进工具的数据库通用语言。
    -   Bookshelf - Backbone.js 风格的 PostgreSQL，MySQL 和 SQLite3 的 ORM。
    -   Objection.js - 基于 SQL 查询生成器 Knex 的轻量级 ORM。
    -   Waterline - 与数据存储区无关的工具，可大大简化与一个或多个数据库的交互。
    -   Massive - PostgreSQL 数据访问工具。
    -   pg-promise - 用于使用 Promise 的本机 SQL 的 PostgreSQL 框架。
    -   MikroORM - 基于数据映射器，工作单元和身份映射模式的 TypeScript ORM。 支持 MongoDB，PostgreSQL，MySQL 和 SQLite。
    -   slonik - 具有严格类型，详细日志记录和断言的 PostgreSQL 客户端。
    -   OpenRecord - PostgreSQL，MySQL，SQLite3 和 RESTful 数据存储的 ORM。 类似于 ActiveRecord。
    -   leoric - 用于 MySQL, PostgreSQL, and SQLite 的 ORM。
    -   Sutando - ActiveRecord 风格的 ORM, 基于 Knex, 支持 MySQL, PostgreSQL, SQLite 等多种数据库。
-   Query builder
    
    -   Knex - PostgreSQL，MySQL 和 SQLite3 的查询构建器，旨在灵活，可移植且易于使用。
-   SQL
    
    -   sqlstring - 简单 SQL 转义和格式，用于 MySQL。
-   列式数据库
    
    -   clickhouse - 用于客户端连接 ClickHouse。
-   数据库实现
    
    -   AlaSQL.js - 用于浏览器和 Node.js 的 JavaScript SQL 数据库。 处理传统的关系表和嵌套的 JSON 数据 (NoSQL)。 从 localStorage、IndexedDB 或 Excel 导出、存储和导入数据。
-   其他
    
    -   Lowdb - 用于小型项目的微型本地 JSON 数据库（支持 Node、Electron 和浏览器）。
    -   NeDB - 用于 Node.js、nw.js、Electron 和浏览器的嵌入式持久数据库或内存数据库。
    -   sharedb - 基于操作转换 (OT) 的实时数据库后端。
    -   Keyv - 支持多个后端的简单键值(KV)存储。
    -   pg-mem - 内存 PostgreSQL 实例。
    -   Mongo Seeding - 使用 JavaScript 和 JSON 文件填充 MongoDB 数据库。
    -   @databases - 使用普通 SQL 查询 PostgreSQL、MySQL 和 SQLite3，而不会导致 SQL 注入 的风险。
    -   Finale - 基于 Sequelize 模型生成 RESTful 接口。
    -   database-js - 类似 JDBC 连接 的多个数据库连接封装。

### 缓存

-   lru-cache - 最近最少使用的缓存（LRU）实现。
-   node-cache - Node.js 内存缓存模块。
-   memcached - 功能齐全的 Memcached Node.js 客户端库。 考虑到扩展性，因此它将支持 Memcached 群集和一致的哈希。
-   node-cache-manager - Node.js Cache 模块。
-   quick-lru - 简单的 “最近最少使用” (LRU) 缓存.
-   hashlru - 更轻量更快的 LRU 算法。
-   flat-cache - 一个傻瓜般简单的键/值存储使用文件来持久化数据。
-   ylru - 基于 hashlru 添加过期时间，允许空值。

### 搜索引擎/分词

-   elasticsearch-js - 官方 Elasticsearch 客户端库。
-   nodejieba - "结巴"中文分词的Node.js版本。
-   @node-rs/jieba - 使用 Rust 开发 和 N-API 实现的 nodejs jieba.
-   elasticsearch-js-legacy - 适用于 Node.js 和浏览器的旧版 Elasticsearch 客户端库。

### Serverless

-   serverless - 无服务器框架 – 使用 AWS Lambda、Azure Functions、Google CloudFunctions 等无服务器架构构建 Web、移动和 IoT 应用程序。
-   @midway/faas - Midway FaaS 是用于构建 Node.js 云功能的 Serverless 框架。
-   malagu - Malagu 是基于 TypeScript 的 Serverless First、可扩展和组件化的应用框架。

### 自动化 & 机器人流程自动化 - RPA

-   puppeteer - 无头 Chrome Node.js API。
-   playwright - 使用单一 API 自动操作 Chromium, Firefox and WebKi。
-   phantomjs - 脚本化无头浏览器。
-   appium - iOS, Android, and Windows Apps 自动化。
-   wechaty - 会话 RPA SDK。
-   robotjs - Node.js 桌面自动化。
-   pageres - 网页截图。
-   nut.js - 使用 Node.js 进行原生 UI 测试/控制

### 测试相关

-   断言库
    
    -   chai - 基于行为驱动开发(BDD)和测试驱动开发(TDD)理念的 Node.js 和浏览器断言库，可与任何 JavaScript 测试框架集成。
    -   power-assert - 使用标准 assert 接口提供的描述型断言消息。
    -   expect.js - 适用于 Node.JS 和浏览器的简约 BDD 风格的断言库。
    -   should.js - Node.JS 的行为驱动开发(BDD)风格断言库。
    -   unexpected - Unexpected - 可扩展的 BDD 断言工具包。
    -   better-assert - C 语言风格的 Node.js 断言，将表达式字符串报告为错误消息。
    -   http-assert - 带状态码的断言。
-   假数据生成
    
    -   faker.js - 在 Node.js 和浏览器中生成大量逼真的假数据。
    -   casual - JavaScript 假数据生成。
    -   fony - 一个简单的命令行工具，从字符串模板中生成假数据。
-   Mock
    
    -   Mock.js - 浏览器和 Node 均可用，支持自定义 schema 和 随机数据。
    -   Nock - HTTP mock 和期望。
    -   Sinon.JS - 通过间谍函数(spies), 目标函数替换（stubs）和 mocks 功能提供的 Mock 库。
    -   mm - 简单但灵活的 mock(或者叫 stub) 包, mock 伴侣。
-   Mock 服务
    
    -   json-server - 在不到 30 秒的时间内获得具有零编码的完整伪造的 REST API。
    -   msw - 顺畅的 REST/GraphQL Mock 库，适用于 Node 和浏览器 !\[https://img.shields.io/github/stars/mswjs/msw.svg?style=social&label=Star\]
    -   easy-mock - 可视化，并且能快速生成模拟数据的持久化服务。
    -   miragejs - 用于构建、测试和共享您的 JavaScript 应用程序的客户端服务。
    -   pretender - 具有良好路由 DSL 的 Mock 服务器库。
    -   http-fake-backend - 通过可配置的路由，提供 JSON 文件或 JavaScript 对象来构建伪造的后端。
    -   smoke - 具有记录功能的，简单但功能强大的基于文件的 Mock 服务器。
-   UI 录制和播放
    
    -   rrweb - 记录和播放 Web 操作。
    -   uirecorder - UI Recorder 是一款面向多端的 UI 自动化录制工具。
-   端到端的测试(E2E)
    
    -   cypress - 对浏览器中运行的任何东西进行快速、简单和可靠的测试。
    -   nightwatch - 用 Node.js 编写，并使用 Webdriver API 的端到端测试框架。
    -   Detox - 用于移动APP的灰盒端到端测试和自动化框架。
    -   CodeceptJS - Node.js 端到端测试框架。
-   测试框架
    
    -   jest - 愉悦的 JavaScript 测试。
    -   mocha - 简单、灵活、有趣的功能丰富的 Node.js 和浏览器测试框架。
    -   ava - 面向未来的测试运行程序。
    -   jasmine - 简单的 Node.js 和浏览器测试框架。
    -   supertest - 使用流畅的 API，基于 Super-agent 库测试 Node.js HTTP 服务器。
    -   node-tap - 用于 Node.js 测试任何协议的工具。
-   覆盖率
    
    -   istanbul - 覆盖率测试工具。
    -   nyc - Istanbul 的命令行工具。
    -   c8 - 使用 Node.js 的内置覆盖率输出覆盖率报告。
    -   node-coveralls - 借助持续集成服务(Travis CI 或 Jenkins) 向用户报告自动测试的测试覆盖率；为 README 添加一个很酷的覆盖率按钮。
    -   codecov - NodeJS 中代码覆盖率报告上载器。
-   基准/性能测试
    
    -   autocannon - 用Node.js编写的快速HTTP/1.1基准测试工具。
    -   artillery - 负载测试。
    -   Benchmark.js - 基准测试库，支持高分辨率计时器并返回具有统计意义的结果。
    -   matcha - 基准测试的简化方法。
    -   benny - 一个非常简单的 JS/TS 库基准测试框架。
    -   node-wrk - Wrk 负载测试工具 Node.js 版封装。
-   解决方案
    
    -   macaca - 多端自动化解决方案。_（你也许会喜欢 awesome-macaca)_

### 办公软件

-   Excel
    
    -   sheetjs - 电子表格数据工具箱(npm: xlsx)。
    -   exceljs - Excel 工作表管理工具。
    -   xlsx-populate - Excel XLSX 生成和解析工具，可运行在 Node 和浏览器。
-   Word
    
    -   officegen - 使用 Javascript，生成可打开 Word（docx）、PowerPoint（pptx）和 Excel（xlsx）的 XML 文件（需 Microsoft Office 2007 及更高版本），输出是一个 stream。
    -   Mammoth - 将 Word 文档(.docx 文件)转化为 HTML。
    -   docx - 通过良好定义的 API,在 NodeJS 和浏览器中，使用 JS/TS 轻松的生成 docx 文件。
-   PDF
    
    -   jsPDF - 使用 JavaScript 生成 PDF 文件的库。
    -   PDFKit - 在 Node.js 和浏览器中生成 PDF 的库。
    -   percollate - 一个命令行工具，可将网页转换为漂亮的，可读的 PDF，EPUB 或 HTML 文档。
    -   pdf-lib - 在任意 JavaScript 环境中创建和修改 PDF 文档。
    -   pdf2json - PDF 文件解析器，它将 PDF 二进制文件转换为基于文本的 JSON。
-   PPT
    
    -   nodeppt - Web 端展示端 PPT 工具。

### 操作系统识别

-   systeminformation - 获取硬件和软件系统信息。
-   is-wsl - 判断当前是否是否为 WSL (适用于 Linux 的 Windows 子系统)。
-   os-name - 获取当前操作系统的名字。
-   getos - 获取当前操作系统名称，包括 Linux 的发行版名称。
-   is-windows - 判断当前系统是否为 Windows。

### 文件压缩解压

-   jszip - 使用 JavaScript 创建、读取、编辑.zip 文件。
-   pako - 高速 zlib 实现，适用于浏览器和 Node.js。
-   adm-zip - 使用 JavaScript 创建、读取、编辑.zip 文件。
-   node-tar - 快速且功能齐全的 Tar。
-   yauzl - Node.js unzip 解压库。
-   unzipper - 使用流的 Node.js 跨平台解压缩。
-   tar-fs - tar-fs 允许您将目录打包到 tar 格式压缩包中，并将 tar 格式压缩包提取到目录中。
-   extract-zip - 用纯 JavaScript 编写的 Zip 提取。 将 zip 解压缩到目录中。
-   compressing - 压缩和解压缩你所需的一切。
-   yazl - Node.js zip 压缩库。
-   7zip - Windows 包压缩/解压 - 7zip。

### 最小化

-   UglifyJS - JavaScript 压缩工具。
-   imagemin - Image 压缩工具。
-   babel-minify - 基于 Babel 工具链的 ES6+ 压缩库。
-   cssnano - 建立在 PostCSS 生态系统之上模块化的压缩工具。
-   clean-css - CSS 压缩工具。
-   minimize - HTML 压缩工具。
-   strip-css-comments - CSS 注释剔除工具。

### 源码混淆/保护

-   javascript-obfuscator - 一个强大的 JavaScript 和 Node.js 混淆器。
-   bytenode - 用于 Node.js 的极简字节码编译器。它真正将你的 JavaScript 代码编译成 V8 字节码，这样你就可以保护你的源代码。

### 邮箱

-   Nylas Mail - 构建在现代 Web 技术的高扩展性邮件客户端程序。
-   Nodemailer - 使用 Node.js 轻松发送电子邮件。
-   Email Templates - 创建、预览和发送自定义电子邮件模板。
-   emailjs - 向任何 SMTP 服务器发送带有附件的文本/HTML 电子邮件。
-   mjml - 旨在减少创建响应电子邮件的痛苦的标记语言。
-   preview-email - 自动打开浏览器以预览使用 Nodemailer 发送的 Node.js 电子邮件消息。

### 网络

-   IP
    
    -   node-ip - NodeJS IP 地址工具。
    -   public-ip - 非常快的获取你的公网 IP 地址。
    -   request-ip - 在服务器中获取请求的 IP 地址。
    -   ipaddr.js - JavaScript 中的 IP 地址操作库。
    -   internal-ip - 获取您的内网 IP 地址。
    -   ipify - 获取你的公网 IP 地址。
    -   address - 获取当前机器 IP 地址和 MAC 地址。
-   端口
    
    -   node-portfinder - 在当前机器上查找开放端口 或 域套接字的简单工具。
    -   get-port - 获取一个可用的端口。
    -   detect-port - 端口探测的 Node.JS 实现。
-   隧道代理
    
    -   localtunnel - Localtunnel 将您的本地主机公开给全世界，以便于测试和共享！
    -   node-tunnel - 用于隧道代理的 HTTP/HTTPS 代理。
    -   tunnel-agent - HTTP 隧道代理。以前是 mikeal/request 的一部分，现在是一个独立的模块。
-   其他
    
    -   netcat - 纯 JS 中的 Netcat 端口。
    -   getmac - 获取电脑的 MAC 地址。
    -   DHCP - DHCP 客户端和服务器。
    -   default-gateway - 获取默认网络网关(跨平台)。

### HTTP

-   请求库
    
    -   axios - 基于 Promise 的 HTTP 客户端（也可以在浏览器中工作）。
    -   superagent - HTTP 请求库。
    -   got - 更好的基于内建“http”模块接口实现。
    -   node-fetch - Node.js 的 `window.fetch` 实现。
    -   isomorphic-fetch - 同构的 fetch api, 用于Node 和浏览器。
    -   undici - 一个 HTTP/1.1 客户端，从头开始为 Node.js 编写。
    -   needle - 灵活，基于流的 HTTP Node.js 客户端请求库。支持 proxy，iconv，cookie，deflate 和 multipart。
    -   urllib - 在复杂世界中请求 HTTP/HTTPS 的 URL。
    -   phin - Node HTTP client.
    -   gotql - 基于got构建的 GraphQL 请求库。
    -   wreck - HTTP 客户端工具。
    -   cacheable-request - 使用符合 RFC 的缓存封装的本机 HTTP 请求库。
    -   gh-got - 基于"got"封装，与 GitHub API 更方便的交互。
    -   flashheart - REST 客户端。
-   信息提取
    
    -   metascraper - 使用 Open Graph、Microdata、RDFa、Twitter Cards、JSON-LD、HTML 等从网站获取统一的元数据。
-   服务端库
    
    -   http-server - 零配置的命令行 Http 服务端。
    -   anywhere - 随启随用的静态文件服务器。
-   Mock 服务
    
    -   json-server - 在不到 30 秒的时间内获得具有零编码的完整伪造的 REST API。
    -   easy-mock - 可视化，并且能快速生成模拟数据的持久化服务。
    -   miragejs - 用于构建、测试和共享您的 JavaScript 应用程序的客户端服务。
    -   http-fake-backend - 通过可配置的路由，提供 JSON 文件或 JavaScript 对象来构建伪造的后端。
    -   smoke - 具有记录功能的，简单但功能强大的基于文件的 Mock 服务器。
-   代理
    
    -   http-proxy - HTTP 代理。
    -   http-proxy-middleware - ⚡用于 connect，express 和 browser-sync 的单线 Node.js Http 代理中间件。
    -   https-proxy-agent - HTTP(S) 代理 `http.Agent`实现。
    -   global-agent - 可以使用环境变量配置的全局 HTTP/HTTPS 代理。
    -   fast-proxy - Node.js 框架，使您可以将 http 请求转发到另一个 HTTP 服务器。 支持的协议：HTTP，HTTPS，HTTP2。
    -   argo - 一个可扩展的异步 HTTP 反向代理和源服务器。
-   下载
    
    -   download - 轻松下载和提取文件。
    -   nugget - 使用 Node.js 编写的极简主义 wget clone。 HTTP GET 文件并将其下载到当前目录。

### 限流

-   rate-limiter-flexible - 在单进程 或 分布式环境中 使用原子增量按键计数和限制请求。

### 验证

-   Passport - 简单的身份验证。
-   Grant - 适用于 Express，Koa，Hapi，Fastify，AWS Lambda，Azure，Google Cloud，Vercel 等的 OAuth 程序。
-   permit - 用于构建 Node.js API 的非标准认证库。

### 授权 / 鉴权

-   jsonwebtoken - JsonWebToken Node.JS 实现
-   CASL - 同构授权用于可视化界面和 API。
-   node-casbin - 支持访问控制模型（如 ACL，RBAC 和 ABAC）的授权库。
-   jose - 通用的“JSON Web 几乎所有东西” —— JWA、JWS、JWE、JWT、JWK，0 依赖
-   basic-auth - 通用基础身份验证授权头字段解析器。
-   selfsigned - 使用 Node.js 生成自签名证书。

### 分布式

-   redlock - 一个高可用的 Redis 分布式锁实现。
-   node-consul - Consul 客户端.
-   node-zookeeper-client - 纯 JavaScript ZooKeeper 客户端。

### 序列化

-   protobuf - Protocol Buffers 实现。
-   hessian.js - JavaScript hessian 二进制 web 服务协议实现，支持与 java 通信。
-   snappy - Google 的 Snappy 压缩库的原生绑定（Native bindings）。
-   compactr - Compactr 协议的实现。

### RPC

-   grpc-js - 纯 JavaScript gRPC 客户端。
-   thrift - Apache Thrift Node.js 实现.
-   jayson - Jayson 是用于 Node.js 的简单但功能强大的 JSON-RPC 2.0 / 1.0 客户端和服务器。
-   sofa-rpc-node - SOFARPC Node 是高性能、高可扩展性、产品级 Node.js RPC 框架。

### 服务端 DOM

-   cheerio - 运行在服务器端，快速、灵活和精益的 jQuery 核心功能实现。
-   jsdom - Node.js 版 Web 标准实现。
-   domino - 基于 Mozilla 的 dom.js 的服务器端 DOM 实现。

### 爬虫

-   node-crawler - NodeJS Web 爬虫 + 服务端 jQuery。
-   x-ray - 具有分页的 Web 抓取爬虫。
-   headless-chrome-crawler - 使用 Chrome 无头浏览器的分布式爬虫。
-   node-osmosis - Node.js 的 HTML / XML 解析器和 Web 抓取工具。
-   scrape-it - 适用于人类的 Node.js 抓取工具。
-   scraperjs - 完整而多功能的 Web 抓取器。
-   simplecrawler - 事件驱动的 Web 爬虫。
-   web-scraper-chrome-extension -实现为 Chrome 插件的 Web 数据抽取工具。
-   webster - 一个可靠的 Web 爬虫框架，可以在网页中抓取 Ajax 和 js 呈现的内容。
-   supercrawler - 定义自定义处理程序以解析内容。 遵守 robots.txt，速率限制和并发限制。
-   Squidwarc - 高保真度，用户可编写脚本的归档爬虫程序，使用带头或不带头的 Chrome 或 Chromium。
-   js-crawler - 适用于 Node.JS 的 Web 爬虫，同时支持 HTTP 和 HTTPS。

### AST

-   解析器
    
    -   babel-parser - JavaScript 解析器。
    -   antlr - ANTLR (ANother Tool for Language Recognition)是一个用于阅读、处理、执行和翻译结构化文本或二进制文件的强大的解析生成器。
    -   acorn - 小巧、快速的 JavaScript 解析器。
    -   esprima - 高性能、符合 ECMASCRIPT 标准的解析器。
    -   recast - JavaScript 语法树转换器，非破坏性漂亮 print 和自动 source map 生成器。
    -   nearley - JavaScript 的简单、快速、功能强大的解析工具集。
    -   espree - 与 Esprima 兼容的 JavaScript 解析器。
    -   csstree - 基于 W3C 标准和浏览器标准实现，包含快速详细的解析器、遍历器、生成器、词法解析的 CSS 工具集。
    -   es-module-lexer - 低开销的词法分析器，专门用于 ES 模块快速分析解析。
-   遍历
    
    -   acorn-walker - 小巧、快速的 JavaScript 解析器。
    -   estraverse - ECMAScript JS AST 遍历功能。
-   代码生成
    
    -   escodegen - ECMAScript 代码生成。
    -   astring - 🌳 小巧快速的 JavaScript 代码生成器（通过 ESTree 兼容的 AST）。
-   JavaScript 解释器
    
    -   JS-Interpreter - JavaScript 中沙箱解释器。
    -   jsjs - 简易的 JavaScript 元循环解释器。
    -   sval - 使用 JavaScript 编写的 JavaScript 解释器。
    -   notevil - 像内置的 javascript eval() 方法一样执行 javascript，但安全。
-   其他
    
    -   astexplorer - 使用多种解析器的 AST Web 可视化工具。
    -   ts-morph - Typescript编译器API的上层封装,使得操纵TS/JS代码更加简单。
    -   estree-walker - 用于遍历 ESTree 兼容树的 AST。
    -   periscopic - 用于分析符合 ESTree 的 AST 的作用域的工具。

### WebAssembly

-   webassembly - 用于生成和运行 WebAssembly 模块的最小工具包和运行时。

### 设计稿转代码（D2C）

-   psd.js - 在 Node.js 和浏览器中解析 Photoshop PSD 文件。

### 沙箱

-   vm2 - Node.js 高级虚拟机/沙箱。
-   sandbox - 用于 Node.js 漂亮的 JavaScript 沙箱。
-   safeify - Safeify 可让 Node 应用安全的隔离执行非信任的用户自定义代码。

### 硬件

-   johnny-five - 基于 Firmata 的 Arduino 框架。
-   serialport - 访问串行端口以进行读写。
-   usb - USB 库。
-   onoff - GPIO 访问和中断检测.
-   pigpio - 树莓派（Raspberry Pi）上的快速 GPIO，PWM，伺服控制，状态更改通知和中断处理。
-   node-escpos - ESC/POS 打印机驱动程序。
-   i2c-bus - I2C 串行总线访问。
-   gps - NMEA 解析器，用于处理 GPS 接收器。
-   node-bluetooth - Node.js 的蓝牙串口通信。
-   spi-device - SPI 串行总线访问。

### 物联网 IoT

-   zetta - 面向物联网的 API 优先的开源软件平台。
-   iot-nodejs - 用于使用 nodejs 连接到 IBM Watson IoT 的客户端库和示例。

### 机器学习 和 神经网络

-   tfjs - 一个 WebGL 加速的 JavaScript 库，用于训练和部署 ML 模型（Tensorflow 官方）。
-   netron - 神经网络、深度学习和机器学习模型的可视化工具。
-   face-api.js - 可在浏览器和 nodejs 中，使用 tensorflow.js 进行人脸检测和人脸识别的 JavaScript API。
-   brain.js - 基于模型训练的神经网络 JS 库，支持浏览器和 Node.js。
-   opencv - OpenCV 是一个计算机视觉库——通过在 Node.js 中与原生接口交互，我们可以在 js 中获得强大的实时视觉能力。
-   pipcook - 为 Web 开发者提供的机器学习平台。
-   onnxjs - 使用 JavaScript 运行 ONNX 模型。
-   tensorflow-nodejs - TensorFlow Node.js 为 Node.js 用户提供常用的 JavaScript 语言绑定和高级 API。

### 自然语言处理

-   compromise - 自然语言处理。
-   natural - 自然语言设施。
-   nlp.js - 构建机器人，具有实体提取、情感分析、自动语言识别等功能。
-   franc - 检测文本使用的语言。
-   sentiment - 基于 AFINN 的 Node.js 情感判断库。
-   retext - 一个可扩展的自然语言系统。
-   leven - 使用 Levenshtein 距离算法测量两个字符串之间的差异。

### GPT

-   chatgpt - 官方 ChatGPT API 的 Node.js 客户端。🔥
-   @waylaidwanderer/chatgpt-api - ChatGPT 和 Bing AI 的客户端实现。 可用作 Node.js 模块、REST API 服务器和 CLI 应用程序。
-   openai - OpenAI API 的 Node.js 库。

### OCR

-   tesseract.js - 100 多种语言的纯 Javascript OCR。
-   ocrad.js - 通过 Emscripten 实现的 JavaScript 的 OCR
-   Parsr - 将 PDF、文档和图像转换为丰富的结构化数据。

### 比特币

-   GitTorrent - 使用 BitTorrent 和比特币的 GitHub 去中心化。
-   bitcoinjs-lib - 一个用于 node.js 和浏览器的 javascript 比特币库。
-   bitcore - 比特币和基于区块链的应用程序的全栈。

场景
--

### 低代码（Lowcode）

_(你也许会喜欢 awesome-lowcode)_

-   H5/PC
    
    -   amis - 前端低代码框架，通过 JSON 配置就能生成各种页面。
-   H5
    
    -   h5-Dooring - 让 H5 制作像搭积木一样简单, 轻松搭建 H5 页面, H5 网站, PC 端网站, 可视化设计,LowCode 平台。
    -   luban-h5 - 类似易企秀的 H5 制作、建站工具、可视化搭建系统。
    -   gods-pen - 基于 vue 的高扩展在线网页制作平台，可自定义组件，可添加脚本，可数据统计。
-   PC
    
    -   pc-Dooring - 让网页制作像搭积木一样简单, 轻松搭建 PC 页面, Web 网站, PC 端网站. lowcode(low-code)可视化搭建平台。
-   逻辑编排
    
    -   node-red - 事件驱动应用的低代码编程。
    -   imove - iMove 是一个逻辑可复用的，面向函数的，流程可视化的 JavaScript 工具库。

### 云 IDE

-   code-server - 在任何地方的任何机器上运行 VS Code，并在浏览器中访问它。
-   theia - Eclipse Theia 是一个可扩展框架，用于使用最先进的 Web 技术开发成熟的多语言云和桌面 IDE 类产品
-   opensumi - 🚀 一个帮助你快速构建云或客户端IDE产品的框架
