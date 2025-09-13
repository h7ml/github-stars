---
project: wechat-versions
stars: 666
description: 保存微信历史版本
url: https://github.com/zsbai/wechat-versions
---

Wechat-Versions-For-macOS
=========================

收集 Mac 微信版本并保存

目录结构
----

├── README.md # 自述文件
├── WeChatSetup # 微信安装包临时目录
│   └── temp # 临时目录
└── scripts   # 脚本目录
    ├── destVersioForMac.sh # 获取安装包及取得版本号与 hash 值的脚本
    └── notify.sh # 新release 时调用通知的脚本

说明
--

-   2024.10.1 更新：通过转换dmg为img后解压，获取精确的微信版本号（例如：3.8.9.xx）；在此之前，后两位小版本号无法获取，所以通过添加更新日期后缀来区分大版本中的小版本，需在下载前自行判断。

项目使用 Github Action 自动下载微信**官网最新版本安装包**计算 Hash 值并推送至仓库 Release，目前暂无保留App Store安装包的想法。

各版本更新日志可参见官网 changelog

_如有问题/侵权，请直接提交 issue 告知。_
