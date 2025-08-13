---
project: okjiasu_action
stars: 19
description: 机场https://okjiasu.com    的自动签到脚本
url: https://github.com/Wiederhoeft/okjiasu_action
---

🏵️ okjiasu\_action
===================

基于github工作流的okjiasu.com签到脚本。可白嫖流量！

服务支持
----

-   github actions
-   本地运行

注册
--

-   邀请注册 h7ml
-   直接注册 无邀请码

功能说明
----

**每日定时签到,白嫖机场流量**

使用 github workflows 进行托管
------------------------

h7ml/okjiasu\_action **大约在每天的北京时间 8：00 左右执行**

1.  Fork 仓库
    
2.  在仓库 `Settings->Secrets->Actions`中添加如下几个变量：
    
    NAME
    
    VALUE
    
    EMAIL\_USER
    
    发送邮件的邮箱账号
    
    EMAIL\_PASS
    
    发送邮件的授权码
    
    USER\_EMAIL
    
    接收通知的邮箱账号
    
    OK\_USER
    
    okjiasu - 账号
    
    OK\_PASSWORD
    
    okjiasu - 密码
    
3.  在 `Settings->Actions`确保 actions 是开启状态
    
4.  关于发送邮件通知，本项目通知使用的是 qq 邮箱，如果你想使用其他邮件服务商进行推送，记得在`config.js`的`email.provider`选项中进行配置修改
    

-   QQ 邮箱-POP3/SMTP/IMAP
-   nodemailer 参考手册

本地运行
----

1.  clone 本仓库
    
    git clone https://github.com/h7ml/okjiasu\_action.git
    
2.  进入项目
    
    cd okjiasu\_action
    
3.  安装依赖
    
    yarn install
    
4.  在项目根目录新建 `.env` 文件，内容如下：
    
    ```
    # 发送邮件的邮箱账号
    EMAIL_USER=""
    
    # 发送邮件的授权码
    EMAIL_PASS=""
    
    # 接收通知的邮箱账号
    USER_EMAIL=""
    
    # okjiasu - 账号
    OK_USER=""
    
    # okjiasu - 密码
    OK_PASSWORD=""
    ```
    
5.  `yarn install` 安装完依赖后，执行 `yarn run serve` 即可
    
6.  在`index.js` 中 配置 `headless:false` 可显示浏览器界面(部署时记得改为 true)
    

今日免费节点
------

### 采集时间: 2023-05-03 12:17:06

节点名称

节点链接

节点二维码
