---
project: owl-admin
stars: 576
description: 🎈 Owl Admin : 基于 laravel 和 amis 开发的后台框架, 友好的组件使用体验, 可轻松实现复杂页面, 内置代码生成器, 让开发者快速搭建后台管理系统
url: https://github.com/slowlyo/owl-admin
---

  

Owl Admin
=========

#### 快速且灵活的后台框架

官网 | Demo | Github | Gitee | 文档 (备用文档) | 加群

     

  

  

### 项目介绍

基于 `Laravel` 、 `amis` 开发的后台框架, 快速且灵活~

-   基于 amis 以 json 的方式在后端构建页面，减少前端开发工作量，提升开发效率。
-   在 amis 150多个组件都不满足的情况下, 可自行开发前端。
-   框架为前后端分离 (不用再因为框架而束手束脚~)。

  

### 内置功能

-   基础后台功能
    -   后台用户管理
    -   角色管理
    -   权限管理
    -   菜单管理
-   **代码生成器**
    -   保存生成记录
    -   导入/导出生成记录
    -   可使用命令清除生成的内容
    -   无需更改代码即可生成完整功能
-   `amis` 全组件封装 150+ , 无需前端开发即可完成复杂页面
-   多模块支持
-   图形化扩展管理

  

### 截图

  

### 安装

> 👉 **注意: `OwlAdmin` 是 `laravel` 的扩展包, 安装前请确保你会使用 `laravel`**

##### 1\. 创建 `laravel` 项目

composer create-project laravel/laravel example-app

##### 2\. 配置数据库信息并安装 `api` 模块

# .env
DB\_CONNECTION\=mysql
DB\_HOST\=127.0.0.1
DB\_PORT\=3306
DB\_DATABASE\=owl\_admin
DB\_USERNAME\=root
DB\_PASSWORD\=

安装`api` 模块

php artisan install:api

##### 3\. 获取 `Owl Admin`

composer require slowlyo/owl-admin

##### 4\. 安装

# 先发布框架资源
php artisan admin:publish
# 执行安装 (可以在执行安装命令前在 config/admin.php 中修改部分配置)
php artisan admin:install

##### 5\. 运行项目

启动服务, 访问 `/admin` 路由即可  
_初始账号密码都是 `admin`_

  

### 支持项目

你可以通过以下方式支持项目:

-   报告 Bug
-   提交 PR
    -   参见 贡献文档
-   点点 Star
    -   如果觉得项目不错，或者已经在使用了，希望你可以去 Github 或者 Gitee 帮我们点个 ⭐ Star，这将是对我们极大的鼓励与支持。
