---
project: proxy_pool
stars: 22747
description: Python ProxyPool for web spider
url: https://github.com/jhao104/proxy_pool
---

ProxyPool 爬虫代理IP池
=================

```
______                        ______             _
| ___ \_                      | ___ \           | |
| |_/ / \__ __   __  _ __   _ | |_/ /___   ___  | |
|  __/|  _// _ \ \ \/ /| | | ||  __// _ \ / _ \ | |
| |   | | | (_) | >  < \ |_| || |  | (_) | (_) || |___
\_|   |_|  \___/ /_/\_\ \__  |\_|   \___/ \___/ \_____\
                       __ / /
                      /___ /
```

### ProxyPool

爬虫代理IP池项目,主要功能为定时采集网上发布的免费代理验证入库，定时验证入库的代理保证代理的可用性，提供API和CLI两种使用方式。同时你也可以扩展代理源以增加代理池IP的质量和数量。

-   文档: document
    
-   支持版本:
    
-   测试地址: http://demo.spiderpy.cn (勿压谢谢)
    
-   付费代理推荐: luminati-china. 国外的亮数据BrightData（以前叫luminati）被认为是代理市场领导者，覆盖全球的7200万IP，大部分是真人住宅IP，成功率扛扛的。付费套餐多种，需要高质量代理IP的可以注册后联系中文客服。申请免费试用 目前有50%折扣优惠活动。(PS:用不明白的同学可以参考这个使用教程)。
    

### 运行项目

##### 下载代码:

-   git clone

git clone git@github.com:jhao104/proxy\_pool.git

-   releases

https://github.com/jhao104/proxy\_pool/releases 下载对应zip文件

##### 安装依赖:

pip install -r requirements.txt

##### 更新配置:

\# setting.py 为项目配置文件

\# 配置API服务

HOST \= "0.0.0.0"               \# IP
PORT \= 5000                    \# 监听端口

\# 配置数据库

DB\_CONN \= 'redis://:pwd@127.0.0.1:8888/0'

\# 配置 ProxyFetcher

PROXY\_FETCHER \= \[
    "freeProxy01",      \# 这里是启用的代理抓取方法名，所有fetch方法位于fetcher/proxyFetcher.py
    "freeProxy02",
    \# ....
\]

#### 启动项目:

# 如果已经具备运行条件, 可用通过proxyPool.py启动。
# 程序分为: schedule 调度程序 和 server Api服务

# 启动调度程序
python proxyPool.py schedule

# 启动webApi服务
python proxyPool.py server

### Docker Image

docker pull jhao104/proxy\_pool

docker run --env DB\_CONN=redis://:password@ip:port/0 -p 5010:5010 jhao104/proxy\_pool:latest

### docker-compose

项目目录下运行:

docker-compose up -d

### 使用

-   Api

启动web服务后, 默认配置下会开启 http://127.0.0.1:5010 的api接口服务:

api

method

Description

params

/

GET

api介绍

None

/get

GET

随机获取一个代理

可选参数: `?type=https` 过滤支持https的代理

/pop

GET

获取并删除一个代理

可选参数: `?type=https` 过滤支持https的代理

/all

GET

获取所有代理

可选参数: `?type=https` 过滤支持https的代理

/count

GET

查看代理数量

None

/delete

GET

删除代理

`?proxy=host:ip`

-   爬虫使用

　　如果要在爬虫代码中使用的话， 可以将此api封装成函数直接使用，例如：

import requests

def get\_proxy():
    return requests.get("http://127.0.0.1:5010/get/").json()

def delete\_proxy(proxy):
    requests.get("http://127.0.0.1:5010/delete/?proxy={}".format(proxy))

\# your spider code

def getHtml():
    \# ....
    retry\_count \= 5
    proxy \= get\_proxy().get("proxy")
    while retry\_count \> 0:
        try:
            html \= requests.get('http://www.example.com', proxies\={"http": "http://{}".format(proxy)})
            \# 使用代理访问
            return html
        except Exception:
            retry\_count \-= 1
    \# 删除代理池中代理
    delete\_proxy(proxy)
    return None

### 扩展代理

　　项目默认包含几个免费的代理获取源，但是免费的毕竟质量有限，所以如果直接运行可能拿到的代理质量不理想。所以，提供了代理获取的扩展方法。

　　添加一个新的代理源方法如下:

-   1、首先在ProxyFetcher类中添加自定义的获取代理的静态方法， 该方法需要以生成器(yield)形式返回`host:ip`格式的代理，例如:

class ProxyFetcher(object):
    \# ....

    \# 自定义代理源获取方法
    @staticmethod
    def freeProxyCustom1():  \# 命名不和已有重复即可

        \# 通过某网站或者某接口或某数据库获取代理
        \# 假设你已经拿到了一个代理列表
        proxies \= \["x.x.x.x:3128", "x.x.x.x:80"\]
        for proxy in proxies:
            yield proxy
        \# 确保每个proxy都是 host:ip正确的格式返回

-   2、添加好方法后，修改setting.py文件中的`PROXY_FETCHER`项：

　　在`PROXY_FETCHER`下添加自定义方法的名字:

PROXY\_FETCHER \= \[
    "freeProxy01",    
    "freeProxy02",
    \# ....
    "freeProxyCustom1"  \#  # 确保名字和你添加方法名字一致
\]

　　`schedule` 进程会每隔一段时间抓取一次代理，下次抓取时会自动识别调用你定义的方法。

### 免费代理源

目前实现的采集免费代理网站有(排名不分先后, 下面仅是对其发布的免费代理情况, 付费代理测评可以参考这里):

代理名称

状态

更新速度

可用率

地址

代码

站大爷

✔

★

\*\*

地址

`freeProxy01`

66代理

✔

★

\*

地址

`freeProxy02`

开心代理

✔

★

\*

地址

`freeProxy03`

FreeProxyList

✔

★

\*

地址

`freeProxy04`

快代理

✔

★

\*

地址

`freeProxy05`

冰凌代理

✔

★★★

\*

地址

`freeProxy06`

云代理

✔

★

\*

地址

`freeProxy07`

小幻代理

✔

★★

\*

地址

`freeProxy08`

免费代理库

✔

☆

\*

地址

`freeProxy09`

89代理

✔

☆

\*

地址

`freeProxy10`

稻壳代理

✔

★★

\*\*\*

地址

`freeProxy11`

如果还有其他好的免费代理网站, 可以在提交在issues, 下次更新时会考虑在项目中支持。

### 问题反馈

　　任何问题欢迎在Issues 中反馈，同时也可以到我的博客中留言。

　　你的反馈会让此项目变得更加完美。

### 贡献代码

　　本项目仅作为基本的通用的代理池架构，不接收特有功能(当然,不限于特别好的idea)。

　　本项目依然不够完善，如果发现bug或有新的功能添加，请在Issues中提交bug(或新功能)描述，我会尽力改进，使她更加完美。

　　这里感谢以下contributor的无私奉献：

　　@kangnwh | @bobobo80 | @halleywj | @newlyedward | @wang-ye | @gladmo | @bernieyangmh | @PythonYXY | @zuijiawoniu | @netAir | @scil | @tangrela | @highroom | @luocaodan | @vc5 | @1again | @obaiyan | @zsbh | @jiannanya | @Jerry12228

### Release Notes

changelog
