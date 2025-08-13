---
project: dsback
stars: 120
description: 系统监控、数据库备份、文件备份、定时备份、DDOS防护、中间件安装、钉钉通知、企业微信通知
url: https://github.com/npsvip/dsback
---

Panel DB
========

Panel DB是一款免费、支持多系统、多种中间件安装、多种数据库定时备份、文件定时备份、系统监控、钉钉通知、企业微信通知、服务器DDOS防护、病毒查杀等功能的运维面板，支持docker离线部署，支持在线更新

_**\# 软件功能**_  
支持Linux全平台，多种数据库、文件定时备份，多种服务器中间件安装，企业微信通知，系统DDOS防御及防攻击优化等

系统及通知  
      ● Linux全平台(中间件安装及系统防护功能仅支持Centos、Ubuntu、Debian)  
      ● Windows Server  
      ● 钉钉实时通知  
      ● 邮箱实时通知  
      ● 企业微信实时通知  

数据库备份  
      ● Mysql  
      ● SqlServer  
      ● MongoDb  
      ● PostgreSql

文件备份  
      ● 全量备份  
      ● 增量备份  

中间件安装  
      ● Redis  
      ● Mysql  
      ● SqlServer  
      ● MongoDb  
      ● PostgreSql  
      ● Docker  
      ● Nginx

系统防护  
      ● DDOS防御脚本  
      ● SYN攻击优化  
      ● 防端口扫描  
      ● 禁UDP  
      ● 禁PING  
      ● 禁止国外IP  
      ● 病毒查杀  

_**\# 安装教程**_  
step1:  
创建mysql数据库，表结构sql文件上面已经给了,下载后导入数据库即可  

step2:  
一行docker命令即可，参数解释如下  
ENV ip=数据库IP,默认127.0.0.1  
ENV port=数据库端口,默认3306  
ENV db=数据库名称,默认dsback  
ENV dbUserName=数据库账户,默认root  
ENV dbPassWord=数据库密码,默认root  
ENV sysUserName=登录面板账户,默认admin  
ENV sysPassWord=登录面板密码,默认admin  

示例如下：  

```
docker run -d --name dsback --restart=always -p 8080:8080 -e ip=你的数据库IP -e port=你的数据库端口 -e db=你的数据库 -e dbUserName=你的数据库账号 -e dbPassWord=你的数据库密码 -e sysUserName=admin -e sysPassWord=admin -v 你的本地日志目录:/opt/logs/api/ aeert/dsback:latest

# ARM架构可选择 aeert/dsback:arm 或 aeert/dsback:arm64 镜像
```

或者直接运行上方脚本  
`./panelDB.sh`

**软件截图**
