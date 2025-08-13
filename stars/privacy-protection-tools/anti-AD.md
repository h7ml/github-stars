---
project: anti-AD
stars: 9558
description: 致力于成为中文区命中率最高的广告过滤列表，实现精确的广告屏蔽和隐私保护。anti-AD 现已支持 AdGuardHome，dnsmasq，Surge，Pi-Hole，Clash, mihomo，smartdns，sing-box 等网络组件。完全兼容常见的广告过滤工具所支持的各种广告过滤列表格式
url: https://github.com/privacy-protection-tools/anti-AD
---

anti-AD
=======

#### 致力于成为中文区命中率最高的广告过滤列表，实现精确的广告屏蔽和隐私保护。anti-AD 现已支持 AdGuardHome，dnsmasq，Surge，Pi-Hole，Clash, mihomo，smartdns，sing-box 等网络组件。完全兼容常见的广告过滤工具所支持的各种广告过滤列表格式

使用 anti-AD 能够屏蔽广告域名，能屏蔽电视盒子广告，屏蔽 App 内置广告，同时屏蔽了一些日志收集、大数据统计等涉及个人隐私信息的站点，能够保护个人隐私不被偷偷上传。

本工具是通过域名解析层来屏蔽广告和保护隐私的，其将各大著名的 hosts，ad filter lists，adblock list 等列表进行合并去重，再进行一系列的抽象化，例如主动剔除失效域名、easylist 优化模糊匹配、增强的黑白名单机制等措施，最终生成期望的高命中率列表。

快速使用(使用官网地址，速度更稳定)
------------------

文件

raw

官网地址

适用于

`adblock-for-dnsmasq.conf`

link

官网地址🚀

dnsmasq及衍生版本

`anti-ad-easylist.txt`

link

官网地址🚀

AdGuardHome（DNS过滤）

`anti-ad-adguard.txt`

link

官网地址🚀

AdGuard（匹配整个URL的域名部分）

`anti-ad-domains.txt`

link

官网地址🚀

Pi-Hole或其他工具（白名单）

`anti-ad-surge.txt`

link

官网地址🚀

Surge或其他工具

`anti-ad-surge2.txt`

link

官网地址🚀

Surge或其他工具，DOMAIN-SET 格式性能更好

`anti-ad-clash.yaml`

link

官网地址🚀

Clash Premium 类似工具（白名单）

`anti-ad-smartdns.conf`

link

官网地址🚀

SmartDNS（白名单）

`anti-ad-sing-box.srs`

link

官网地址🚀

sing-box（二进制文件，需`1.10.0`及以上版本）

`mihomo.mrs`

link

官网地址🚀

mihomo（二进制文件，需`1.18.7`及以上版本）

`anti-ad-easylist.txt` 包含正则规则，适用于 AdGuardHome，请勿在 AdGuard/uBlock Origin 等能够匹配 URL 路径的工具中使用（特定 URL 可能被错误拦截）

争议域名
----

一些域名可能与广告/跟踪有关，但部分情况下它们还有其他的作用，拦截它们可能会造成额外的问题。本项目对部分此类有争议的域名做了整理和简单说明，您可根据自己的需要自行添加额外规则放行或拦截相关域名。

点此查看

欢迎 anti-AD 用户贡献和完善这部分内容。

版本历史
----

#### v4.5.2 (2022.12.15)

-   项目代码切换到PHP 8，不完全兼容旧版本PHP

#### v4.5.1 (2021.05.31)

-   移动构建脚本到另一个分支，让默认分支看起来更干净
-   github Actions的针对性优化，优化自动构建逻辑
-   anti-AD仍然是一个完全开源的项目
-   没有了

#### v4.5.0 (2021.05.02)

-   重构工具`easylist-extend.php`，优化提升3倍执行效率
-   修复一部分小bug
-   开始支持AdGuardHome新的modifiers语法(目前测试阶段，adgh本身解析还有bug)

#### 更多版本演进历史>>>

一些补充的话
------

anti-AD 在自我认知上始终是一个非主流的小众项目。此项目一直坚持每一行代码开源！anti-AD 过滤列表的所有规则均来自上游列表和网友提交的 issues，欢迎各界朋友审阅。在没有阅读代码或没有完全理解代码意图之前，本项目以及作者不再接受任何无端的质疑、猜忌，作者也不打算再浪费时间作出任何解释。

欢迎提issue
--------

对于 anti-AD，大家伙儿有任何建议，或者存在误杀，bug，其他错误，各种意见 请开 issue

加入 QQ 群更实时的交流：716981535  

Special Thanks To
-----------------

-   TG-Twilight/AWAvenue-Ads-Rule - 秋风广告规则，干掉所有无良广告 (来自#897)
-   v2fly/domain-list-community - Community managed domain list
-   malware-filter/urlhaus-filter - Malicious URL blocklist,来自 #858
-   AdguardTeam/AdguardFilters - AdGuard Content Blocking Filters
-   fanboy-annoyance - 优秀的easylist列表
-   notracking/hosts-blocklists-scripts - 提供无效域名和无效hosts列表
-   Adblock Plus - 畅游清爽洁净的网络！
-   neoFelhz/neohosts - 自由·负责·克制 去广告 Hosts 项目
-   vokins/yhosts - yhosts（该源已停止维护）
-   cjx82630/cjxlist - Adblock Plus EasyList Lite与CJX's Annoyance List
-   _@rufengsuixing 提出的jsDelivr加速过滤列表下载的建议_
-   _@xlighting2017 提供的surge格式建议_
-   ACL4SSR/ACL4SSR - 一些常见APP的广告 @wchqybs in #79
-   ADgk.txt - 鸣谢 坂本dalao
-   jdlingyu/ad-wars - 只是 ad-wars 的帮助文档
-   hoshsadiq/adblock-nocoin-list - 恶意挖矿屏蔽列表
-   easylist.to - 感谢提供出色的easylist
-   ZeroDot1/CoinBlockerLists - 屏蔽恶意劫持挖矿
-   crazy-max/WindowsSpyBlocker - Block spying and tracking on Windows
