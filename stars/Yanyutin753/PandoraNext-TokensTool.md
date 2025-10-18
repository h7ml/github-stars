---
project: PandoraNext-TokensTool
stars: 1255
description: 【更方便更安全的管理PandoraNext】通过手机端和电脑端使小白能快速部署属于自己的免费Open API中转站。tokensTool支持通过PandoraNext管理刷新所有token，支持分享，支持share_token，pool_token一键自定义放入oneapi。tokensTool全面支持PandoraNext部署方法且支持热部署，自定义后缀，登录黑名单IP和登录日志，保护隐私安全，已打包好docker镜像，且有详细部署和使用文档，小白也能免费部署，一键启动！
url: https://github.com/Yanyutin753/PandoraNext-TokensTool
---

PandoraNext-TokensTool
======================

### PandoraNext-TokensTool 是一个基于 PandoraNext 中的便捷添加管理tokens.json和config.josn的工具，旨在更加简便地使用pandoraNext资源，手机端电脑端在线管理PandoraNext,使得可以方便地白嫖 chatGPT，本工具是站在巨人的肩膀上，方便大家，麻烦给个不要钱的星星⭐⭐⭐！

#### 不准白嫖，请给我免费的star⭐吧，十分感谢！

Important

1.  **保存账号信息：** 支持保存 OpenAI 账号密码和 token，方便快速访问。
    
2.  **自动添加删除修改token：** 工具能够自动在 tokens.josn 中添加删除刷新token，简化配置过程，并一键查看token用量。
    
3.  **自动刷新share\_token,access\_token,pool\_token**,tokensTool工具会自动通过openAI账号密码刷新tokens,重启PandoraNext，方便使用。
    
4.  **通过账号密码添加token**,该功能如今恢复正常 ，避免查找繁琐的token
    
5.  **一键暂停，启动,重启PandoraNext** ,使得修改token效率更高
    
6.  **支持在线修改config.json文件,重启PandoraNext生效**
    
7.  **支持热重载，需要在配置文件或者在网页上添加重载密码，开启服务**
    
8.  **新增脚本文件,真一键部署并更新PandoraNext和tokensTool双服务**
    
9.  **新增获取多个pool\_tokens，并支持批量删除修改**,方便使用
    
10.  **新增连接one-api，使得生成的share\_token，pool\_token能发送到one-api，实现同步自动更新**
    
11.  **新增登录日志，获取登陆的IP和地址，增加安全性**
    
12.  **新增自定义前缀，增加安全性**
    

✨点击查看文档站
--------

 ```
 旧的文档，请点击上面连接跳转新的文档站
```

* * *

使用方法
----

### 一键部署PandoraNext和tokensTool(最强推荐)

#### 将直接拉取最新版本的PandoraNext和tokensTool

```
# 安装git
(Ubuntu)
sudo apt update
sudo apt install git

（如Fedora、CentOS等）
sudo yum update
sudo yum install git

# 国内服务器
cd / && git clone https://gitee.com/yangyangEN/tokenTools-sh.git

# 国外服务器
cd / && git clone https://github.com/Yanyutin753/tokenTools-sh.git

# 运行脚本
cd /tokenTools-sh && sudo sh install.sh

# 一键更新pandoraNext和tokensTool服务
cd /tokenTools-sh && sudo sh update.sh

# 更新update.sh或者install.sh

# 国内
sudo rm -rf /tokenTools-sh && cd / && git clone https://gitee.com/yangyangEN/tokenTools-sh.git
# 国外
sudo rm -rf /tokenTools-sh && cd / && git clone https://github.com/Yanyutin753/tokenTools-sh.git
```

#### 1\. 开放8081和8181端口，先访问8081,然后填写系统变量，把127.0.0.1:8181改成0.0.0.0:8181

#### 2\. 在8081页面的系统变量里的tokentool设置更改账号密码，并填写license\_ip

_**注意是下面类似括号里的内容**_\*\*

```
curl -fLO "https://dash.pandoranext.com/data/ (uVlk_4ilqs23dfsdfdsfsdfOlgaPdNkgGDwesNmVHGoI_23) /license.jwt"
```

#### 3.设置相应的信息，点击重启PandoraNext，期间如遇打不开PandoraNext,请耐心等待一会，再重启PandoraNext即可（热重载需要在容器启动之后才能进行）

### 具体想要修改一键部署的端口可以在/pandora/docker-compose.yml里修改

* * *

非一键部署方式
-------

### **环境变量**

-   **启动端口号**：server.port=8081
    
-   **URL自定义后缀(选填)**：server.servlet.context-path=/tokensTool
    
    -   记住前面必须加上/，例如/tokensTool,/tool等
-   **PandoraNext的部署方式**：--deployWay=releases/docker
    
    -   **手动部署**\--deployWay=releases
    -   **docker和docker-compose部署** --deployWay=docker
-   **PandoraNext中存放config.json的位置**（docker部署在上面代码查到位置） --deployPosition
    
    -   如果你的tokensTool的jar包放在了config.json --deployPosition=default
    -   如果不在的话就填你config.json的文件目录 例如：--deployPosition=/www/wwwroot/PandoraNext/PandoraNext-v0.1.3-linux-386-51a5f88
-   ⭐记住路径没有/config.json
    
-   **是否开启热重载**： --hotReload=true
    
-   记得修改你的路径，密码，账号，端口号（选填），最最重要没有括号
    

#### 如果不知道docker里面容器config.json位置，可以参考以下代码

```
# 查找容器名为 "PandoraNext" 的所有挂载信息
docker inspect -f '{{range .Mounts}}{{.Destination}}: {{.Source}}{{"\n"}}{{end}}' PandoraNext
# 拿到:后面的地址
```

### java部署详情

```
# 先拿到管理员权限
sudo su -
# 提示你输入密码进行确认。输入密码并按照提示完成验证。
```

```
# 安装 OpenJDK 11：
sudo apt install openjdk-11-jdk
# 安装完成后，可以通过运行以下命令来验证 JDK 安装：
java -version
```

```
# 填写下面路径
cd （你的jar包的位置）
```

##### 运行程序

```
# 例如
nohup java -jar pandoraNext-0.0.1-SNAPSHOT.jar --server.port=8081 --deployWay=releases --deployPosition=default --pandoara_Ip=127.0.0.1 > myput.log 2>&1 &

# 等待一会 放行8081端口即可运行（自行调整）
```

docker部署详情
----------

```
# 先拉取镜像
docker pull yangclivia/tokenstool:latest
```

#### 手动部署PandoraNext启动命令

```
docker run -d \
  --restart=always \
  -u root \
  --name tokensTool \
  --net=host \
  --pid=host \
  --privileged=true \
  -v （你config.json的文件目录）:/data \
  yangclivia/tokenstool:latest \
  --deployWay=releases \
  --deployPosition=/data \
  --hotReload=true \
  --server.port=8081 \
  --server.servlet.context-path=/tokensTool \
```

#### Docker部署PandoraNext启动命令

```
docker run -d \
  --restart=always \
  -u root \
  --name tokensTool \
  --net=host \
  --pid=host \
  --privileged=true \
  -v （你config.json的文件目录）:/data \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v /usr/bin/docker:/usr/bin/docker \
  yangclivia/tokenstool:latest \
  --deployWay=docker \
  --deployPosition=/data \
  --hotReload=true \
  --server.port=8081 \
  --server.servlet.context-path=/tokensTool \
```

### Docker Compose部署详情

代码模板
----

```
version: '3'
services:
  tokensTool:
    image: yangclivia/tokenstool:latest
    container_name: tokensTool
    restart: always
    user: root
    network_mode: host
    pid: host
    privileged: true
    volumes:
      - （你config.json的文件目录）:/data
      - /var/run/docker.sock:/var/run/docker.sock
      - /usr/bin/docker:/usr/bin/docker
    command: 
      - --deployWay=(部署方式看环境变量)
      - --deployPosition=/data
      - --hotReload=true
      - --server.port=8081
      - --server.servlet.context-path=/tokensTool
```

##### 启动tokensTool

```

cd (你的docker-compose.yml位置)

docker-compose up -d
```

##### 更新tokensTool项目代码

```
cd (你的docker-compose.yml位置)

docker-compose pull

docker-compose up -d
```

注意事项
----

1.  pandora容器端口跟映射端口一致能减少麻烦，bind端口要跟容器端口一致
2.  不做反代的话，路由端口也要跟反射端一致，做的话就在tools proxy url地址里面写上http(s)://(ip:port或者域名)/后缀名
3.  默认API调用接口：http(s)://(ip:port或者域名)/后缀名/v1/chat/completions

### 初次启动，请根据提示完成填写，并之后重启pandoraNext服务

### 想要二开项目的友友们，可以自行遵循相应的开源规则更改前后端项目，本人小白，项目写的不太好，还请谅解！

接口
--

1.  /shared\_token
    
    -   请求方式为get
    -   示例网址：http://ip:8081/shared\_token?password=123456
    -   返回
    
    ```
     {
    "code": 1,
    "msg": "success",
    "data": [
              "fk-Yasdasdasdasdasdasd",
              "fk-ssadasdd asdasdasdasM"
          ]
      }
    ```
    

2./token/shared\_token

-   请求方式为get
-   示例网址：http://ip:8081/token/shared\_token?password=123456&tokenName=tokenstool
-   返回

```
{
"code": 1,
"msg": "success",
"data": "fk-I2hsq9weY_NnBm0Fgcsadsasdasdasg9_OFwn7A"
}
```

3 /access\_token

-   请求方式为get
-   示例网址：http://ip:8081/access\_token?password=123456
-   返回

```
{
"code": 1,
"msg": "success",
"data": [
      "access_token_1",
      "access_token_2"
  ]
}
```

4 /token/access\_token

-   请求方式为get
-   示例网址：http://ip:8081/token/access\_token?password=123456&tokenName=tokenstool
-   返回

```
{
"code": 1,
"msg": "success",
"data": "access_token"
}
```

5 /token/pool\_token

-   请求方式为get
-   示例网址：http://ip:8081/pool\_token?password=123456&tokenName=tokenstool
-   返回
    
    ```
     {
         "code": 1,
         "msg": "success",
         "data": "pk-L25JirYw2mWiyRqasdasdSCYrnovbHkmXIA7jDUs-Zpug"
     }
    ```

Caution

-   **本项目是站在巨人的肩膀上的，感谢Pandora超级无敌始皇!，欢迎各位来帮助修改本项目，使得本项目变得更方便，更简单！**
    
-   **kwxos提供不用单独VPS也能免费部署TokensTool和PandoraNext的服务的脚本，大家可以试试并给⭐支持他吧！**
    
-   **有群佬写了一个自动刷新token的脚本，大家也可以试试！**
    
-   **初始用户名：root 初始密码值:123456 (请务必在第一次登录之后修改)**
    
-   **现如今只支持账号密码登录，希望大佬能扩充！**
    

### 新增群聊，点了⭐️可以进群讨论部署，我把你们拉进群，无广，广子踢掉

### 请给我一个免费的⭐吧！！！

Star History
------------
