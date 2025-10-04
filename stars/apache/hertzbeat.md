---
project: hertzbeat
stars: 6689
description: Real-time observability system with agentless, performance cluster, prometheus-compatible, custom monitoring and status page building capabilities.
url: https://github.com/apache/hertzbeat
---

**Readme**: **English** | 中文 | 日本語

> A real-time observability system with agentless, performance cluster, prometheus-compatible, custom monitoring and status page building capabilities.

**Home: hertzbeat.apache.org**  
**Email: Mail to `dev-subscribe@hertzbeat.apache.org` to subscribe mailing lists**

🎡 Introduction
---------------

Apache HertzBeat™ is an easy-to-use, open source, real-time observability system with agentless, high performance cluster, prometheus-compatible, offers powerful custom monitoring and status page building capabilities.

### Features

-   Combines **monitoring, alarm, and notification** features into one platform, and supports monitoring for web service, program, database, cache, os, webserver, middleware, bigdata, cloud-native, network, custom and more.
-   Easy to use and agentless, web-based and with one-click monitoring and alerting, zero learning curve.
-   Makes protocols such as `Http, Jmx, Ssh, Snmp, Jdbc, Prometheus` configurable, allowing you to collect any metrics by simply configuring the template `YML` file online. Imagine being able to quickly adapt to a new monitoring type like K8s or Docker simply by configuring online with HertzBeat.
-   Compatible with the `Prometheus` ecosystem and more, can monitoring what `Prometheus` can monitoring with few clicks on webui.
-   High performance, supports horizontal expansion of multi-collector clusters, multi-isolated network monitoring and cloud-edge collaboration.
-   Provides flexible alarm threshold rules and timely notifications delivered via `Discord` `Slack` `Telegram` `Email` `Dingtalk` `WeChat` `FeiShu` `Webhook` `SMS` `ServerChan`.
-   Provides powerful status page building capabilities, easily communicate the real-time status of your service to users.

> HertzBeat's powerful customization, multi-type support, high performance, easy expansion, and low coupling, aims to help users quickly build their own monitoring system.

* * *

* * *

🥐 Architecture
---------------

⛄ Supported
-----------

> We define all monitoring collection types such as `mysql`, `jvm`, and `k8s` as `YML` monitoring templates, allowing users to import them to support corresponding types of monitoring. Welcome everyone to contribute your customized general monitoring type YML template during use.

-   Website, Port Telnet, Http Api, Ping Connect, Jvm, SiteMap, Ssl Certificate, SpringBoot2, FTP Server, SpringBoot3, Udp Port, Dns, Pop3, Ntp, Api Code, Smtp, Nginx
-   Mysql, PostgreSQL, MariaDB, Redis, ElasticSearch, SqlServer, Oracle, MongoDB, DM, OpenGauss, ClickHouse, IoTDB, Redis Cluster, Redis Sentinel Doris BE, Doris FE, Memcached, NebulaGraph
-   Linux, Ubuntu, CentOS, Windows, EulerOS, Fedora CoreOS, OpenSUSE, Rocky Linux, Red Hat, FreeBSD, AlmaLinux, Debian Linux
-   Tomcat, Nacos, Zookeeper, RabbitMQ, Flink, Kafka, ShenYu, DynamicTp, Jetty, ActiveMQ, Spring Gateway, EMQX MQTT, AirFlow, Hive, Spark, Hadoop
-   Kubernetes, Docker
-   CiscoSwitch, HpeSwitch, HuaweiSwitch, TpLinkSwitch, H3cSwitch
-   And More Your Custom Template.
-   Notified Support `Discord` `Slack` `Telegram` `Email` `Dingtalk` `WeChat` `FeiShu` `Webhook` `SMS` `ServerChan`.

🐕 Quick Start
--------------

-   If you wish to deploy HertzBeat locally, please refer to the following Deployment Documentation for instructions.

### 🍞 Install HertzBeat

> HertzBeat supports installation through source code, docker or package, cpu support x86/arm64.

##### 1：Install quickly via docker

1.  Just one command to get started
    
    docker run -d -p 1157:1157 -p 1158:1158 --name hertzbeat apache/hertzbeat
    
2.  Access `http://localhost:1157` to start, default account: `admin/hertzbeat`
    
3.  Deploy collector clusters (Optional)
    
    docker run -d -e IDENTITY=custom-collector-name -e MANAGER\_HOST=127.0.0.1 -e MANAGER\_PORT=1158 --name hertzbeat-collector apache/hertzbeat-collector
    
    -   `-e IDENTITY=custom-collector-name` : set the collector unique identity name.
    -   `-e MODE=public` : set the running mode(public or private), public cluster or private cloud-edge.
    -   `-e MANAGER_HOST=127.0.0.1` : set the main hertzbeat server ip.
    -   `-e MANAGER_PORT=1158` : set the main hertzbeat server port, default 1158.

Detailed config refer to Install HertzBeat via Docker

##### 2：Install via package

1.  Download the release package `hertzbeat-xx.tar.gz` Download
2.  Configure the HertzBeat configuration yml file `hertzbeat/config/application.yml` (optional)
3.  Run command `$ ./bin/startup.sh` or `bin/startup.bat`
4.  Access `http://localhost:1157` to start, default account: `admin/hertzbeat`
5.  Deploy collector clusters (Optional)
    -   Download the release package `hertzbeat-collector-xx.tar.gz` to new machine Download
    -   Configure the collector configuration yml file `hertzbeat-collector/config/application.yml`: unique `identity` name, running `mode` (public or private), hertzbeat `manager-host`, hertzbeat `manager-port`
        
        collector:
          dispatch:
            entrance:
              netty:
                enabled: true
                identity: ${IDENTITY:}
                mode: ${MODE:public}
                manager-host: ${MANAGER\_HOST:127.0.0.1}
                manager-port: ${MANAGER\_PORT:1158}
        
    -   Run command `$ ./bin/startup.sh` or `bin/startup.bat`
    -   Access `http://localhost:1157` and you will see the registered new collector in dashboard

Detailed config refer to Install HertzBeat via Package

##### 3：Start via source code

1.  Local source code debugging needs to start the back-end project `manager` and the front-end project `web-app`.
2.  Backend：need `maven3+`, `java17`, `lombok`, add VM options in IDE: `--add-opens=java.base/java.nio=org.apache.arrow.memory.core,ALL-UNNAMED`, then start the `manager` service.
3.  Web：need `nodejs npm angular-cli` environment, Run `ng serve --open` in `web-app` directory after backend startup.
4.  Access `http://localhost:4200` to start, default account: `admin/hertzbeat`

Detailed steps refer to CONTRIBUTING

##### 4：Install All(hertzbeat+postgresql+tsdb) via Docker-compose

Install the postgresql/mysql database, victoria-metrics/iotdb/tdengine database and hertzbeat at one time through docker-compose deployment script.

Detailed steps refer to Install via Docker-Compose

##### 5: Install All(hertzbeat+collector+postgresql+tsdb) via kubernetes helm charts

Install HertzBeat cluster in a Kubernetes cluster by Helm chart.

Detailed steps refer to Artifact Hub

**HAVE FUN**

✨ Contributors
--------------

Thanks to these wonderful people, welcome to join us:  
Contributor Guide

  
**tomsun28**  
💻 📖 🎨

  
**会编程的王学长**  
💻 📖 🎨

  
**MaxKey**  
💻 🎨 🤔

  
**观沧海**  
💻 🎨 🐛

  
**yuye**  
💻 📖

  
**jx10086**  
💻 🐛

  
**winnerTimer**  
💻 🐛

  
**goo-kits**  
💻 🐛

  
**brave4Time**  
💻 🐛

  
**WalkerLee**  
💻 🐛

  
**jianghang**  
💻 🐛

  
**ChineseTony**  
💻 🐛

  
**wyt199905**  
💻

  
**卫傅庆**  
💻 🐛

  
**zklmcookle**  
💻

  
**DevilX5**  
📖 💻

  
**tea**  
💻

  
**yangshihui**  
💻 🐛

  
**DreamGirl524**  
💻 📖

  
**gzwlly**  
📖

  
**cuipiheqiuqiu**  
💻 ⚠️ 🎨

  
**lambert**  
💻

  
**mroldx**  
📖

  
**woshiniusange**  
📖

  
**VampireAchao**  
💻

  
**zcx**  
💻 🐛 🎨 ⚠️ 📝

  
**CharlieXCL**  
📖

  
**Privauto**  
💻 📖

  
**emrys**  
📖

  
**SxLiuYu**  
🐛

  
**All Contributors**  
📖

  
**铁甲小宝**  
💻 📖

  
**click33**  
📖

  
**蒋小小**  
📖

  
**Kevin Huang**  
📖

  
**铁甲小宝**  
🐛 💻 📖 ⚠️ 🎨

  
**Captain Jack**  
📖

  
**haibo.duan**  
⚠️ 💻

  
**assassin**  
🐛 💻

  
**Reverse wind**  
⚠️ 💻

  
**luxx**  
💻

  
**Ikko Ashimine**  
📖

  
**leizenan**  
💻

  
**BKing**  
📖

  
**xingshuaiLi**  
📖

  
**wangke6666**  
📖

  
**刺猬**  
🐛 💻

  
**Haste**  
💻

  
**zhongshi.yi**  
📖

  
**Qi Zhang**  
📖

  
**MrAndyMing**  
📖

  
**idongliming**  
💻

  
**Zichao Lin**  
💻 📖

  
**liudonghua**  
💻 🤔

  
**Jerry**  
💻 ⚠️ 🤔

  
**yanhom**  
📖

  
**fsl**  
💻

  
**xttttv**  
📖

  
**NavinKumarBarnwal**  
💻

  
**Zakkary**  
📖

  
**sunxinbo**  
💻 ⚠️

  
**ldzbook**  
📖 🐛

  
**余与雨**  
💻 ⚠️

  
**MysticalDream**  
💻 ⚠️

  
**zhouyoulin12**  
💻 ⚠️

  
**jerjjj**  
💻

  
**wjl110**  
💻

  
**Sean**  
📖

  
**chenyiqin**  
💻 ⚠️

  
**hudongdong129**  
💻 ⚠️ 📖 🎨

  
**TherChenYang**  
💻 ⚠️

  
**HattoriHenzo**  
💻 ⚠️

  
**ycilry**  
📖

  
**aoshiguchen**  
📖 💻

  
**蔡本祥**  
💻

  
**浮游**  
💻

  
**Grass-Life**  
💻

  
**xiaohe428**  
💻 📖

  
**TableRow**  
📖 💻

  
**ByteIDance**  
💻

  
**Jangfe**  
💻

  
**zqr10159**  
📖 💻 📝 🐛 ⚠️ 🎨

  
**vinci**  
💻 📖 🎨

  
**js110**  
💻

  
**CrazyLionLi**  
📖

  
**banmajio**  
💻

  
**topsuder**  
💻

  
**richar2022**  
💻

  
**fcb-xiaobo**  
💻

  
**wenkyzhang**  
📖

  
**ZangJuxy**  
📖

  
**l646505418**  
💻 🐛

  
**Carpe-Wang**  
💻 🐛

  
**莫枢**  
💻

  
**huangcanda**  
💻

  
**世纪末的架构师**  
💻

  
**ShuningWan**  
📖

  
**MrYZhou**  
📖

  
**suncqujsj**  
📖

  
**sunqinbo**  
💻

  
**haoww**  
📖

  
**i-mayuan**  
📖

  
**fengruge**  
📖

  
**zhanghuan**  
💻

  
**shenymin**  
💻

  
**Dhruva Chandra**  
💻

  
**miss\_z**  
📖

  
**wyt990**  
💻

  
**licocon**  
💻

  
**Mi Na**  
💻

  
**Kylin-Guo**  
📖

  
**Mr灬Dong先生**  
💻

  
**Pratyay Banerjee**  
📖 💻

  
**yujianzhong520**  
💻

  
**SPPan**  
💻

  
**ZhangJiashu**  
💻

  
**impress**  
💻

  
**凌晨一点半**  
📖

  
**Eeshaan Sawant**  
💻

  
**nandofromthebando**  
💻

  
**caiboking**  
💻

  
**baixing99**  
💻

  
**Yang Chuang**  
💻

  
**wlin20**  
💻

  
**guojing1983**  
💻

  
**moxi**  
📖

  
**qq471754603**  
💻

  
**渭雨**  
💻

  
**liuxuezhuo**  
💻

  
**lisongning**  
💻

  
**YutingNie**  
💻 📖 🎨

  
**Mike Zhou**  
💻 📖 🎨

  
**lynx009**  
💻 📖 📝 🐛 🎨

  
**littlezhongzer**  
💻

  
**ChenXiangxxxxx**  
💻

  
**Mr.zhou**  
💻

  
**姚贤丰**  
💻

  
**lingluojun**  
💻

  
**1ue**  
💻

  
**qyaaaa**  
💻 🐛

  
**novohit**  
💻

  
**zhuoshangyi**  
💻

  
**ruanliang**  
📖 💻

  
**Eden4701**  
💻 📖 🎨

  
**XiaTian688**  
📖

  
**liyinjiang**  
💻

  
**ZhangJiashu**  
📖

  
**moghn**  
📖

  
**xiaoguolong**  
💻

  
**Smliexx**  
💻 🐛

  
**Calvin**  
📖 💻 🎨 🐛 ⚠️

  
**Bala Sukesh**  
💻

  
**Jinyao Ma**  
💻

  
**Rick**  
💻 ⚠️

  
**东风**  
💻 🎨 📖 🐛

  
**sonam singh**  
💻

  
**ZhangZixuan1994**  
💻

  
**SHIG**  
💻

  
**泰上老菌**  
💻

  
**ldysdu**  
💻

  
**梁同学**  
💻

  
**avv**  
💻

  
**yqxxgh**  
📖 💻 🐛

  
**CharlieShi46**  
💻

  
**Nctllnty**  
💻

  
**Wang-Yonghao**  
📖

  
**读钓**  
💻

  
**Xin**  
💻 🐛

  
**handy**  
💻

  
**LiuTianyou**  
💻 📖 🐛 ⚠️ 📝 🎨

  
**WinterKi1ler**  
💻

  
**miki**  
💻

  
**Keshav Carpenter**  
💻 📖

  
**makechoicenow**  
💻

  
**Gao Jian**  
⚠️ 💻 📖 🎨 🐛

  
**Hyeon Sung**  
💻 📖

  
**crossoverJie**  
💻 📖 📝 ⚠️ 🎨

  
**PeixyJ**  
💻

  
**风如歌**  
💻

  
**Manan Pujara**  
💻

  
**xuziyang**  
💻 📖 🐛

  
**lwqzz**  
💻

  
**YxYL**  
💻

  
**tomorrowshipyltm**  
📖

  
**栗磊**  
💻

  
**Alan**  
📖

  
**Jast**  
💻 🤔 📖 📝 🐛 ⚠️ 🎨

  
**Zhang Yuxuan**  
💻 📖 🐛 📝 ⚠️

  
**P.P.**  
💻

  
**llp2333**  
💻

  
**feiyang li**  
📖

  
**aias00**  
💻 📖 🐛 🤔 ⚠️

  
**Jin**  
📖

  
**YuLuo**  
💻 🐛 ⚠️ 📝

  
**linDong**  
💻 📖 🐛

  
**lwjxy**  
💻

  
**John**  
💻 📖

  
**boatrainlsz**  
📖

  
**Bill Lau**  
💻

  
**lwyang**  
📖

  
**xfl12345**  
📖

  
**Limbo**  
💻

  
**哈哈哈哈哈哈哈哈哈**  
💻

  
**Leon Li**  
💻

  
**dennis zhuang**  
💻

  
**Kerwin Bryant**  
🎨 💻 📖 🐛

  
**daixianglong**  
📖

  
**mchgood**  
📖

  
**kangli**  
💻 📖 🐛

  
**cdphantom**  
💻

  
**jiawei.guo**  
💻

  
**QBH-insist**  
💻

  
**jiangsh**  
💻

  
**Keaifa**  
💻 🐛

  
**Loong**  
💻

  
**Chandrakant Vankayalapati**  
💻

  
**b\_mountain**  
💻

  
**TemirlanBasitov**  
💻

  
**wyfvsfy**  
📖

  
**sherry-peng2333**  
💻

  
**Yzzz**  
💻

  
**puruidong**  
📖

  
**shinestare**  
💻

  
**po-168**  
💻

  
**wbs99**  
💻

  
**starryCoder**  
💻

  
**hasimmollah**  
💻

  
**Ayu**  
💻

  
**Nick Guo**  
📖 💻 🐛

  
**doveLin**  
💻

  
**yunfan24**  
💻 📖 🐛 ⚠️ 📝

  
**nullwli**  
💻

  
**Simon Sigré**  
📖 💻

  
**ponfee**  
💻

  
**Vedant7789**  
💻

  
**Craaaaazy77**  
📖

  
**Suvrat1629**  
💻

  
**ghy**  
💻

  
**helei1030**  
📖

  
**PJ Fanning**  
💻 🐛 ⚠️

  
**monster**  
💻

  
**Sherlock Yin**  
💻 📖 🐛

  
**wanhao**  
💻 📖

  
**jonasHanhan**  
💻

  
**NikhilMurugesan**  
💻

  
**myangle1120**  
💻

  
**yasminvo**  
💻

  
**不关银渐层的事哦**  
💻 🐛

  
**yyahang**  
💻

  
**jujin**  
💻 📖 🤔 📝

  
**LL-LIN**  
💻 🐛

  
**Yang Chen**  
💻 📖 🐛

  
**Sarthak Arora**  
💻 📖

  
**彭镜肇**  
💻

  
**Walter Jia**  
💻

  
**boyucjz**  
💻

  
**Cyanty**  
💻 📖

  
**Jay丿167**  
💻

  
**Duansg**  
📖

  
**zhangyaxi**  
💻 ⚠️

  
**songyg**  
📖

  
**Liuxin**  
💻

  
**yy549159265**  
💻 ⚠️ 🎨

  
**cto-huhang**  
📖

  
**LunaRain\_079**  
📖

  
**DeleiGuo**  
📖 💻 ⚠️ 🐛

  
**Rocky, Chi**  
💻

  
**Wenqi Luo**  
🐛

  
**tuzuy**  
💻 🎨

  
**carl pinto**  
💻

💬 Join discussion
------------------

##### Channel

Join the Mailing Lists : Mail to `dev-subscribe@hertzbeat.apache.org` to subscribe mailing lists.

Chat On Discord

WeChat Group : Add friend `ahertzbeat` and invite to the group.

WeChat Public : Search ID `usthecom`.

QQ Group : Group num `1035688434`

Github Discussion

Reddit Community

Follow Us Twitter

Subscribe YouTube

##### Open-Source Project Build From Open-Source

HertzBeat is built on so many great open source projects, thanks to them!

-   `Java Spring SpringBoot Jpa Maven Assembly Netty Lombok Sureness Protobuf HttpClient Guava SnakeYaml JsonPath ...`
-   `TypeScript Angular NG-ZORRO NG-ALAIN NodeJs Npm Html Less Echarts Rxjs ZoneJs MonacoEditor SlickCarousel Docusaurus ...`

Landscape
---------

    
  
HertzBeat has been included in the CNCF Observability And Analysis - Observability Landscape.

🛡️ License
-----------

`Apache License, Version 2.0`
