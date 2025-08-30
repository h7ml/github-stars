---
project: tgmeng-api
stars: 144
description: 糖果梦热搜-后端
url: https://github.com/tgmeng-com/tgmeng-api
---

糖果梦 热榜（后端） | Tgmeng Trend

           

* * *


-------------------------------------------------

🏩 项目主页：https://trend.tgmeng.com
--------------------------------

-   #### 本站前后端均已100%全面开源，欢迎大家Star，Fork，PR，Issues。  
    
-   #### 这里是后端，👉前端项目源码请点击前往👈
    

* * *

👁️ 预览
------

* * *

📖 简介
-----

糖果梦热榜是一个实时更新的热门清单，汇集了最新的资讯，涵盖新闻、社交、媒体、GitHub等多个领域。只需打开页面，即可轻松浏览各大热门内容，时刻跟进行业动态，掌握最热话题。

* * *

🌍 时效性
------

-   网站数据每分钟更新一次，（GitHub相关数据每20-40分钟更新一次）
-   所有接口均来自官方，无任何第三方中转，主打无情铁手，AA接W接A接无情铁手接外圈刮接一刀斩

* * *

✨ 已支持功能
-------

-   ✅ 支持开启代理访问第三方
    -   ✅ 配置代理池
    -   ✅ 代理池可选部分开启
    -   ✅ 从开启的代理池中随机选择
    -   ✅ HTTPS和SOCKS代理都支持
-   ✅ 支持内存缓存
    -   ✅ 使用Caffeine进行内存缓存
    -   ✅ 可选是否开启缓存(不开启就每次都走接口)
    -   ✅ 配置最大缓存条数
    -   ✅ 配置全局缓存过期时间
    -   ✅ 配置单独特殊数据独立缓存过期时间
    -   ✅ 配置单独特殊缓存数据随机浮动过期时间范围
-   ✅ 定时器自动更新缓存
    -   ✅ 可选是否开启自动定时更新缓存
    -   ✅ 配置定时自动缓存执行频率
    -   ✅ 配置定时自动缓存具体开启接口
-   ✅ 异常处理
    -   ✅ 全局异常拦截处理
    -   ✅ 自定义异常支持
-   ✅ 请求头自动模拟
-   ✅ 全局返回结果封装
-   ✅ 全局日志处理
-   ✅ 跨域配置
-   ✅ GitHub Action 自动部署
    -   ✅ 提交代码即自动部署项目到指定服务器
    -   ✅ 提交新Tag即可自动发布Realease
    -   ✅ 提交新代码即可自动发布到Docker镜像到DockerHub
    -   ✅ 提交新代码即可自动发布到Docker镜像到GHCR(github container registry)

* * *

🗼 部署
-----

### 1 GitHub Action 一键部署

-   修改 .github/workflows/deploy.yml 中的下列值，
    
-   如果你不需要把自动打镜像到dockerhub，把里面dockerhub相关的代码注释/删掉即可（文件里搜DockerHub就行）。
    
-   你的代码推送到github仓库后，就会自动触发action，自动部署本项目
    

SERVER\_HOST      # 你的服务器IP
SERVER\_USER      # 你的服务器用户名
SERVER\_PASSWORD  # 你的服务器密码
SERVER\_PORT      # 你的服务器端口
REMOTE\_JAR\_DIR   # 你的要部署的目录

### 2 Docker镜像一键部署

docker pull tgmeng/tgmeng-api:latest                     # 这是dockerhub里的镜像
# docker pull ghcr.io/tgmeng-com/tgmeng-api:latest       # 这是ghcr里的镜像，和上面是一样的，拉哪个都行
docker run -d -p 8080:4399 --name tgmeng-api tgmeng/tgmeng-api:latest
docker ps
docker logs -f --tail=50 tgmeng-api

### 3 DockerCompose一键部署

-   下载本项目根目录下的docker-compose.yml，然后在他的同级目录执行下面命令

docker-compose up -d
docker-compose ps
docker-compose logs -f --tail=50 tgmeng-api

⚖️ 免责声明
-------

-   软件性质：本项目为开源软件，按 “现状” 提供，不保证功能、性能或兼容性。
-   风险承担：使用风险由用户自行承担，开发者不提供任何明示或暗示担保（如适销性、特定用途适用性等）。
-   责任限制：因使用本软件导致的直接 / 间接损失（包括数据丢失、业务中断等），开发者不承担责任。
-   合规义务：二次开发或使用需遵守法律法规，相关责任由使用者自行承担。
-   侵权处理：如发现本项目存在侵权内容，请联系开发者，将及时处理。
-   条款变更：开发者有权修改免责声明及软件功能，持续使用即视为接受更新。

* * *

❤️ 联系我
------

           

* * *

💐 致谢
-----

-   #### LINUX DO 感谢L站的各位大佬们的耐心指导与帮助，受益匪浅，感激之情难以言表
    

* * *

🌎 许可证
------

-   本项目采用 GNU GENERAL PUBLIC LICENSE Version 3 许可证 授权。
-   

* * *

🧧 投喂
-----

* * *

⭐ Star History
--------------
