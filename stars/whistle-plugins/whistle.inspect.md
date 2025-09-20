---
project: whistle.inspect
stars: 193
description: 集成 eruda、vConsole、mdebug 等调试H5页面工具的插件
url: https://github.com/whistle-plugins/whistle.inspect
---

whistle.inspect
===============

> 使用该插件建议用最新版本的 whistle

该whistle插件集成了 vConsole、eruda、mdebug 等用来在移动端页面上模拟Chrome开发者工具功能的模块，方便调试手机上的H5页面，只需简单配置即可随意切换 vConsole、eruda、mdebug。

> 更多移动端调试方法参见：利用 whistle 调试移动端页面。

安装
==

1.  首先需要安装最新版 whistle，如果你的机器已经安装了 whistle，请确保 whistle 为最新版本：
    -   安装及如何使用 whistle 参见 Github
    -   如何升级 whistle 参见帮助文档。
2.  安装inspect插件：
    
    ```
    w2 i whistle.inspect
    ```
    
    > 或使用 cnpm 镜像 `w2 i whistle.inspect --registry=https://registry.nlark.com` 如果已安装 cnpm，还可以用 `w2 ci whistle.inspect`
    

使用
==

安装插件后，只需配置简单的规则即可随意切换 vConsole、eruda、mdebug：

```
# 在匹配 pattern 的页面中插入 eruda
pattern whistle.inspect://eruda # 或 whistle.inspect://e

# 在匹配 pattern 的页面中插入 vConsole
pattern whistle.inspect://vconsole # 或 whistle.inspect://v

# 在匹配 pattern 的页面中插入 mdebug
pattern whistle.inspect://mdebug # 或 whistle.inspect://m
```

其中，`pattern` 表示匹配请求 url 的表达式，可以为域名（如：`www.test.com whistle.inspect://e`）、路径，通配符、正则表达式等，具体参见：whistle的匹配模式。

配置后访问对应页面，可以看到页面已经注入 vConsole、eruda、mdebug：
