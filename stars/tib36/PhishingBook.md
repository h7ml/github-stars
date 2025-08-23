---
project: PhishingBook
stars: 1124
description: 红蓝对抗：钓鱼演练资源汇总&备忘录
url: https://github.com/tib36/PhishingBook
---

PhishingBook
------------

  
  

#### 红蓝对抗：钓鱼演练资源汇总&备忘录

#### 目录

-   Office历史漏洞
-   钓鱼辅助工具项目
-   免杀项目
-   用于参考的C2项目
-   红队相关其他项目
-   蓝队反钓鱼资源
-   杂项堆积

#### 关于

本项目收集来自网络（主要是github）的钓鱼相关的资源，其中许多来自作者在攻防演练一线的经验，故列出谨供后人参考。

简单粗暴，基本上仅提供分类、链接和简介

持续更新中。。

**如果有帮助，建议师傅顺手点个免费的Star**

**注：**

本项目出现的资源均收集自公开网络，本项目作者未提供且不提供任何相关技术

这些资源仅仅是收集而来，未经验证是否可用，也没有逐一经过后门检测，因此学习及使用前需自行验证其可用性和安全性，**本项目仅仅是一个整理汇总网络公开资源的markdown页面，仅用于安全技术研究讨论**，请勿进行任何非授权渗透行为，否则请自行承担责任。

**本项目设立的目的仅仅是作为一个资源备忘录使用，用于工作中涉及的安全建设及人员安全意识培训。为防止技术滥用，项目内不对任何实际技术细节及工具进行存档，仅转发相关原作者发布的互联网公开链接。正因如此，本项目无法保证相关资源的安全性。如果您需要对其中的任何技术进行研究学习，请使用自行搭建的虚拟环境。**

欢迎任何纠错及补充（当然，额。。最好是和本项目相关的= =）

* * *

#### 分类:Office历史漏洞

项目名称

项目简介

**office-exploits**

Office-Exploits：Office漏洞集合（包含噩梦公式等历史漏洞，项目较老）

**office-exploit-case-study**

Office 历史EXP及学习项目

**CVE-2023-21716**

CVE-2023-21716 POC（Windows 10）

**'Follina' MS-MSDT n-day Microsoft Office RCE**

CVE-2022-30190 'Follina' Office RCE 测试工具

**'Follina' MS-MSDT n-day Microsoft Office RCE—修改版**

修改版Follina，支持自定义Word模板。

**CVE-2021-40444**

CVE-2021-40444 POC

**CVE-2021-40444**

CVE-2021-40444 EXP

**MSHTML-RCE-Exploit**

CVE-2021-40444 Demo

**CVE-2017-0199**

CVE-2017-0199 EXP

**PoC Exploit for CVE-2018-0802**

PoC Exploit for CVE-2018-0802

**CVE-2022-24934**

WPS Office 历史漏洞Demo

**WPS-20230809-RCE POC1**

WPS Office RCE

**WPS-20230809-RCE POC2**

WPS Office RCE

**Outlook RCE**

CVE-2024-21413 Microsoft Outlook漏洞POC

**WPS RCE:CVE-2024-7262&7263**

WPS Office RCE

* * *

#### 分类:钓鱼辅助工具项目

项目名称

项目简介

**Swaks**

邮件伪造工具，集成伪装发信人等功能

**MatryoshkaDollTool**

C#实现的程序加壳/捆绑工具

**BeCyIconGrabber Portable**

图标提取工具，可用于辅助进行图标伪装

**Restorator**

资源替换工具，可用于图标伪装，但是似乎是一款需付费的工具

**SigThief**

数字签名伪装

**Bad-Pdf**

通过恶意PDF文件窃取NTLM Hash

**Lnk-Trojan**

Lnk钓鱼工具

**EmailAll**

一款强大的邮箱收集工具

**sendMail**

批量群发钓鱼邮件

**ditt**

生成高仿域名

**PhishingInstall**

快速搭建钓鱼邮服

**社工字典**

社会工程学密码生成器

**EasyPersistent**

CobaltStrike的权限维持插件，支持多种权限维持方法

**Gophish**

Gophish，一款大型开源钓鱼框架

**Flash-Pop**

Flash钓鱼弹窗版

**Fake-flash.cn**

旧版Flash钓鱼页，中文+英文，可能需要改改再用

**Goblin 钓鱼演练工具**

适用于红蓝对抗的钓鱼演练工具。通过反向代理，可以在不影响用户操作的情况下无感知的获取用户的信息，或者诱导用户操作。支持隐藏服务端，支持docker快速部署

**Medusa**

Medusa红队作战平台

**idea-project-fish-exploit**

JetBrains系列产品.idea钓鱼反制红队

**IDE-Honeypot**

一款针对于IDE的反制蜜罐。通过项目文件钓鱼的思路理论上可对部分IDE实现无感触发

**CrossNet**

红队行动中利用白利用、免杀、自动判断网络环境生成钓鱼可执行文件。

**LNKUp**

恶意Lnk钓鱼生成器

**EBurst**

Exchange邮箱爆破

**cli.im在线工具**

在线生成和编辑二维码

**Taie-AutoPhishing**

钓鱼工具及思路汇总

* * *

#### 分类:免杀项目

项目名称

项目简介

**BypassAntiVirus**

TideSec的系列免杀教程

**掩日**

强大的红队免杀工具，截至目前仍在更新，可用性较强

**遮天**

遮天-免杀生成工具

**潮影-在线免杀平台**

线上版免杀工具平台

**darkPulse**

用go编写的多功能Loader

**GobypassAV-shellcode**

CobaltStrike shellcode强效免杀

**Bundler-bypass**

免杀捆绑器

**GoFileBinder**

Golang免杀捆绑器

**CS插件BypassAV**

Cobalt Strike插件，用于快速生成免杀的可执行文件

**PengCode**

将exe转换为shellcode

**rust-shellcode**

rust实现的shellcode加载器，支持多种加载方式

**NimShellCodeLoader**

使用小众的Nim语言实现的加载器，主要针对国产杀软

**PicBypass**

远程加载shellcode图片来免杀，可以作为思路然后通过其他语言扩展

**Amsi-Bypass-Powershell**

绕过Windows AMSI

**CS-Avoid-killing**

CobaltStrike免杀加载器

**Bypass Anti-Virus**

一些杀软绕过姿势

**bypassAV**

免杀shellcode加载器

**GolangBypassAV**

Golang下的免杀思路和工具

**Malleable C2**

用于混淆CobaltStrike流量特征（实战中还需要修改其他特征，例如证书）

**CrossC2**

经典项目，用于生成跨平台beacon

**NoteRCE**

一种另辟蹊径的免杀执行系统命令的木马,防溯源，无需VPS

**KaynLdr**

用C / ASM编写的反射加载器

**killEscaper**

利用shellcode来制作免杀exe的工具，可结合渗透工具生成的shellcode二次转换exe，支持CobaltStrike、metasploit等

**DamnPythonEvasion**

基于python pyd的shellcode免杀绕过

**SysWhispers3WinHttp**

基于SysWhispers3增添WinHttp分离加载+交叉编译

**ShellcodeLoader**

Windows平台的shellcode免杀加载器，内置多种加载方式

**pe\_to\_shellcode**

能将绝大部分PE转换为shellcode供外部加载，且shellcode本身可作为PE执行

* * *

#### 分类:用于参考的C2项目

项目名称

项目简介

**Sliver**

Sliver C2框架，貌似最近比较火

**RustDesk**

一款开源、支持普通用户权限、支持纯内网环境的远程桌面工具

**gotohttp**

gotohttp远程桌面工具

**Covenant**

Covenant，一款 .NET C2

**AsyncRAT**

AsyncRAT

**Manjusaka**

一款基于WEB界面的远程主机管理工具

**Havoc**

Havoc，类似CobaltStrike，基本上相当于重写了CS

**BlackMamba**

Python编写的开源C2框架

**Quasar**

一款C#编写的开源RAT，项目已停止更新

* * *

#### 分类:红队相关其他项目

项目名称

项目简介

**APT事件报告汇总-1**

国内某公司整理的APT分析报告，部分手法可参考并落地

**APT事件报告汇总-2**

国内某公司整理的APT分析报告，部分手法可参考并落地

**APT事件报告汇总-3**

国内某公司整理的APT分析报告，部分手法可参考并落地

**Fish-Hub**

钓鱼相关案例和参考

**红队防猝死手册**

红队防猝死手册，一些防止犯低级错误的指南

**红队笔记**

强大且全面的红队指南

**红队知识库**

一个红队知识库

* * *

#### 分类:蓝队反钓鱼资源

项目名称

项目简介

**微步云沙箱**

通过隔离环境运行程序，初步检测文件是否恶意

**安恒云沙箱**

通过隔离环境运行程序，初步检测文件是否恶意

**奇安信云沙箱**

通过隔离环境运行程序，初步检测文件是否恶意

**Freebuf云沙箱**

通过隔离环境运行程序，初步检测文件是否恶意

**360云沙箱**

通过隔离环境运行程序，初步检测文件是否恶意

**VirusTotal**

经典的VT，在线多引擎检测

**Any.run**

Any.Run交互式恶意软件分析工具沙箱服务

* * *

#### 分类:杂项堆积

杂项

**企业钓鱼演练总结**

**SMTP Smuggling 分析及实现**

**钓鱼研判经验**

**钓鱼指南**

**邮件钓鱼平台搭建**

**钓鱼具体手法**

**钓鱼手法分析**

**Office钓鱼姿势**

**Windows凭据钓鱼窃取**

**邮件钓鱼技巧（提高成功率）**

**钓鱼姿势汇总（CHM、自解压等）**

**自解压钓鱼详解**

**渗透Exchange邮服**

**钓鱼优秀战例**

**反制红队的钓鱼优秀战例**

**Office钓鱼手法**

**文档钓鱼汇总**

**Office宏免杀**

* * *
