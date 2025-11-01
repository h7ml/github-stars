---
project: fish-island-backend
stars: 661
description: 摸鱼岛🎣后端 基于爬虫 ➕ Netty ➕ SpringBoot ➕Redis➕ MySQL 开源🌟一站式摸鱼网
url: https://github.com/lhccong/fish-island-backend
---

**中文** | English

摸鱼岛
===

_✨ 开源🌟一站式摸鱼网 ✨_

部署教程 · 目前现状 · 意见反馈 · 截图展示 · 在线演示 · 开源与贡献 · 相关项目 · 赞赏支持

Note

本项目为开源项目，使用者必须在网站标注作者名称以及指向本项目的链接。如果不想保留署名，必须首先获得授权。不得用于非法用途。

Note

在线体验地址🔗

最新版（域名 2025.09 过期）：https://fish.codebug.icu/ 稳定版：https://yucoder.cn/

后端地址🌈：https://github.com/lhccong/fish-island-backend

前端地址🏖️：https://github.com/lhccong/fish-island-frontend

Warning

私部署时记得修改后端接口地址路径指向。

功能
--

1.  支持多种数据源聚合：
    -   \[✅\] 知乎热榜
    -   \[✅\] 微博热榜
    -   \[✅\] 虎扑步行街热榜
    -   \[✅\] 编程导航热榜
    -   \[✅\] CSDN 热榜
    -   \[✅\] 掘金热榜
    -   \[✅\] B 站热门
    -   \[✅\] 抖音热搜
    -   \[✅\] 网易云热歌榜（支持网站点击播放）
    -   \[✅\] 什么值得买热榜
    -   \[✅\] 待补充...
2.  每日待办功能。
3.  摸鱼聊天室：
    -   \[✅\] 发送 emoji 表情包
    -   \[✅\] 发送搜狗在线表情包
    -   \[✅\] 支持网站链接解析
    -   \[✅\] 支持 markdown 文本解析
    -   \[✅\] 支持 AI 助手回答（接入硅基流动模型）
    -   \[✅\] 头像框功能
    -   \[✅\] 用户地理位置显示功能
    -   \[✅\] 用户称号功能
    -   \[✅\] 五子棋、象棋对战邀请功能
    -   \[✅\] 积分红包🧧发送功能
    -   \[✅\] 支持用户 CV 发送图片功能
4.  摸鱼阅读：
    -   \[✅\] 在线搜书功能
    -   \[✅\] 小窗口观看功能
    -   \[✅\] 支持自定义书源
5.  小游戏：
    -   \[✅\] 五子棋（人机/在线对战）
    -   \[✅\] 象棋（人机/在线对战）
    -   \[✅\] 2048
6.  工具箱：
    -   \[✅\] JSON 格式化
    -   \[✅\] 文本比对
    -   \[✅\] 聚合翻译
    -   \[✅\] Git 提交格式生成
    -   \[✅\] AI 智能体
    -   \[✅\] AI 周报助手
7.  头像框兑换功能。
8.  其他：
    -   \[✅\] 音乐播放器
    -   \[✅\] 下班薪资计算器（放假倒计时）
    -   \[✅\] 修改网站图标
    -   \[✅\] 网站标题闪烁消息提醒
    -   \[✅\] 摸鱼初始页

Star History
------------

截图展示
----

### 信息聚合

### 每日待办

### 摸鱼室

### 摸鱼阅读

### 小游戏

-   五子棋

-   象棋

-   2048

### 工具箱

-   JSON 格式化工具

-   文本比对

### 头像框兑换

目前现状
----

-   各大公众号转发。
    
-   用户突破 1k 的个人网站。
    
-   最高峰实时在线人数达 80 +。
    

部署教程
----

### 后端

-   执行初始化 SQL create\_table.sql
    
-   更改 MySQL 地址、Redis 地址、Minio 地址、邮箱发送配置
    
-   Maven 打包
    
-   docker 部署
    
-   dockerfile 文件
    
    FROM openjdk:8
    ENV workdir=/cong/fish
    COPY . ${workdir}
    WORKDIR ${workdir}
    EXPOSE 8123
    CMD \["java","-jar","-Duser.timezone=GMT+08","fish-island-backend-0.0.1-SNAPSHOT.jar"\]
    
-   打包命令
    
    docker build -f ./dockerfile -t fish .
    
    启动命令：docker run -d -e TZ=CST -p 8123:8123 -p 8090:8090 --name "fish" fish:latest
    
-   nginx 配置
    
    server {
        listen       80;
        listen  \[::\]:80;
        server\_name  moyuapi.codebug.icu;
    
        rewrite ^(.\*) https://$server\_name$1 permanent;
    }
    
    server {
        listen       443 ssl;
        server\_name  moyuapi.codebug.icu;
    
        ssl\_certificate      /etc/nginx/ssl/cert.pem;
        ssl\_certificate\_key  /etc/nginx/ssl/key.pem;
        ssl\_session\_cache    shared:SSL:1m;
        ssl\_session\_timeout  5m;
    
        ssl\_ciphers  HIGH:!aNULL:!MD5;
        ssl\_prefer\_server\_ciphers  on;
    
        location / {
             root /usr/share/nginx/fish;
             index index.html;
    					try\_files $uri $uri/ /index.html;
        }
    
       location /fish/ {
             proxy\_pass http://fish:8123/;    
        }
    
    \# WebSocket代理配置，处理 wss:// 请求
        location /ws/ {
            proxy\_pass http://fish:8090/;  # 后端 WebSocket 服务地址
            proxy\_http\_version 1.1;  # 使用 HTTP/1.1 协议，WebSocket 需要这个版本
            proxy\_set\_header Upgrade $http\_upgrade;  # 必须设置这些头来支持 WebSocket 协议的升级
            proxy\_set\_header Connection 'upgrade';  # 维持 WebSocket 连接
            proxy\_set\_header Host $host;  # 确保 Host 头部传递正确
            proxy\_cache\_bypass $http\_upgrade;  # 禁用缓存
        }
    
    location /sogou-api/ {
            proxy\_pass https://pic.sogou.com/;
            proxy\_set\_header Host pic.sogou.com;
            proxy\_set\_header X-Real-IP $remote\_addr;
            proxy\_set\_header X-Forwarded-For $proxy\_add\_x\_forwarded\_for;
            proxy\_ssl\_server\_name on;
    
            # 解决 CORS 问题
            add\_header Access-Control-Allow-Origin \*;
            add\_header Access-Control-Allow-Methods "GET, POST, OPTIONS";
            add\_header Access-Control-Allow-Headers "DNT,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type,Range";
            add\_header Access-Control-Expose-Headers "Content-Length,Content-Range";
    
            # 处理 OPTIONS 预检请求
            if ($request\_method = OPTIONS) {
                return 204;
            }
        }
    
    location /holiday/ {
        proxy\_pass https://date.appworlds.cn/;
        
        # 保持目标 API 的 Host，避免返回默认网页
        proxy\_set\_header Host date.appworlds.cn;
    
        # 伪装成浏览器，防止服务器根据 User-Agent 返回 HTML
        proxy\_set\_header User-Agent "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36";
    
        # 强制服务器返回 JSON，而不是 HTML
        proxy\_set\_header Accept "application/json";
    
        # CORS 允许跨域
        add\_header Access-Control-Allow-Origin \*;
        add\_header Access-Control-Allow-Methods "GET, POST, OPTIONS";
        add\_header Access-Control-Allow-Headers "DNT,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type,Range";
        add\_header Access-Control-Expose-Headers "Content-Length,Content-Range";
    
        # 处理 OPTIONS 预检请求
        if ($request\_method = OPTIONS) {
            return 204;
        }
    }
    
    location /img-api/ {
            proxy\_pass https://i.111666.best/;
            proxy\_set\_header Host pic.sogou.com;
            proxy\_set\_header X-Real-IP $remote\_addr;
            proxy\_set\_header X-Forwarded-For $proxy\_add\_x\_forwarded\_for;
            proxy\_ssl\_server\_name on;
    
            # 解决 CORS 问题
            add\_header Access-Control-Allow-Origin \*;
            add\_header Access-Control-Allow-Methods "GET, POST, OPTIONS";
            add\_header Access-Control-Allow-Headers "DNT,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type,Range";
            add\_header Access-Control-Expose-Headers "Content-Length,Content-Range";
    
            # 处理 OPTIONS 预检请求
            if ($request\_method = OPTIONS) {
                return 204;
            }
        }
    
        error\_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   /usr/share/nginx/html;
        }
    }
    

### 前端

-   修改 src/constants/index.ts 的接口地址。
-   max build --打包命令。
-   部署 dist 文件。

开源与贡献
-----

### 项目支持者 🔥

### 前端贡献者 🌟

### 后端贡献者 🌟:

### 📌 贡献方式

如果你也有希望聚合的数据源不妨来参加一下贡献，将你的数据源爬取出来放入其中。

1️⃣ 页面元素抓取

📌 **适用于**：目标网站未提供 API，数据嵌入在 HTML 结构中。

✅ 贡献要求

-   **推荐使用**：
    -   `Jsoup`（Java）
    -   `BeautifulSoup`（Python）
    -   `Cheerio`（Node.js）
-   **选择器精准**：避免因页面结构变化导致抓取失败。
-   **减少 HTTP 请求**：优化抓取效率，避免重复请求。
-   **遵守网站爬取规则**（`robots.txt` ）。

💡 示例代码

Document doc = Jsoup.connect("https://example.com").get();
String title = doc.select("h1.article-title").text();

2️⃣ 页面接口返回数据抓取

📌 **适用于**：目标网站提供 API，可直接调用接口获取 JSON/XML 数据。

✅ 贡献要求

-   **推荐使用**：
    -   `HttpClient`（Java）
    -   `axios`（Node.js）
    -   `requests`（Python）
-   **分析 API 请求**：确保请求参数完整（`headers`、`cookies`、`token`）。
-   **减少不必要的请求**：优化调用频率，避免触发反爬机制。
-   **异常处理**：确保代码稳定运行。

💡 示例代码

String apiUrl = "https://api.example.com/data";
String response = HttpRequest.get(apiUrl).execute().body();
JSONObject json = JSON.parseObject(response);

* * *

### 🔗 数据源注册

数据抓取完成后，需要注册数据源，以便系统能够正确使用。

🚀 注册流程

1.  **添加数据源 Key**： `/src/main/java/com/cong/fishisland/model/enums/HotDataKeyEnum.java` 定义新的数据源 Key。
    
2.  **更新数据源映射**：
    
    -   `/src/main/java/com/lhccong/fish/backend/config/DatabaseConfig.java` 文件中，添加新的数据源配置。
3.  **创建数据源类**：
    
    -   `src/main/java/com/cong/fishisland/datasource` 目录下，新建数据源类，继承 `DataSource`，实现 `getHotPost` 方法。
4.  **实现数据获取逻辑**：
    
    -   按照 `HotPostDataVO` 格式返回数据。
    -   使用 `@Builder` 注解，确保数据能正确解析。

💡 示例代码

HotPostDataVO.builder()
            .title(title)
            .url(url)
            .followerCount(followerCount)
            .excerpt(excerpt)
            .build();

* * *

### 🚀 贡献流程

1.  **Fork 仓库** ➜ 点击 GitHub 右上角 `Fork` 按钮。
2.  **创建分支** ➜ 推荐使用有意义的分支名，如 `feature/data-scraper-optimization`。
3.  **提交代码** ➜ 确保代码可读性高，符合规范。
4.  **提交 Pull Request（PR）** ➜ 详细描述您的更改内容，并关联相关 issue（如有）。
5.  **等待审核** ➜ 维护者会进行代码审核并合并。

以上讲解如果对你有帮助，不妨给我的项目点个小小的 star 🌟，成为一下我的精神股东呢

### 🎉 感谢您的贡献！

您的每一份贡献都让 **fish-island** 变得更好！💪
