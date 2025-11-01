---
project: SPlayer
stars: 5456
description: 🎉 一个简约的音乐播放器，支持逐字歌词，下载歌曲，展示评论区，音乐云盘及歌单管理，音乐频谱，移动端基础适配 | 网易云音乐 | A minimalist music player
url: https://github.com/imsyy/SPlayer
---

SPlayer
=======

> A simple music player

说明
--

Important

### 严肃警告

-   请务必遵守 GNU Affero General Public License (AGPL-3.0) 许可协议
-   在您的修改、演绎、分发或派生项目中，必须同样采用 **AGPL-3.0** 许可协议，**并在适当的位置包含本项目的许可和版权信息**
-   **禁止用于售卖或其他盈利用途**，如若发现，作者保留追究法律责任的权利
-   禁止在二开项目中修改程序原版权信息（ 您可以添加二开作者信息 ）
-   感谢您的尊重与理解

-   本项目采用 Vue 3 + TypeScript + Naïve UI + Electron 开发
    
-   支持网页端与客户端，由于设备有限，目前仅适配 `Win`，其他平台可自行解决兼容性后进行构建
    
-   仅对移动端做了基础适配，**不保证功能全部可用**
    
    > 请注意，本程序不打算开发移动端，也不会对移动端进行完美适配，仅保证基础可用性
    
-   欢迎各位大佬 `Star` 😍
    

👀 Demo
-------

-   SPlayer

🎉 功能
-----

-   ✨ 支持扫码登录
-   📱 支持手机号登录
-   📅 自动进行每日签到及云贝签到
-   💻 支持桌面歌词
-   💻 支持切换为本地播放器，此模式将不会连接网络
-   🎨 封面主题色自适应，支持全站着色
-   🌚 Light / Dark / Auto 模式自动切换
-   📁 本地歌曲管理及分类（建议先使用 音乐标签 进行匹配后再使用）
-   📁 简易的本地音乐标签编辑及封面修改
-   🎵 **支持播放部分无版权歌曲（可能会与原曲不匹配，客户端独占功能）**
-   ⬇️ 下载歌曲（ 最高支持 Hi-Res，需具有相应会员账号 ）
-   ➕ 新建歌单及歌单编辑
-   ❤️ 收藏 / 取消收藏歌单或歌手
-   🎶 每日推荐歌曲
-   📻 私人 FM
-   ☁️ 云盘音乐上传
-   📂 云盘内歌曲播放
-   🔄 云盘内歌曲纠正
-   🗑️ 云盘歌曲删除
-   📝 支持逐字歌词
-   🔄 歌词滚动以及歌词翻译
-   📹 MV 与视频播放
-   🎶 音乐频谱显示
-   ⏭️ 音乐渐入渐出
-   🔄 支持 PWA
-   💬 支持评论区
-   📱 移动端基础适配
-   🌐 `i18n` 支持

🖼️ screenshots
---------------

> 开发中，仅供参考

主页面

播放页面

发现页面

歌单页面

评论页面

本地音乐

📦️ 获取
------

### 稳定版

通常情况下，可以在 Releases 中获取稳定版

### 开发版

可以通过 `GitHub Actions` 工作流获取最新的开发版，目前开发版仅提供 `Win` 版本

Dev Workflow

Snap Store
----------

⚙️ Docker 部署
------------

> 安装及配置 `Docker` 将不在此处说明，请自行解决

### 本地构建

> 请尽量拉取最新分支后使用本地构建方式，在线部署的仓库可能更新不及时

# 构建
docker build -t splayer .

# 运行
docker run -d --name SPlayer -p 25884:25884 splayer
# 或使用 Docker Compose
docker-compose up -d

### 在线部署

# 从 Docker Hub 拉取
docker pull imsyy/splayer:latest
# 从 GitHub ghcr 拉取
docker pull ghcr.io/imsyy/splayer:latest

# 运行
docker run -d --name SPlayer -p 25884:25884 imsyy/splayer:latest

以上步骤成功后，将会在本地 localhost:25884 启动，如需更换端口，请自行修改命令行中的端口号

⚙️ Vercel 部署
------------

> 其他部署平台大致相同，在此不做说明

1.  本程序依赖 NeteaseCloudMusicApi 运行，请确保您已成功部署该项目，并成功取得在线访问地址
    
2.  点击本仓库右上角的 `Fork`，复制本仓库到你的 `GitHub` 账号
    
3.  复制 `/.env.example` 文件并重命名为 `/.env`
    
4.  将 `.env` 文件中的 `VITE_API_URL` 改为第一步得到的 API 地址
    
    VITE\_API\_URL \= "https://example.com";
    
5.  将 `Build and Output Settings` 中的 `Output Directory` 改为 `out/renderer`
    
6.  点击 `Deploy`，即可成功部署
    

⚙️ 服务器部署
--------

1.  重复 `⚙️ Vercel 部署` 中的 1 - 4 步骤
    
2.  克隆仓库
    
    git clone https://github.com/imsyy/SPlayer.git
    
3.  安装依赖
    
    pnpm install
    # 或
    yarn install
    # 或
    npm install
    
4.  编译打包
    
    pnpm build
    # 或
    yarn build
    # 或
    npm build
    
5.  将站点运行目录设置为 `out/renderer` 目录
    

⚙️ 本地部署
-------

1.  本地部署需要用到 `Node.js`。可前往 Node.js 官网 下载安装包，请下载最新稳定版
    
2.  安装 pnpm
    
    npm install pnpm -g
    
3.  克隆仓库并拉取至本地，此处不再赘述
    
4.  使用 `pnpm install` 安装项目依赖（若安装过程中遇到网络错误，请使用国内镜像源替代，此处不再赘述）
    
5.  复制 `/.env.example` 文件并重命名为 `/.env` 并修改配置
    
6.  打包客户端，请依据你的系统类型来选择，打包成功后，会输出安装包或可执行文件在 `/dist` 目录中，可自行安装
    
    命令
    
    系统类型
    
    `pnpm build:win`
    
    Windows
    
    `pnpm build:linux`
    
    Linux
    
    `pnpm build:mac`
    
    MacOS
    

😘 鸣谢
-----

特此感谢为本项目提供支持与灵感的项目

-   NeteaseCloudMusicApi
-   YesPlayMusic
-   UnblockNeteaseMusic
-   applemusic-like-lyrics
-   Vue-mmPlayer
-   refined-now-playing-netease
-   material-color-utilities

📢 免责声明
-------

本项目部分功能使用了网易云音乐的第三方 API 服务，**仅供个人学习研究使用，禁止用于商业及非法用途**

同时，本项目开发者承诺 **严格遵守相关法律法规和网易云音乐 API 使用协议，不会利用本项目进行任何违法活动。** 如因使用本项目而引起的任何纠纷或责任，均由使用者自行承担。**本项目开发者不承担任何因使用本项目而导致的任何直接或间接责任，并保留追究使用者违法行为的权利**

请使用者在使用本项目时遵守相关法律法规，**不要将本项目用于任何商业及非法用途。如有违反，一切后果由使用者自负。** 同时，使用者应该自行承担因使用本项目而带来的风险和责任。本项目开发者不对本项目所提供的服务和内容做出任何保证

感谢您的理解

📜 开源许可
-------

-   **本项目仅供个人学习研究使用，禁止用于商业及非法用途**
-   本项目基于 GNU Affero General Public License (AGPL-3.0) 许可进行开源
    1.  **修改和分发：** 任何对本项目的修改和分发都必须基于 AGPL-3.0 进行，源代码必须一并提供
    2.  **派生作品：** 任何派生作品必须同样采用 AGPL-3.0，并在适当的地方注明原始项目的许可证
    3.  **注明原作者：** 在任何修改、派生作品或其他分发中，必须在适当的位置明确注明原作者及其贡献
    4.  **免责声明：** 根据 AGPL-3.0，本项目不提供任何明示或暗示的担保。请详细阅读 GNU Affero General Public License (AGPL-3.0) 以了解完整的免责声明内容
    5.  **社区参与：** 欢迎社区的参与和贡献，我们鼓励开发者一同改进和维护本项目
    6.  **许可证链接：** 请阅读 GNU Affero General Public License (AGPL-3.0) 了解更多详情

⭐ Star History
--------------
