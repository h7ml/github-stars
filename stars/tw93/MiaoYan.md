---
project: MiaoYan
stars: 6501
description: ⛷ Lightweight Markdown app to help you write great sentences. ⛷ 轻灵的 Markdown 笔记本伴你写出妙言
url: https://github.com/tw93/MiaoYan
---

#### **English** | 中文 | **日本語**

妙言
==

轻灵的 Markdown 笔记本伴你写出妙言~

特点
--

-   🏂 **妙**：纯本地使用、安全、语法高亮、黑暗模式、源文件保存、国际化、演示模式、PPT 模式、单独编辑模式、文档自动排版、文档导出、内部跳转、图床、LaTeX、Mermaid、PlantUML、Markmap 脑图
-   🎊 **美**：极简的设计风格，文件夹 + 文件列表 + 编辑器方式 3 列模式
-   🚄 **快**：使用 Swift5 原生开发，相比 Web 套壳方式性能体验好
-   🥛 **简**：很轻巧，纯编辑器输入体验，众多快捷键助你快人一步

首次使用
----

1.  从 GitHub Releases 中 **下载** 最新的 dmg 安装包，macOS Big Sur 及以上版本体验更好，如安装出现问题请参考 文档。
2.  可以在 iCloud 或根目录下创建一个 `MiaoYan` 的文件夹，打开妙言的设置，将默认存储地址修改成这个。
3.  点击妙言左上角新增文件夹的图标，创建好自己的文档分类文件夹，就可以开始使用了。
4.  同样假如你不习惯默认的字体，可以在设置中修改成其他的正常字体。

快捷键
---

#### 窗口操作

-   `command + 1`：收起展开目录
-   `command + 2`：收起展开文档列表
-   `command + 3`：切换编辑和预览
-   `command + 4`：切换到演示模式
-   `command + option + m`：全局唤起/隐藏妙言

#### 文档操作

-   `command + n`：新建文档
-   `command + r`：重命名文档
-   `command + d`：复制文档
-   `command + o`：单独打开文档
-   `command + delete`：删除文档
-   `command + shift + n`：新建文件夹
-   `command + shift + l`：自动排版
-   `command + option + r`：在 Finder 中显示
-   `command + option + i`：显示字数等文档属性
-   `command + option + p`：启动妙言 PPT 预览

🏂 此外还有很多快捷键 👆🏻 👇🏻 👈🏻 👉🏻 等着爱折腾的你去寻找~

妙言 PPT
------

点击查看 PPT 模式效果演示

1.  新朋友默认初始化会生成模版，如果是老朋友需升级到 1.0，可以 Copy 此文件 到妙言玩一玩。
2.  执行 `command + option + p` 可以启动妙言 PPT 预览，也可以选中文档点击右键，选择 `妙言 PPT` 打开。
3.  只有在有 `---` 分隔符标志的文档中，才可启用 PPT 模式，演示过程中你可以 `回车键` 预览演讲大纲，`ESC` 键可退出 PPT 模式。
4.  你可以使用 HTML 来自定义效果，更多复杂的用法可以参考 Reveal 文档。

为什么要做妙言
-------

-   之前有尝试过众多的笔记应用，大学时期为知笔记、印象笔记，工作时候用过 Ulysses、Quiver、MWeb、Bear、Typora，种种原因，没有找到一个习惯的 Markdown 应用，才有了做妙言的想法。
-   本职为前端开发，会一点 iOS 开发，爱折腾，借妙言来玩一下 Swift 以及独立产品，当做一个很愉快的事情。
-   更多介绍可见 妙言 - 更适合工程师用的笔记应用，很欢迎交流和建议

支持
--

-   我有两只猫，假如觉得妙言让你生活更美好，可以给猫 喂罐头 🥩🍤。
-   如果你喜欢妙言，可以在 Github Star，更欢迎 推荐 给你志同道合的朋友使用。
-   可以关注我的 Twitter 获取到最新的妙言更新消息，也欢迎加入 Telegram 聊天群。

感谢
--

-   glushchenko/fsnotes：项目初始化代码参考于此，非常感谢作者
    
-   stackotter/swift-cmark-gfm：快速高效的 Swift Markdown 解析器
    
-   raspu/Highlightr：语法高亮能力
    
-   仓耳字库：一款漂亮的开源中文字体仓耳今楷，妙言将其作为默认字体
    
-   hakimel/reveal.js：妙言 PPT 底层渲染依赖此框架
    
-   本项目 CDN 加速及安全防护由 Tencent EdgeOne 赞助
    

> **📦 依赖管理**：项目使用 Swift Package Manager 管理依赖，详细信息请查看 `DEPENDENCIES.md`

协议
==

-   遵循 MIT 协议
-   请自由地享受和参与开源
