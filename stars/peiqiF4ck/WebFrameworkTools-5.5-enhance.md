---
project: WebFrameworkTools-5.5-enhance
stars: 304
description: 本软件首先集成危害性较大框架和部分主流cms的rce(无需登录,或者登录绕过执行rce)和反序列化(利用链简单)。傻瓜式导入url即可实现批量getshell。批量自动化测试。例如:Thinkphp,Struts2,weblogic。出现的最新漏洞进行实时跟踪并且更新例如:log4jRCE,向日葵 禅道RCE 瑞友天翼应用虚拟化系统sql注入导致RCE大华智慧园区上传,金蝶云星空漏洞等等.    
url: https://github.com/peiqiF4ck/WebFrameworkTools-5.5-enhance
---

2025年推出 webframeworktools 5.5 增强版
=================================

### 在去年2024年7月份我们开始针对软件性能进行测试到。2024年12月软件测试完毕。总耗时将近4个月软件在1000万条url表现很好。跑了将近4个月没有出现奔溃现象。软件表现很不错。软件由于某些原因工具将永久对外停止发布,我们会出售全部webframeworktools 5.3 源代码。感兴趣的请到youtube中找相关情况 在github,博客,youtube还是会分享某些东西得

WebFrameworkTools-5.5-enhance-main For RedTeam
==============================================

更新日志:
-----

-   2025-07-23 更新 Microsoft share point CVE-2025-53770 一键批量getshell模块详情看底部。实战中坑点讲解请看视频 https://youtu.be/gITPNrJpZmE?si=Ihc-42IiJec56TyN
-   2025-07-20 更新webframeworktools v5.5 增强版 增加webtitle模块 端口扫描 指纹识别 目录扫描 由于某些原因工具将永久停止对外发布。github 将做工具更新记录!!!
-   2025-05-29 更新vBulletin Remote Code Execution Vulnerabilities Exploited 远程代码执行漏洞 CVE-2025-48828 CVE-2025-48827截图演示见底部
-   2025-04-20 dll生成器 一键生成CVE-2025-3248代码执行exp 并且直接批量实战演示见youtube.
-   2025-01-20 软件使用视频教程和文字教程和2024-08-31版本10w条已经发布到博客请去博客下载
-   2024-11-01 更新漏洞如下: 泛微 e-cology H2远程命令执行漏洞  
    某盗u平台任意文件上传  
    汇智-企业资源管理系统-任意文件上传  
    微商城系统-任意文件上传  
    SparkShop开源商城任意文件上传  
    无纸化业务管理系统密码泄露  
    天锐绿盾审批系统put上传不能上传脚本文件  
    SPIP porte\_plume插件代码执行漏洞  
    速达软件任意文件写入漏洞  
    pkpmbs 建设工程质量监督系统 任意文件上传  
    CyberPanel upgrademysqlstatus 远程命令执行漏洞(QVD-2024-44346)  
    若依漏洞(只加入登陆和swagger漏洞)  
    某\*云默认密码(自主发现0day如果这个不行后续将更新另外一个day这个可以通杀所有无需账号密码) 另外更新 某请求遇到大量数据时会奔溃的bug。后续将加入更多自主发现的漏洞。
-   2024-10-30 更新dll生成器UserDllpluginExpGenerate 在处理Cyber​​Panel RCE options 请求无法处理的功能
-   2024-08-26 详情见博客 更新时空erpshiro 反序列化漏洞 erp  
    友点cms上传漏洞  
    hospital后勤系统上传漏洞 hospital  
    大华智慧园区bitmap上传漏洞  
    泛微任意文件读取漏洞。泛微任意用户登录绕过  
    联达OA上传漏洞(不知名oa)  
    鸿宇多用户商城 user.php 反序列化漏洞  
    泛微e-office发序列化漏洞  
    太阳能系统DataCube3(cve)  
    wordpress ticket 文件上传漏洞  
    wordpress booking 代码执行  
    蓝凌智慧协同平台eis 文件上传漏洞  
    可视化融合指挥调度平台上传漏洞  
    JeeSpringCloud uploadFile.jsp 文件上传  
    用友U8 cloud servicedispatcher 反序列化rce漏洞 yongyouu8  
    用友GRP-U8 operOriztion SQL注入漏洞  
    用友GRP-U8 fastjson 漏洞  
    富通天下外贸ERP任意文件上传漏洞  
    普元eos 反序列化漏洞  
    迅饶科技 X2View物联网设备存在任意用户添加漏洞  
    中成科信票务管理平台任意文件上传漏洞  
    魔方网表ERP存在文件上传漏洞  
    电信网关配置管理系统RCE  
    H5云商城-任意文件上传(othercms)  
    红海任意文件上传(othersystem)  
    微擎系统-任意文件上传-AccountEdit(站很少没啥用容易修改配置 未集成)  
    微厦在线学习平台OrganSetup存在任意文件上传漏洞(可能会触发问题未集成)  
    分诊叫号系统任意文件上传漏洞(医院)  
    泛微e-cology OA action.jsp 文件上传漏洞  
    申欧录音系统rce漏洞  
    wordpress CVE-2024-5084 上传漏洞  
    万户ezEip 上传漏洞,反序列化漏洞  
    LyLme Spage上传漏洞  
    泛微OA-E-Mobile移动管理平台lang2sql任意文件上传漏洞  
    迈普多命令执行漏洞  
    云匣子堡垒机 fastjson漏洞  
    Hikvision综合安防管理平台 applyAutoLoginTicket任意代码执行  
    Hikvision综合安防管理平台 applyCT任意代码执行  
    Hikvision综合安防管理平台 config-properties信息泄露  
    Hikvision综合安防管理平台 env信息泄露  
    Hikvision综合安防管理平台 find信息泄露  
    Hikvision综合安防管理平台 keepAlive任意代码执行  
    Hikvision综合安防管理平台 session任意代码执行  
    Hikvision综合安防管理平台 env\_heapdump信息泄露  
    CVE-2024-4577 php cgi 远程命令执行  
    CVE-2024-23692 HFS 远程命令执行  
    课交单对接平台sql注入  
    新增tp5 内置三种常用getshell方式。由于日志方式这个比较复杂将会在这三种方式都不管用的情况下使用日志方式手工getshell。  
    yzmcms rce漏洞  
    和丰山海-数字标牌 任意文件上传  
    Chatgpt ai 弱口令  
    NetMizer RCE  
    X-NAS/Main RCE漏洞  
    pyq 上传漏洞  
    极验xx任意文件读取漏洞  
    短视频系统漏洞  
    geoserver 远程命令执行  
    ZXUi 文件上传漏洞  
    jx彩票漏洞  
    h\*y发卡平台漏洞  
    jy cat 系统上传漏洞  
    qt 交易所漏洞  
    3g shop 漏洞  
    jeecgboot漏洞  
    EKing-管理易 FileUpload存在任意文件上传漏洞  
    Apace OFBiz 授权不当致远程代码执行漏洞(CVE-2024-38856)  
    H3C iMC智能管理中心byod\_index.xhtml远程代码执行漏洞  
    pbootcms rce漏洞  
    同享人力资源管理系统-任意文件上传  
    赛蓝企业管理系统-任意文件上传-SubmitUploadify  
    瑞斯康达-多业务智能网关-远程命令执行  
    喰星云-数字化餐饮服务系统任意用户添加漏洞  
    时空智友ERP-任意文件上传  
    App托管服务分发平台-任意文件上传  
    禅道任意用户添加漏洞  
    金慧-综合管理信息系统-SQL注入  
    PEPM系统存在远程代码执行漏洞  
    LiveBOS 任意文件上传漏洞  
    智慧校园(安校易)管理系统 任意文件上传  
    中小学智慧校园信息管理系统 任意文件上传  
    章管家 saveUser.htm 任意用户创建漏洞  
    ALR-F800命令执行漏洞  
    赛企业管理系统 AuthToken/Index 身份认证绕过漏洞  
    云时空社会化商业ERP系统 user/online 身份认证绕过漏洞  
    WookTeam sql注入和xxx漏洞  
    九思OA文件读取漏洞  
    用友U8-CRM import任意文件上传漏洞  
    息AI网络运维平台RCE  
    泛微 e-cology 9 sql注入漏洞  
    蓝凌EKP存在sys\_ui\_component远程命令执行漏洞  
    杭州三汇网debug rce  
    用友NC系统FileManager任意文件上传  
    赛通文档安全管理系统getAllUsers信息泄露  
    某服装品牌系统任意文件上传  
    指挥调度平台rce漏洞(绕过waf)  
    致远OA任意文件上传漏洞  
    致远互联FE 任意文件上传  
    教学视频应用云任意文件上传  
    潮GS企业管理软件反序列化  
    
-   2024-07-18 更新 软件下载地址到期时间为10月31号。下载地址见release。licenseKey见频道。
-   2024-06-03 更新 CVE-2024-5084 WordPress 上传漏洞 50个网站作为测试动图见下图
-   2024-03-30 更新 泛微E-Office10 一键getshell exp 另外还更新了几个漏洞下次写github补上 QVD-2024-11354。实战复现文章:https://peiqif4ck.github.io/penetrationtest/2024/03/articles/b8f9d080e95e9930/
-   2024-03-14 更新 AspCms,DedeCms,Ecshop,FCKeditor,FineCms,MacCms,OmWeb,OpenSns,PhpWeb,QiBoCms,SouthDic,Zabbix,致远OA,YiQiCms,Eyoucms,LJcms,phpok,Oklite,ezEIP,phpcms,pageAdmin,Jymusic,BigIp,WordPress,seacms,u163pan,zzzcms,PowerCreatorCms,FHAdmin,YongYouNC,晨光cms,GameDomain,Discuz!,maccms10,phpoa,faka平台,maxcms,pigcms,beecms 等39个cmsexp 后半年不忙了继续补充弹药
-   2024-02-28 更新了wordpress RCE-CVE-2024-25600 此次更新为试水更新。证明群主还在。前半年不更新软件。需要了解软件和源代码的。关注频道。后半年着重内部更新exp!!! 请关注频道和github信息
-   2024-01-19 Webfraneworktools v5.5 beta最新版已经发布。自行寻找下载地址。
-   软件已经开放下载。dll生成器也带上了另外可以自己写插件事例https://github.com/peiqiF4ck/ToolsUserDllplugin 软件见release 软件发布版本为5.1 5.2 和5.5暂未发布避免影响扩大。源代码计划24年年中或者年终出售具体看情况而定也可能提前。出售源码后本人将不在维护公开版本的软件改为内部维护。另外频道已经开启欢迎大家订阅关注软件动态。再次感谢大家对软件的支持。软件如果无法下载,请自行寻找下载地址。作者将不在发布下载地址直到明年hw。期间作者将不在频道件更新软件信息
-   2023-12-31 发布5.2 ini自定义配置文件调用任意第三方漏洞利用软件教程 https://peiqif4ck.github.io/securitytools/2024/01/articles/1fee187af88e0843 工具请关注文章具体在文章中发布
-   2023-09-09 版本更新至5.5 修复多处bug增加无回显漏洞探测interactsh 类。加入java 算法转换成C#算法的文件。
-   2023-09-01 更新了hw 中漏洞24个分别为用友nc cloud 上传漏洞 一键getshell,汉得SRM tomcat.jsp 文件存在登陆绕过漏洞,深信服 应用交付管理系统 login 远程命令执行漏洞(shell拿不到),网神 SecGate 3600 防火墙 obj\_app\_upfile 任意文件上传漏洞,用友 移动管理系统 uploadApk.do,HiKVISION 综合安防管理平台 env 信息泄漏漏洞,锐捷 NBR 路由器 fileupload.php 任意文件上传,金盘 微信管理平台 getsysteminfo 未授权访问,网御上网行为管理系统Sql注入,用友 U8 CRM客户关系管理系统 getemaildata.php 任意文件上传漏洞,广联达sql注入,企望制造 ERP comboxstore.action 远程命令执行漏洞,大华 智慧园区综合管理平台 video 任意文件上传漏洞,大华城市安防监控系统平台管理存在任意文件下载漏洞,大华城市安防监控系统平台管理sql注入漏洞,飞企互联 FE业务协作平台 ShowImageServlet 任意文件读取漏洞,Metabase validate 远程命令执行漏洞 CVE-2023-38646(poc),大华 智慧园区综合管理平台 账号密码泄露,fficeweb365 任意文件上传漏洞,致远OA M1Server userTokenService 远程命令执行漏洞,金蝶OA 云星空 CommonFileServer 任意文件读取漏洞,新开普 前置服务管理平台 service.action 远程命令执行漏洞(勉强加上了),明源云 ERP系统 接口管家 ApiUpdate.ashx 任意文件上传漏洞,亿赛通文件上传漏洞。详情看截图2023h漏洞。 2023hw漏洞更新此次更新24个漏洞由于时间或者其他原因部分漏洞没有更新。这个不影响。我们软件新版本5.2功能可以调用任意脚本执行exp 弥补了这个不足。另外已出exp poc 编写教程 https://peiqif4ck.github.io/securitytools/2023/09/articles/2633a9b907f3f584/ 这次更新以后我将不会再更新漏洞。后续我学习完毕以后将专注更新软件。感谢大家对软件的支持 。
-   2023-08-21 版本更新到5.2 修复了某editor编辑器上传漏洞的bug。增加第三方程序一键调用批量配置执行。测试结果见下图。后续将写一篇相关的文章来详细介绍这个功能。
-   2023-08-04 修复dig.pm dnslog平台不能使用的bug。由于dnslog.cn 这个网站平台仅允许国内ip使用。。。后续我们无回显漏洞换成interactsh。不在使用dnslog.cn探测无回显漏洞。敬请期待!!!
-   2023-07-18 更新金蝶云星空反序列化漏洞导致命令执行。其中exp 请求包重新更改屏蔽反序列化特征。 反序列化包重新更改。漏洞验证重新更改以求绕过waf。在实战中更加试用
-   2023-07-17 更新Sapido路由器未授权命令执行漏洞。修复几个模块https http 反斜杠 导致404 等bug
-   2023-07-14 更新Altenergy Power System Control命令执行漏洞(CVE-2023-28343) 一键getshell 漏洞原理分析工具展示截图 https://peiqif4ck.github.io/penetrationtest/2023/07/articles/a67e92b61df29d7e/
-   2023-07-11 更新 SPIP < 4.2.1 - Remote Code Execution (Unauthenticated) 一键getshell 漏洞编号 CVE-2023-27372
-   2023-07-11 更新 大华智慧园区综合管理平台任意文件上传漏洞
-   2023-07-10 更新海康威视isecure center 综合安防管理平台任意文件上传漏洞,修复某个模块逻辑性错误导致无法继续下一个函数的bug
-   2023-07-05 更新CVE-2023-34960 一键getshell exp 我看了一下代码然后自己写了一个exp我们只用管道符和echo和其他linux命令配合getshell。后续写一篇根据exp分析这个漏洞的文章。复测分析文章 https://peiqif4ck.github.io/penetrationtest/2023/07/articles/3a5c54b2df6ebaf1/ 工具测试截图见底部
-   2023-06-30 更新 泛微-EOffice文件上传漏洞两枚一键getshell不一键getshell不是我们软件的风格,nginxWebUI RCE漏洞(版本小于3.5.0)能一键getshell都一键了除非个别命令执行的还有其他的问题不能一键的。近期会放出软件022年8月份之前的因为新版本对代码进行优化暂时不放出。后续内部更新。2022年8月为后期最终版流出版本。敬请期待关注github和我们的频道。感谢大家。
-   2023-04-18 更新瑞友天翼应用虚拟化系统远程代码执行漏洞 一键getshell(通杀6.x) 奇安信漏洞编号 QVD-2023-8621 演示图见底部见博客
-   2023-04-16 更新瑞友天翼应用虚拟化系统远程代码执行漏洞 一键getshell(通杀7.x) 奇安信漏洞编号 QVD-2023-8621 演示图见底部见博客
-   2023-03-27 更新线程池框架合并线程池 ThreadHelper.dll 到代码码中使其支持.net core 版本处理速度更加快(重大更新!!!)
-   2023-03-26 更新CVE-2023-28432 MinIO信息泄露漏洞 演示图见底部
-   2023-03-15 修复之前nacos 逻辑判断错误导致存在的漏洞没有直接添加用户。更新nacos 秘钥硬编码漏洞 漏洞编号 QVD-2023-6271 。这个刚好之前有exp 更新一下否则也是后续更新了。因为要学习其他东西
-   2023-01-16 更新CVE-2022-46463 harbor未授权访问 测试截图见底部
-   2023-01-14 增加禅道Rce exp地址:https://www.github.com/webraybtl/zentaopms\_poc/ 这个poc只写了伪静态。我们动态静态都有。修复了若干https http请求头部问题导致xml请求错误导致漏报和误报问题。测试截图请看下图 。从此刻起更新的exp poc名称和使用所在的模块 全部写入软件内部。且不在github中显示。 软件发布将不在github中上传附件。将在频道更新。github仅仅记录软件更新细节。软件仅在国家hw时候放出一次。后续软件将停止对外发布并且采用内部邀请制方式内部攻防演练中使用
-   2023-01-08 修复https 多出bug 修复十几个逻辑性的bug错误。增加不排除模块。版本更新至5.1
-   2022-10-07 增加 -m参数列出所有内置模块
-   2022-10-04 更新 排除模块功能选项具体。看演示截图 修复dnslog 逻辑 代码
-   2022-09-28 更新 easyCVR 接口信息泄露(gateway)
-   2022-08-26 更新 zimbra-邮件系统文件上传漏洞 CVE-2022-27925 From https://github.com/miko550/CVE-2022-27925 (zimbra),金和oa文件上传漏洞,用友时空 ksoa 任意文件上传,致翔OA sql注入(oaAll)
-   更新日志记录软件已经停止更新!!!
-   以下为2022-08-18软件更新日志记录!!!
-   2022-08-17 更新 修复http编码导致部分网站遗落的重大bug 更新 nsfocus resourse.php 任意文件上传漏洞,安恒明御waf绕过登录(firewall),红帆医用系统sql注入漏洞,浪擎灾被软件添加用户(hwcms), 华天动力文件上传(htoa),用友u8任意文件上传(yongyougrp),泛微-EOffice文件上传漏洞,泛微OA ecology9任意文件上传,泛微OA 文件上传，weaverEcology8 sessionKey登录(weaveroa),h3c cas文件上传漏洞,天融信上网审计管理系统rce,联软安界 UniSDP 软件定义边界系统RCE(yunwei),用友nc GRP文件上传漏洞(yongyouu8),致远oa任意文件上传漏洞!!!!(seeyonoa)等共计16枚漏洞,软件后续发布!!!!
-   2022-07-19 更新 蓝凌OA treexml RCE 过阿里云webshell,使用自定义编码器过阿里云流量监测(landrayoa),thinkphp 任意文件读取漏洞 开启debug模式(thinkphp)
-   2022-06-15 更新 Apereo Cas 4.1.x 反序列化漏洞(yunwei),Atlassian Confluence存在远程代码执行漏洞CVE-2022-26134(atlassianconfl)
-   2022-05-19 更新CVE-2022-30525(firewall) zyxel 远程命令执行漏洞。该漏洞由于不回显采用 dnslog方式探测根据网络原因 可能会出现漏报!!!!
-   2022-05-09 更新CVE-2022-1388 F5 big ip Rce (bigip) 由于exp特殊原因.net框架特殊原因只进行检测可能会有误报 from https://github.com/bytecaps/CVE-2022-1388-EXP
-   2022-04-21 更新CVE-2022-29464 wso2 file upload(yunwei) from https://github.com/hakivvi/CVE-2022-29464
-   2022-04-15 更新vmware Workspace RCE CVE-2022-22954(vmware)!!!.修复dll模式线程终止的bug
-   2022-04-08 添加 一键生成dll的软件指纹生成功能。注意一键生成dll软件除post数据框那里可以有带双引号的数据。其他所有地方都不允许有双引号否则会编译失败!!!
-   2022-04-05 修复 一键生成dll的软件提交json数据导致的bug。感谢用户反馈。或者不修复的话提交直接转义特殊符号进行提交\\" \\\\
-   2022-04-03 新增 Spring Cloud Function SPEL表达式注入漏洞 CVE-2022-22963(springboot),spring core rce检测 CVE-2022-22965(spring) 。修复git 信息泄露漏洞,weaverOa8 sql注入误报,yongyouu8 信息泄露误报问题。修复 solr log4j探测不出误报问题。感谢反馈!!!
-   2022-03-25 新增模块cms(存放常见的cms),原来的改为hwcms,增加OA模块(小众oa产品合集)更新 一米oa任意文件读取漏洞(oa),cmsEasy sql注入漏洞(cms) ,致翔OA sql注入(oa)
-   2022-03-03 zabbix 认证绕过CVE-2022-23131(zabbix), spring Cloud Gateway Rce CVE-2022-22947(spring)
-   2022-03-01 某上网行为管理系统RCE导致getshell(dkey),PowerMTA 邮件系统任意文件读取漏洞(zujian)
-   2022-02-16 向日葵远程命令执行(sunlogin)
-   2022-02-05 更新框架集成自定义dll工具版本5.0。自定义phpstudy 自定义EXP演示.见底部演示截图。新手使用请看软件使用帮助和演示视频
-   2022-01-18 更新MeterSphere RCE(api)
-   2022-01-13 更新Canal Admin信息泄露弱口令(gateway),华天动力一键getshell-mysql(htoa),PatrolFlow 一键getshell(gateway),spon 网络对讲机一键getshell,rce(hardware)
-   2022-01-07 增加自动http网页识别编码自定义http头部方法类以增强软件功能
-   2022-01-05 更新Apache APISIX Dashboard CVE-2021-45232 演示图见底部 合并 https://github.com/wuppp/cve-2021-45232-exp 。增加Crc32算法类修正dict字典键值重复报错问题!!!
-   2022-01-02 更新Panabit-Panalog日志系统RCE(yunwei),x天智能edr任意文件上传getshell(hwcms),ASUSTORNAS(phpmyadmin) 弱口令一键getshell。根据网站数量调低默认线程保证结果准确性
-   2021-12-30 更新齐博cms ssrf|任意文件读取漏洞(hwcms)，增加除www.dnslog.cn接口避免dnslog无法使用导致问题。如果获取不到dnslog则会提示!!!。
-   2021-12-29 更新log4j漏洞探测(支持模块和产品Http Header Fuzzing(16)|Apache SkyWalking|Seeyon OA|MobileIrons|Apache solr|APACHE-Druid|APACHE OFBiz No Testing|APACHE Struts2|vmware-Horizon|vmware vcenter|XenMobile|UniFiNetwork|vmware-Workspace No Testing!!!|weblogic log4j)合并此项目 https://github.com/Dghpi9/Log4j2-Fuzz
-   2021-12-25 更新bootdo系统漏洞(bootdo)
-   2021-12-19 万户 OA 任意文件写入(ezoffice)
-   2021-12-16 xxxoffice OA RCE(hwcms)
-   2021-12-15 更新 泛微OA CNVD-2021-49104(weaver OA ) 任意文件上传漏洞 覆盖两个上传接口。Lxxxxec VPN 任意文件上传前台(vpn)
-   2021-12-12 更新xxx教学管理ERP系统任意文件上传(hwcms)。xx捷CRM Sql注入直接getshell(hwcms)。修复了某些bug。最近log4j漏洞比较火但是因为log4j参数只能fuzz。且该漏洞影响较大。各大厂商都很重视。估计修复很快。两个原因:故不集成到本工具里面了。
-   2021-12-09 更新Grafana任意文件读取 CVE-2021-43798,增加软件更新提醒功能
-   2021-12-06 更新Jenkins CVE-2019-1003000 并且增加爆破账号密码功能
-   2021-12-04 更新Joomla-3.4.6远程代码执行漏洞(影响版本3.0-3.4.6)
-   2021-12-03 konga JWT 认证绕过
-   2021-12-01 更新X5系统前台SSRF，XXE(工具作者自己挖掘)还有一枚前台初始化数据库直接重置管理员密码威力太大暂时不写工具里面
-   2021-11-30 修复bug youyou 出现错误直接跑不完的bug 和获取报错的类遇到强制关闭的类没有加入try catch 导致没有waf的情况下也停止的bug并且不出现任何结果。
-   2021-11-29 雪在烧棋牌站任意文件上传漏洞(upload) 属于古董级别漏洞。修复 数组遍历没有做判断导致误报的bug。修复正常网站没有有斜杠没有去掉的bug
-   2021-11-28 锐捷EG易网关与NBR路由器后台命令执行漏洞(ruijie),修复:weiphp sql注入误报 solr-CVE-2019-17558 误报。修复获取网站路径斜杠多截取导致获取到不完整网站的bug
-   2021-11-27 xxx酒店电视网关(通用) 未授权RCE漏洞(gateway)
-   2021-11-26 更新webuploader上传漏洞,用友-UFIDA-NC" 目录遍历,metinfo 6.0 任意文件读取漏洞(hwcms).,nodejs 文件读取，node js rce CVE-2021-21315
-   2021-11-21 更新xxx一体机rce漏洞
-   2021-11-20 更新weiphp 未授权文件上传。sql注入漏洞
-   2021-11-19 更新Apache ShenYu 未授权接口访问(CVE-2021-37580)
-   2021-11-12 更新泛微OA 任意文件上传xday
-   2021-11-08 更新某堡垒机Rce漏洞
-   2021-11-07 H5S视频平台未授权 接口泄露
-   2021-10-29 更新 gitlab 未授权 rce gitlab CVE-2021-22205 合并此项目https://github.com/r0eXpeR/CVE-2021-22205 不回显漏洞使用dnslog检测如果不出网那么即使有漏洞也无法检测
-   2021-10-16 修复导致软件奔溃严重bug,修复shiro 识别不准确的bug
-   2021-10-10 更新phpstudy,CVE-2021-41773 CVE-2021-42013 检测和识别是否是对应版本(apache)由于net特性会对poc进行自动编码导致无法准确检测!!!请使用专用工具检测
-   2021-09-29 更新:VMware vCenter Server CVE-2021-22005 Reference:https://github.com/rwincey/CVE-2021-22005
-   2021-09-04 Atlassian Confluence OGNL 表达式注入CVE-2021-26084
-   2021-08-28 修复在识别框架shiro的时候部分网站识别不准确的bug。修复 weaverOA WorkflowServicexml dnslog检测失败的bug。此问题存在于公开版本
-   更新日志记录软件已经停止更新!!!
-   以下是公开版的更新
-   2021-08-15 更新git信息泄露,更新路由器防火墙硬编码漏洞(dkey),gitlab 邮箱信息泄露,h3防火墙任意文件读取漏洞,汉王考勤系统sql注入漏洞 ,海康威视视频网管任意文件读取,汇捷通云视频任意文件读取,webmail basic rce,Jellyfin 任意文件读取漏洞,cloudRouter, 金何OA C6 任意文件读取漏洞,极通EWEBS任意文件包含,webui任意文件下载,Kyan账号密码泄露,佑友-佑友防火墙命令执行,三星 wlan AP 命令执行, php v8.1 后门,,深信服终端检测平台RCE漏洞,Selea OCR-ANPR摄像机文件读取漏洞,shiziyucms注入,ShopOX 任意文件下载漏洞，TamronOS IPTV ,网康 NS-ASG 应用安全网关文件下载,AC集中管理平台弱口令,Zeroshell 防火墙rce, 协达Oa 任意文件下载,任务调度弱口令,好视通文件读取漏洞 ,AI网络运维平台RCE,WorkflowServicexml rce
-   2021-07-18 致远OA htmloffice 误报修复,spring boot探测误报修复,Apache Kylin弱口令误报修复,新增蓝凌OA 前台getshell,任意文件读取， 致远OA FastJson 漏洞,致远OA任意文件下载漏洞,致远OA 监控密码泄露导致铭感信息泄露,用友u8 OA sql注入,铭感信息泄露等漏洞(合并此项目所有漏洞https://codeload.github.com/Summer177/seeyon\_exp/zip/refs/heads/main)。2021-07-18更新版本将下周在github发布!!!!!。最新版本已经同步到git
-   2021-07-11 修复能多开,导致绕过1000条限制的bug,更新:Yapi Rce漏洞,飞鱼星路由器信息泄露(router),ACTI Camera 任意文件读取漏洞(webcam),Nacos 弱口令 未授权, Apache Kylin Console弱口令,Atlassian Jira 信息泄露漏洞 CVE-2020-14181，中国移动 禹路由未获授权访问,密码敏感信息泄露(router) coremail 任意文件上传漏洞,信息泄露漏洞， D-Link ShareCenter DNS-320 rce(router)，海康威视流媒体密码泄露,任意文件读取(webcam), Dlink 弱密码(router),浙江大华DSS 任意文件下载(webcam),FineReport（帆软）报表系统目录遍历漏洞(hwcms)， Finetree-5MP-摄像机 未授权添加账号密码,弱密码
-   2021-06-28 更新用友UFiDa bshservlet rce漏洞,更新万户ezoffice文件上传漏洞
-   2021-05-23 更新泛微OA /weaver/weaver.common.Ctrl 任意文件上传漏洞,h3c intelligent management Rce,蓝海卓越2015版宽带计费系统RCE,Dlink密码泄露漏洞(CVE-2019-17506),启莱OAsql注入漏洞
-   2021-05-16 更新thinkcmf文件包含漏洞rce版本thinkcmf版本小于2.3.0大于1.6 可以无视宝塔防火墙。阿里云等waf 目录无权限。过滤转义单双引号等拦截一键getshell
-   2021-05-09 更新CVE-2021-30461 voip monitor rce漏洞
-   2021-04-24 增加勾选功能(使用见:软件使用注意事项)。。并且修复issue:EASY提交的误报问题:下一代云桌面,activemq,锐捷网络-EWEB这三个漏洞的误报问题。同时加入了对gov edu域名的检测出现直接丢弃。另外加入金山 V8 终端安全系统rce和任意文件读取漏洞。再次感谢EASY 提供的建议。
-   2021-04-18 2.0重构版 增加4个漏洞(亿邮电子邮件系统 rce ,用友 GRP 8 sql注入, 红帆oA sql注入漏洞, 泛微 Emoblie 6.6 RCE)不确定漏洞写入MaybeVul.txt中,增加这个是为了如果目标站有waf我们的shell被杀。或者执行某些命令被waf拦截可以记录方便手工绕过!!!!!泛微emobile归类有问题下次更新将调到泛微类里面!!!!
-   2021-04-11 更新hv热门漏洞9个,更新近期HVV热门漏洞 泛微9 任意文件上传漏洞,泛微8 sql注入漏洞，帆软 V9 任意文件覆盖文件上传，浪潮ClusterEngine 4.0 RCE,和信下一代云桌面VENGD 上传漏洞,齐治科技-堡垒机任意用户登录,360新天擎sql注入(用一个线程跑出结果,一个以上网站少无法跑出结果),360新天擎未授权接口访问,奇安信 网康防火墙 代码执行,致远oa 解压上传漏洞 合并之前 A8 文件写入。和hmloffice漏洞修复springboot框架识别
-   2021-04-04 新增D-Link-DCS-CVE-2020-25078 Exp ,新增shiro框架检查,新增springboot信息泄露
-   2021-04-03 新增三星路由器(WLAN AP WEA453e )任意文件读取,rce,默认密码漏洞。修复已知bug支持 类似 http://wwww.baidu.com/aaaa/ 这种域名方式,大部分支持如果有的漏洞不支持可以反馈我邮件提供type参数我修复一下
-   2021-03-28 新增 CNVD-2021-10543 MessageSolution信息泄露漏洞,新增Apache OFBiz CVE-2021-26295,CVE-2020-9496,新增jboss除JBoss seam2模板注入漏洞外的所有漏洞
-   2021-03-21 新增solr 全版本任意文件读取漏洞，新增F5 Big IP CVE-2021-22986 RCE Exp
-   2021-03-06 新增DVR 摄像头exp 新增Nexus Repository Manager exp。修改默认线程数为20。增加超时时间。增加界面显示shell的路径。修复cookie bug
-   2021-02-27 新增 CVE-2021-21972 Vmware vcenter exp
-   2021-02-24 修复thinkphp某处rce不能测试成功的bug
-   2021-02-21 新增fastjson jenkins exp/poc
-   2021-02-20 新增ElasticSearch exp/poc
-   2021-02-19 新增Drupal exp/poc
-   2021-02-16 新增tomcat unomi exp/poc
-   2021-02-15 新增activemq exp/poc
-   2021-02-14 新增solr exp/poc 结果增加了cve编号和漏洞名称
-   2021-02-12 更新solr 4个exp/poc 动图测试效果见本页底部
-   2021-02-08 更新solr CVE-2019-17558 一个CVE
-   2021-02-05 更新Dlink
-   2021-02-01 更新apachedruid
-   .......

工具编写背景:
-------

-   编写目的：  
    测试已经公开漏洞
-   背景  
    在公司内部有些早已经公开的漏洞比如struts2 thinkphp weblogic 这些需要批量测试用网上的工具有C#写的有python java 写的用这些工具都得装一下依赖库。python虽然很方面但是装库确实是很麻烦。另外本人也不擅长python。java可以可以跨平台但是java jdk 之间相互不兼容。另外java我没有.net擅长。go语言新崛起的语言听说是高并发很不错但是我不会 。另外外编译生成文件太大(主要是因为不会手动滑稽)。还是最后选择.net来编写
-   优点缺点  
    （1）缺点:不跨平台 poc exp少  
    （2）优点:本软件首先集成危害性较大前台rce(无需登录,或者登录绕过执行rce)。反序列化(利用链简单)。上传getshell。sql注入等高危漏洞直接就可以拿权限出数据。其次对一些构造复杂exp漏洞进行检测。傻瓜式主要导入url即可实现批量测试,能一键getshell检测绝不sql注入或者不是只检测。其中thinkphp 集成所有rce Exp Struts2漏洞集成了shack2 和k8 漏洞利用工具所有Exp并对他们的exp进行优化和修复。以后尽力融入所有好的利用工具exp和poc全部集成一体!!! 此工具的所集成漏洞全部是基于平时实战中所得到的经验从而写入到工具里。例如:通达oA一键getshell实战测试 struts2一键getshell 等等  
    (3)优点:本软件虽然不能直接由用户自定义编写exp或者poc。但是支持代理模式用户可以直接抓取poc或者exp放到bp抓包工具中进行手工测试。另外除了getshell如果失败的话会返回测试的payload详情同样可以由用户把exp导入bp中进行测试。而且把不确定成功与否的漏洞详情写入maybevul.txt中用户可以自己手工测试到底是漏洞不存在还是被拦截了。这样大大增加了成功率。相比于其他软件exp内置并且不支持代理直接抓取软件内部exp。即使失败了也搞不清楚到底是exp问题还是被拦截了

WebFrameworkTools-5.1-main 5.0工具使用方法
------------------------------------

### 内置exp模式

url.txt 中网站一行一个且必须以http:// https:// 开头  
启动勾选模式,需要创建include.txt。模块一行一个具体看 勾选功能演示  
启动排除模块模式,需要创建uninclude.txt。模块一行一个具体看 排除模块功能演示  
WebFrameworkTools-5.1-main.exe 所有exp都跑使用默认线程模式(注意劲量不要使用全部模块一个耗时太长。另一个有waf被ban ip导致速度变慢建议使用勾选模块方式或者指定模块。如果您确定没有waf什么影响那么全部模块没毛病!!!)  
WebFrameworkTools-5.1-main.exe -m 列出所有内置模块名称  
WebFrameworkTools-5.1-main.exe -thread 200 所有exp都跑使用自定义线程模式  
WebFrameworkTools-5.1-main.exe -type thinkphp 使用默认线程跑 thinkphp框架漏洞使用说明  
WebFrameworkTools-5.1-main.exe -type thinkphp -thread 200 使用自定义线程 线程跑 thinkphp框架漏洞  
WebFrameworkTools-5.1-main.exe -url http://www.baidu.com  
WebFrameworkTools-5.1-main.exe -url http://www.baidu.com -thread 30  
WebFrameworkTools-5.1-main.exe -url http://www.baidu.com/ -type thinkphp  
WebFrameworkTools-5.1-main.exe -url http://www.baidu.com -type thinkphp -thread 30  

### 用户自定义dll模式

同目录下创建userdll.txt即可进入用户自定义模式 WebFrameworkToolsUser.exe 跑所有dll  
WebFrameworkToolsUser.exe -thread 30 线程是30跑所有dll  
WebFrameworkToolsUser.exe -dllname test.dll 默认线程跑test.dll(test.dll为例子此处名字是任意)  
WebFrameworkToolsUser.exe -dllname test.dll -thread 30 30个线程跑test.dll(test.dll为例子此处名字是任意)  
WebFrameworkToolsUser.exe -url http://www.baidu.com 指定网站默认线程跑所有dll  
WebFrameworkToolsUser.exe -url http://www.baidu.com -thread 30 指定网站30个线程跑所有dll  
WebFrameworkToolsUser.exe -url http://www.baidu.com -dllname test.dll 默认线程跑指定dll(由于只有一个dll一个网站就使用默认线程就行了)  
一键生成dll,Dllplugins.dll 是内置dll不要尝试加载。对于批量dll话在软件目录添加一个dll目录即可进行批量。其他和内置exp操作一样。注意一键生成dll软件除post数据框那里可以有带双引号的数据。其他所有地方都不允许有双引号否则会编译失败!!!使用如下图:

演示忘记截图加ThreadHelper.dll 必须要有否则报错。。 如果要使用勾选功能见上图实测效果。勾选功能演示。如果想启用排除模块功能,请看排除模块功能截图演示 如果想自定义作者见自定义作者演示图  

### 内置exp模块

集成漏洞如下(-type参数) 注意有的type参数虽然标注了两个类别但并不代表这个参数只包含这两个漏洞!!!!  
thinkphp  
weblogic  
struts2  
hadoop  
atlassiancrowd  
ueditor  
tongdaoa  
apacheflink  
ruijie  
apachedruid  
router(dlink rce漏洞,三星路由器,dlink密码泄露,飞鱼星路由器信息泄露,中国移动 禹路由未获授权访问,密码敏感信息泄露, D-Link ShareCenter DNS-320 rce,Dlink 弱密码) cloudRouter密码泄露,三星 wlan AP 命令执行  
solr  
activemq  
tomcat  
unomi  
es  
fastjson  
jenkins  
vmvcenter  
webcam(DVR摄像头,D-Link-DCS,ACTI Camera 任意文件读取漏洞,海康威视流媒体密码泄露,任意文件读取,浙江大华DSS 任意文件下载, Finetree-5MP-摄像机 未授权添加账号密码,弱密码，海康威视视频网管任意文件读取,汇捷通云视频任意文件读取,Jellyfin 任意文件读取漏洞, Selea OCR-ANPR摄像机文件读取漏洞,H5S视频平台未授权)  
nexus  
bigip  
messasolu  
ofbiz  
jboss  
shiro  
springboot  
weaveroa(泛微OA,泛微 Emoblie 6.6 RCE),WorkflowServicexml rce,泛微OA 任意文件上传xday  
hwcms(帆软 V9 任意文件覆盖文件上传，浪潮ClusterEngine 4.0 RCE,和信下一代云桌面VENGD 上传漏洞,齐治科技-堡垒机任意用户登录，红帆oA,金山 V8 终端安全系统,启莱OAsql注入漏洞) 汉王考勤系统sql注入漏洞,金何OA C6 任意文件读取漏洞,极通EWEBS任意文件包含, ShiziyuCms 注入,ShopOX 任意文件下载漏洞,TamronOS IPTV命令执行协达Oa 任意文件下载 任务调度弱口令,好视通文件读取漏洞,xx捷CRM,教学管理ERP  
firewall(360新天擎sql注入(线程调到最低!!!测试否则会漏洞网站),360新天擎未授权接口访问,奇安信 网康防火墙 代码执行,FineReport（帆软）报表系统目录遍历漏洞) h3防火墙任意文件读取漏洞,佑友-佑友防火墙命令执行,Zeroshell 防火墙rce,xxx一体机rce漏洞  
seeyonoa(致远OA)  
yongyougrp((用友GRP))  
eyou  
voip  
thinkcmf  
natshell(蓝海卓越宽带计费系统)  
h3c(h3c intelligent management)  
yongyouuf(用友UFiDa BshServlet rce)  
ezoffice(万户ezOFFICE上传漏洞)  
yapi  
nacos  
apachekylin  
atlassianjira  
coremail  
landrayoa  
yongyouu8  
git(git信息泄露)  
dkey  
webui  
webmail  
yunwei(Kyan账号密码泄露,AI网络运维平台RCE)  
zujian(php v8.1 后门)  
sangfor  
wlan(AC集中管理平台弱口令)  
vpn(网康 NS-ASG 应用安全网关文件下载)  
atlassianconfl  
phpstudy  
apache  
gitlab(CVE-2021-22205,gitlab 邮箱信息泄露)  
baoleiji  
apachesou(CVE-2021-37580)  
weiphp  
upload(以后此为上传组件类集合:webuploader)  
gateway(网关,流媒体,视频终端合集,接口)  
nodejs  
x5  
konga  
drupal  
joomla  
grafana  
bootdo  
log4j(Http Header Fuzzing(16)|Apache SkyWalking|Seeyon OA|MobileIrons|Apache solr|APACHE-Druid|APACHE OFBiz No Testing|APACHE Struts2|vmware-Horizon|vmware vcenter|XenMobile|UniFiNetwork|vmware-Workspace No Testing!!!|weblogic log4j)  
phpmyadmin(phpmyadmin相关漏洞更新)  
apisix(Apache APISIX Dashboard)  
hardware(硬件漏洞)  
htoa  
api(接口漏洞集合)  
sunlogin  
zabbix  
spring(此为spring类型漏洞集合)  
cms(常见cms cmseasy)  
vmware(vmwareworkspace,vmware系列产品集合)  
zimbra(zimbra系列产品漏洞集合)  
oaAll(不知名oa漏洞集合)  
如果会在软件同目录下生产shell.txt。注意括号内的不是type参数是支持哪些漏洞例如router(dlink,三星路由器) 这个-type router这么写就o了

软件使用注意事项
--------

-   软件需要安装.netframwork 4.5.1 极其以上版本并且需要安装C++类库
-   使用自定义模式单个url。可以自己指定线程设置线程小。用默认线程20出的结果可能不准确
-   本来软件不打算集成例如文件读取信息泄露等漏洞。但是为了渗透实战中获取更大成果决定以后加入除直接拿shell,rce等高危漏洞其他次高危漏洞和某些有价值的中危漏洞!!!。另外本软件只集成框架漏洞。但是为了因为实战中资产数目庞大可能涉及的不只是框架还有可能目标旁站或者C段有某些cms。所以现决定把特征不明显的cms加入本软件特征明显并且是直接出数据和getshell的加入我的另一款图形化工具cms识别自动测试的工具。CmsExpAttackProgram中。两者互相查漏补缺。相互扶持发挥它们各自的优势!!!
-   另外说一下跑沙箱检测的有爆毒。怀疑是木马文件的这些人建议删除本软件别用就行。此软件采用c#和c++混合开发另外加了net和c++的强壳。如果爆毒属于正常如果有人担心木马病毒那么建议删除本软件。另外软件免费。我没有求着你们用。软件打不开的问题看git说明。别动不动脑残就知道发issu和私信。私信几十封我真看不过来。。。。
-   切勿利用本工具对未授权的网站进行非法攻击。由此产生的法律后果由使用者自行承担!!!
-   2021-04-24加入勾选功能如果需要使用勾选功能在同目录创建include.txt里面加入自定义的检测类型即可。使用效果(见:上图实测效果 勾选功能演示)。线程设置和全选一样直接设置即可。include.txt可以删除或者改名如果不用勾选功能的话!!!!
-   注意(非常非常重要):线程数不要设置太大。线程数越大结果越不准确!!!!!。尽量调低线程数字或者就用默认线程跑就行了!!!!
-   非回显漏洞采用dnslog 验证确保联网。如果在局域网不联网环境下dnslog验证的漏洞全部无法验证。采用dnslog验证如果icmp不出网可能会漏掉某些有漏洞的网站
-   遇到postData是jason格式时候必须 Content-type:application/json 而不是默认格式  
    
-   Dlink漏洞需要有WebFrameworkTools.exe.config 并且一个网站一分钟内最多可以检测三次超过三次即使漏洞存在也检测不到 这个目前反弹shell方式不清楚  
    
-   solr CVE-2017-12629 漏洞检测时间耗时较长请耐心等待结果
-   建议进行针对对性漏洞测试全量跑耗时就容易被waf封  
    
-   为了避免被非法利用工具软件最大支持检测url个数为100条
-   如果工具有误报请把你的截图附上关键url可打码。如果是-type参数请指明。啥也没有我不好判断bug点!!!!感谢支持。一起携手打造web框架自动化测试工具

为什么有的框架集成了部分漏洞,为什么有的框架漏洞没有集成
----------------------------

-   因为这个是批量不是专项检测工具。有的漏洞利用链很复杂要调用外部程序生成payload进行检测。很耗时另外有的exp或者poc只针对特定版本。不同版本exp不同。无法确定版本的时候导致很难准确进行漏洞检测和利用。如果漏洞链条太长本工具只集成判断是否使用该漏洞的框架例如:shiro 只判断网站是否使用shiro框架不进行任何poc和exp操作!!!请使用专用工具进行测试!!!!  
    

上图实测效果
------

Microsoft share point CVE-2025-53770

  

自定义作者演示

  

CVE-CVE-2021-22205  

YAPI RCE 漏洞实战测试

  

网东统一通信平台 045 漏洞实战一键getshell

  
勾选功能演示

  

列出软件内置模块截图

  

  

排除模块功能演示

  

CVE-2021-30461 VOIP Monitor RCE 演示截图

  
HVV部分漏洞实战测试 360新天擎注入

  

jboss漏洞测试图

  

CVE-2021-21972 Vmware vcenter 最新漏洞测试结果  

  
windows主机测试  

通达oA一键getshell实战测试注意由于网站数量少所以采用自定义线程数来跑如果采用默认线程那么结果不准确

  
druid测试批量测试 ApacheFlink实战png ActiveMQ测试 solr动图测试 solr新增exp测试图 测试结果 同类软件Unomi测试对比:某软件测试结果速度有点慢可能是线程开的小 我们的软件测试结果和速度几分钟搞定

Apache APISIX Dashboard CVE-2021-45232

5.0自定义Exp PhpStudyRce 功能演示截图

向日葵RCE

禅道测试

harbor 未授权访问-CVE-2022-46463

Nacos 身份认证绕过漏洞(QVD-2023-6271) 测试截图

MinIO信息泄露漏洞(CVE-2023-28432) 测试截图

瑞友天翼应用虚拟化系统远程代码执行漏洞(QVD-2023-8621) 演示截图

CVE-2023-34960漏洞演示截图

webframeworktools 第三方调用ini测试截图

2023hw漏洞更新截图

wordpress RCE-CVE-2024-25600

QVD-2024-11354 Eoffice 10 远程代码执行漏洞一键getshell

CVE-2024-5084 50个网站测试截图 动图

静态图

GeoServer RCE（CVE-2024-36401）

QVD-2024-44346

CVE-2025-48828|CVE-2025-48827
