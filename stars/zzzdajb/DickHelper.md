---
project: DickHelper
stars: 640
description: A simple and easy-to-use masturbation management tool
url: https://github.com/zzzdajb/DickHelper
---

牛子小助手 (DickHelper)
==================

一个简单、高效、易用的打飞机记录工具，帮助你科学管理✈️生活。

QQ交流群：745297798 （该群为作者个人的群，作者偶尔会写些奇奇怪怪的东西）

### 项目重构中 | Rewriting

鉴于作者大量使用AI完成代码，导致以目前群主的水平，已经无力继续维护该项目，DickHelper（牛子小助手）项目将正式结束维护，代码将不再更新。我知道你很急，但是请你先别急，群主将基于Avalonia构建一个和现有DickHelper一模一样的程序，并且目标是支持全平台，提供客户端。

此致，敬礼，还请使用我Demo的各位提前备份数据。

在线演示 | Online Demo
------------------

🔗 演示demo：牛子小助手Demo

⚠️ 注意事项：

-   这只是一个演示站点，不保证长期可用性和数据持久性
-   数据存储是基于域名的，即不同域名下的数据是相互独立的
-   建议自行部署使用，以确保可用性

特点 | Features
-------------

-   🔒 **数据安全**: 所有数据完全存储在本地，无需担心隐私泄露
    
-   📊 **数据可视化**: 直观的图表展示统计信息
    
-   📱 **响应式设计**: 支持各种设备尺寸
    
-   🌐 **无需后端**: 纯前端应用，无需服务器
    

本地部署 | Local Deployment
-----------------------

如果你想在本地运行此项目，请按照以下步骤操作：

If you want to run this project locally, follow these steps:

# 克隆项目 | Clone the repository
git clone https://github.com/zzzdajb/DickHelper.git

# 进入项目目录 | Enter the project directory
cd GoodDick

# 安装依赖 | Install dependencies
npm install

# 启动开发服务器 | Start development server
npm run dev

云端部署 | Cloud Deployment
-----------------------

本项目是纯前端应用，可以轻松部署到各种静态网站托管平台。

### Vercel

1.  在 GitHub上Fork本仓库
    
2.  登录 Vercel
    
3.  点击 "New Project" 并导入你的 GitHub 仓库
    
4.  保持默认配置即可，Vercel 会自动检测 Vite 项目
    
5.  点击 "Deploy"
    

部署完成后，Vercel会提供一个可访问的URL。中国大陆地区污染了Vercel的默认域名，你可以通过绑定自己的域名来解决这个问题。

### Cloudflare Pages 参考文档

1.  在 GitHub上Fork本仓库
    
2.  登录 Cloudflare
    
3.  在"Workers & Pages" 中点击 "Create" , 类型选择 "Pages" 并导入你的 GitHub 仓库
    
4.  在"Framework preset" 中选择 "React(Vite)"
    
5.  点击 "Deploy"
    

部署完成后，Cloudflare Pages 会提供一个可访问的URL。中国大陆地区污染了 Cloudflare Pages 的默认域名，你可以通过绑定自己的域名来解决这个问题。

Docker 部署 | Docker Deployment
-----------------------------

### 使用预构建镜像 | Using Pre-built Image

我们提供了预构建的Docker镜像，您可以直接拉取使用：

# 拉取最新镜像 | Pull the latest image
docker pull ghcr.io/zzzdajb/dickhelper:latest

# 运行容器 | Run container
docker run -d -p 80:80 --name dick-helper ghcr.io/zzzdajb/dickhelper:latest

### 自行构建镜像 | Build Your Own Image

如果您想自行构建Docker镜像，可以按照以下步骤操作：

# 构建镜像 | Build image
docker build -t dick-helper .

# 运行容器 | Run container
docker run -d -p 80:80 --name dick-helper dick-helper

技术栈 | Tech Stack
----------------

-   React 19.0.0
-   TypeScript 5.7.2
-   Vite 6.1.0
-   Material-UI 6.4.5
-   Chart.js 4.4.7

隐私说明 | Privacy Statement
------------------------

本项目基于纯前端技术构建，默认情况下，所有的数据会根据域名保存在您的浏览器当中，未经您允许，我们不会收集并使用您的任何信息。在后续开发当中，可能会有部分功能需要联网并且上传数据，在此之前，我们会征得您的同意，如果您拒绝上传数据，您将无法访问少数功能，但这不会对您正常使用程序造成任何影响。

项目维护说明 | Maintenance Statement
------------------------------

⚠️ 请注意：本项目由AI工具Trae编写，原作者可能没有持续维护的能力。欢迎社区贡献者参与改进。

许可证 | License
-------------

GPL-3.0（GNU General Public License v3.0）

NodeSupport赞助了本项目

Star History
------------
