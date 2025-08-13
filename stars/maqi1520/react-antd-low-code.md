---
project: react-antd-low-code
stars: 206
description: 简易版 react 低代码平台
url: https://github.com/maqi1520/react-antd-low-code
---

react-antd-low-code
-------------------

-   **Framework**: Next.js
-   **Database**: PlanetScale
-   **ORM**: Prisma
-   **Authentication**: NextAuth.js
-   **Deployment**: Vercel
-   **UI**: Ant Design
-   **Styling**: Tailwind CSS

开发
--

安装 docker-compose

docker-compose up
docker-compose up -d  // 后台启动并运行容器

同步数据表
-----

npx prisma db push

启动开发

yarn install
yarn dev

运行
--

yarn build
yarn start

环境变量
----

复制 `.env.example` 为 `.env` 文件，并修改相关配置

部署
--
