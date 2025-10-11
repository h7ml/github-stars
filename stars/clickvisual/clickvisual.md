---
project: clickvisual
stars: 1615
description: A lightweight log analytic and data visualize platform  built on clickhouse.
url: https://github.com/clickvisual/clickvisual
---

ClickVisual
===========

English | 中文

ClickVisual is a lightweight browser-based logs analytics and logs search platform for ClickHouse, we are from @OfficeSDK

### Documentation

See https://clickvisual.net

### Log Query Demonstration

### Alarm Process Demonstration

### DAG Workflow

### Configuration Page

Features
--------

-   Support visual query dashboard, query histogram and raw logs for SQL.
-   Support showing percentage for specified fields.
-   Support vscode style configuration board, you can easily emit your fluent-bit configuration to Kubernetes ConfigMap.
-   Out of the box, easily deployment with `kubectl`.
-   Support for GitHub and GitLab Authentication.

Architecture
------------

Installation
------------

-   For Docker

# clone clickvisual source code.
git clone https://github.com/clickvisual/clickvisual.git

# you may need to set docker image mirror, visit <https://github.com/yeasy/docker\_practice/blob/master/install/mirror.md> for details.
docker-compose up

# then go to browser and visit http://localhost:19001.
# login username: clickvisual 
# login password: clickvisual

-   For host

# download release.
# get latest version.
latest=$(curl -sL https://api.github.com/repos/clickvisual/clickvisual/releases/latest | grep  ".tag\_name" | sed -E 's/.\*"(\[^"\]+)".\*/\\1/')

# for MacOS amd64.
wget "https://github.com/clickvisual/clickvisual/releases/download/${latest}/clickvisual-${latest}\-darwin-amd64.tar.gz" -O clickvisual-${latest}.tar.gz 

# for Linux amd64.
wget "https://github.com/clickvisual/clickvisual/releases/download/${latest}/clickvisual-${latest}\-linux-amd64.tar.gz" -O clickvisual-$(latest).tar.gz  

# extract zip file to current directory.
mkdir -p ./clickvisual-${latest} && tar -zxvf clickvisual-${latest}.tar.gz -C ./clickvisual-${latest}

# open config/default.toml, then change database and redis or other section configuration
# execute migration latest sql script in scripts/migration directory
# start clickvisual
cd ./clickvisual-${latest} && ./clickvisual -config config/default.toml

# then go to browser and visit http://localhost:19001
# login username: clickvisual
# login password: clickvisual

Document Contribution
---------------------

If you want to participate in https://clickvisual.net document updating activities  
Please refer to this document https://github.com/clickvisual/clickvisual/tree/master/docs

Join Us
-------

Join us, please add the "cv" keyword in the verification information.

Wechat id is "MEXES\_"

Contributors
------------

Thanks for these wonderful people:

  
**MEX7**

  
**m1666**

  
**askuy**

  
**sevennt**

  
**LincolnZhou**

  
**Link Duan**

  
**梁桂锋**

  
**qingbozhang**

  
**qianque7**

  
**Chen Ziqian**

  
**antony**

  
**ArthurQ**

  
**Jeff Li**

  
**Ather Shu**

  
**Jeremy**

  
**csy**

  
**zackzhangkai**

  
**kl**

Star History
------------

Thank You
---------

-   腾源会/WeOpen

Thank JetBrains for Open Source licenses support
------------------------------------------------

Friends
-------

-   DBM - An awesome database management tool specified for ClickHouse
