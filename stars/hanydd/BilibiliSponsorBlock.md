---
project: BilibiliSponsorBlock
stars: 3992
description: 一款跳过小电视视频中恰饭片段的浏览器插件，移植自 SponsorBlock。A browser extension to skip sponsored segments in videos, ported from the SponsorBlock
url: https://github.com/hanydd/BilibiliSponsorBlock
---

  
Logo by @munadikieh. Modified by Yaodong

小电视空降助手
=======

Chrome

FireFox

讨论群

受够了视频中无处不在的赞助广告了吗？受够了看了一半才发现的软广视频了吗？小电视空降助手是一款帮你精准空降到广告之后的浏览器插件。插件自动获取并跳过广告片段，让你的视频体验毫无中断！

除了广告之外，插件还支持跳过其他类别的片段，例如开场结尾的动画、一键三连提示，或者直接空降到视频封面的位置。插件中所有的标注片段都来自网友标注，您也可以提交自己的片段来为空降指挥部添砖加瓦。

想知道大佬们提交了多少片段？在排行榜看看吧。

目前本项目由我个人在业余时间维护，如果你想支持我，欢迎查看赞助。

本插件移植自插件SponsorBlock，保留了大部分的 UI 和使用方法，加入一些了小电视特色的功能。

安装
==

-   目前上架了Chrome 应用商店，火狐应用商店。如果你知道更多流行的浏览器插件商店，欢迎留言~
    
-   如果你无法打开上面的商店，可以尝试从从 Github Release 页面获取未打包的插件。
    
    1.  根据您浏览器的类型下载适合的版本，Chrome、Edge、360 和基于 Chromium 的国产浏览器下载 `ChromiumExtension.zip`；火狐浏览器下载`FirefoxExtension.zip`。并解压缩。
        
    2.  打开浏览器的插件管理页面，启用“开发者模式”，点击`加载已解压的拓展程序`，选择刚刚下载解压的插件文件夹，就可以完成安装。
        

功能
==

使用说明
----

如果你使用过原插件，你会发现在核心功能和交互上，本插件基本没有做出大的改动。可以先参照原插件的使用方法尝试使用。

可以先在这个示例视频上试一试精准空降的快乐！

视频使用说明正在计划制作中。

相比原插件变化
-------

-   放弃了多语言支持，只支持简体和繁体中文。
    
-   放弃了移动端H5网页支持。
    
-   放弃了第三方镜像站支持。如果有使用人数多的镜像站，欢迎讨论添加支持。
    
-   加入了绑定搬运视频的功能。绑定的视频可以自动从 SponsorBlock 数据库中获取片段信息。
    
-   更新 UI。
    

功能更新计划
------

参考 Github Project

服务端及数据
======

为了方便大家二次开发，所有片段的数据现在开放下载：https://bsbsb.top/database.zip

API
===

API文档：https://github.com/hanydd/BilibiliSponsorBlock/wiki/API

测试视频 BV14741127BN

本项目对 API 改动不大，也可以先参考原项目文档。

搭建项目
====

详见 CONTRIBUTING.md

致谢
==

感谢ajayyy创造的SponsorBlock给我的启发！

### 开源协议

本项目遵循 GNU GPL v3 开源协议。
