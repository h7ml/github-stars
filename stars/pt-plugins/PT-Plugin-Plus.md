---
project: PT-Plugin-Plus
stars: 7888
description: PT 助手 Plus，为 Microsoft Edge、Google Chrome、Firefox 浏览器插件（Web Extensions），主要用于辅助下载 PT 站的种子。
url: https://github.com/pt-plugins/PT-Plugin-Plus
---

Warning

PT-Plugin-Plus 项目已经进入停止维护期（具体说明见： #2235 ）

我们推荐您使用全新的替代方案： **PT-depiler** 。 PT-depiler 是 PT-Plugin-Plus 的继任者，保留了绝大多数核心功能并进行了全面优化，包括更好的兼容性、更稳定的性能和更丰富的功能支持。建议所有用户迁移至新项目以获得持续的更新和支持。

Tip

如果你浏览器中使用的PTPP已经被禁用，你可以尝试以下方法 **重新恢复使用** 或 **导出数据以迁移至PT-depiler**：

① 使用浏览器 flags 临时启用 （需要 chrome < 139）

② 使用临时插件 PTPP Exporter （仅适用于通过 crx 或者 zip 方法安装）

③ 使用低版本 chrome 抢救数据 （推荐！也可用于其他基于 chromium 但未移除 MV2 支持的浏览器）

  

* * *

关于
--

PT 助手 Plus，是一款浏览器插件（Web Extensions），一个可以提升 PT 站点使用效率的工具。

适用于各 PT 站，可使下载种子等各项操作变化更简单、快捷。配合下载服务器（如 Transmission、µTorrent 等），可一键下载指定的种子。

该版本是对原来的 PT 助手 进行了重构，去掉了繁琐的配置，以获得更好的使用体验；

> 注意：`1.0.0` 以下的配置不能直接用于该版本，请勿将 `1.0.0` 以下的版本配置进行导入操作。

最新版本请登录后从Pre-release获取。如不会安装请参看Wiki

**提Issue前请务必检查Dev版本、Pull Request以及之前的Issue**

**M-Team 请于站点控制台 -> 实验室 获取 Token 填入后使用**

已支持的浏览器
-------

-   （已下架，见原因）
-   （已下架，见原因）
-   
-   及其他基于 `Chromium` 内核的浏览器

功能
--

-   一键发送指定的种子到下载服务器，目前已支持：
    -   Transmission
    -   Synology Download Station
    -   µTorrent
    -   Deluge
    -   qBittorrent `v4.1+`
    -   ruTorrent
    -   Flood
-   比 RSS 更灵活的下载方式：
    -   针对不同的站点发送到不同的下载服务器；
    -   针对不同的站点、下载服务器设置不同的保存路径；
-   批量下载当前页所有种子；
-   批量复制当前页面所有种子的下载链接（`部分站点需要设置 passkey`）；
-   显示默认下载服务器当前可用空间，目前已支持：
    -   Transmission
-   多站聚合搜索相同关键字的种子；
    -   查看 已支持的站点列表
-   根据当前站点显示专属功能，如：
    -   封面模式浏览种子页面；
-   保存下载历史记录（默认关闭）；
-   `豆瓣` 电影页面、Top250、选电影 一键搜索 PT 种子支持；
-   `IMDb` 电影页面、Top250 一键搜索 PT 种子支持；
-   更多功能请参考 Wiki ；

安装及使用
-----

-   如何安装和使用，请参考 Wiki 的详细说明；
-   常见问题可 点这里 找到答案；
