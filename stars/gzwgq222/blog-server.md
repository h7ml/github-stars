---
project: blog-server
stars: 35
description: :balloon: koa2 + mysql + sequelize 构建 web 服务
url: https://github.com/gzwgq222/blog-server
---

博客 node server
--------------

koa-generator 构建项目

koa + koa-router + mysql2 + sequelize

```
 "scripts": {
    "start": "node bin/www",
    "dev": "./node_modules/.bin/nodemon bin/www",
    "prd": "pm2 start bin/www",
    "test": "echo \"Error: no test specified\" && exit 1"
  }
```

从 package.json 可以看出 dev 命令当项目文件有变化的时候会自动编译，start 则需要每次手动重启

运行

```
yarn dev

localhost:3000
```

### 实现功能

-   登录
-   分页
-   查询
-   标签列表
-   分类列表
-   收藏列表
-   文章列表
-   发布文章时间轴
-   文章访问次数统计
-   后台适配移动端
-   后台对访问文章次数进行可视化
-   评论功能

### Logs

时间

事件

2019/03/30

开发完毕 部署上线

### Links

-   koa
-   sequelizejs 英文
-   sequelizejs 中文
-   sequelize-docs-Zh-CN

初尝 koa+mysql，错误之处还望斧正

喜欢或对你有帮助，欢迎右上角 star
