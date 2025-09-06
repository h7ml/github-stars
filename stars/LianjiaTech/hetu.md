---
project: hetu
stars: 807
description: 低代码平台, 可视化编辑器，单手打代码，解放你的双手
url: https://github.com/LianjiaTech/hetu
---

河图
==

河图, 是一个 `低代码` 平台, 通过可视化界面, 快速生成各种后台页面, 极大减少开发成本。

河图是贝壳找房内部孵化项目, 目前已在公司大多数业务线落地, 完成200+项目, 1500+页面。

✨ 特性
----

-   🚴‍♀️ 操作简单、功能强大的可视化编辑器
-   📦 开箱即用、高质量后台管理系统模版
-   ⚙️ 开发流程全部线上化，节省沟通、调试、运维成本
-   🛡 使用 React、TypeScript、nodejs、express 开发

🖥 兼容环境
-------

-   现代浏览器、IE11以上

🔗 链接
-----

-   项目文档
-   项目首页
-   服务器部署

🍼 准备
-----

### 1\. 一个邮箱账号

用于发送验证码, 需要 开启SMTP服务

### 2\. MySQL数据库

> 本项目使用mysql 5.7版本

-   方式1: 手动部署MySQL数据库
-   方式2: 购买MySQL云服务

### 3\. 初始化数据库

将 server/open\_hetu.sql 文件, 通过mysql Gui工具, 导入到数据库

### 4\. 创建配置文件

克隆项目, 在项目根目录下创建`system_config.ini`文件, 配置内容如下(将\*\*\*\*替换为自己的配置, 去掉注释内容)

\[server\]
port = 9536         // node服务启动端口

\[mysql\]             // mysql配置
host = \*\*\*\*
port = \*\*\*\*
user = \*\*\*\*
password = \*\*\*\*
database = \*\*\*\*

\[email\]
host = smtp.163.com // SMTP服务域名
port = 364          // 连接端口
user = \*\*\*\*         // 公共邮箱账号
pass = \*\*\*\*         // 授权密码

> 如果项目报`host port`未找到, 可尝试将配置写死在项目中

### 5\. 全局安装yarn

```
npm install -g yarn
```

🚀 开始
-----

### 第一步 启动组件库服务

```
# 进入plugin目录
cd ./plugin

# 安装依赖
yarn

# 打包输出esm模块
yarn run build:umd

# 启动组件库服务
yarn run server:dist
```

打开 http://127.0.0.1:8080/manifest.json 预览, 可以看到如下内容

{
  "files": {
    "index.js": "/0.0.6/hetu.umd.development.js",
    "index.min.js": "/0.0.6/hetu.umd.production.min.js",
    "index.css": "/0.0.6/index.css"
  },
  "entrypoints": \[
    "index.js",
    "index.css"
  \]
}

河图主应用, 会自动读取里面的内容, 并动态加载资源

### 第二步 安装依赖

安装client层依赖

cd ../client && yarn

安装server层依赖

cd ../server && yarn

### 第三步 启动服务

启动client层服务

cd ../client && yarn start

启动server层服务

cd ../server && yarn dev

打开 http://127.0.0.1:1234 预览, 可使用任意邮箱注册账号

🤝 版本记录
-------

CHANGELOG

🙋 问题咨询
-------

-   QQ群 【河图开源交流】 782899873

❤️ 主要贡献者
--------

Name

Avatar

Name

Avatar

Name

Avatar

Name

Avatar

Name

Avatar

好爸爸

嘻老师

姚泽源

liaoqixin

般若超

License
-------

MIT

Copyright(c) 2020 Lianjia, Inc. All Rights Reserved
