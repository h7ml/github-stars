---
project: zan-proxy
stars: 1834
description: An extensible proxy for PC/Mobile/APP developer
url: https://github.com/youzan/zan-proxy
---

A proxy for your debug environment

访问中文版

`Zan Proxy` is an HTTP proxy server written in Node.js, which can be used to modify requests and mock reponse data. It is also a tool for custom DNS resolving and requests monitoring. The proxy server can be easily configured by a user-friendly interface. In addition, a mechanism is provided for developers to customize the behavior of the server.

Features
--------

-   Clean and user-friendly interface
-   Support HTTP, HTTPS and websocket
-   Support remote redirect rules
-   Modify the request target
-   Mock the response data
-   Custom plugins to modify default behaviour
-   Custom DNS resolving
-   GUI Configuration

Installation
------------

Download from Github.

### Upgrade To v5

Zan Proxy v5.0.0 did some incompatible change，you should pay attention to something when upgrading：

1.  To fit macOS 10.15 and ios 13, we replaced the Zan Proxy certificate(from 1024 bits to 2048 bits), we will automatically install the certificate for you on the Mac, but on other devices(like Windows、phone), you have to install the certificate manually.
2.  Change some config file fields, but you need not update it manually, Zan Proxy will update these files automatically.

Interface
---------

### GUI

### Web

Documentation
-------------

The detailed documentation can be refered here.

Running From Source Code
------------------------

1.  install dependencies
    
    yarn
    cd webui && yarn
    
2.  start webui development mode
    
    yarn dev:ui
    
3.  start cli/gui development mode
    
    yarn dev:cli  # cli development mode
    yarn dev:gui  # gui development mode
    
4.  build
    
    yarn build:cli
    yarn build:gui
    

Plugins List
------------

-   zp-print-url print the urls
-   zp-debug-tool web debug tool

(PRs are welcomed to append the list)

Links
-----

-   Vue UI
-   React UI
-   Weapp UI

Wechat Group
------------

Scan the qrcode to join our wechat discussion group, please note that you want to join ZanProxy discussion group.

LICENSE
-------

MIT
