---
project: react-admin
stars: 554
description: 动态菜单配置、权限精确到按钮、通用模块；标准后台管理系统解决方案
url: https://github.com/javaLuo/react-admin
---

React-admin ·
=============

标准后台管理系统解决方案  
动态菜单配置，权限精确到按钮  

what's this?
------------

react+redux 后台管理系统脚手架  
react+redux+vite+antd

-   非服务端渲染
-   仿antd-pro外观，但没有使用dva和roadhog

构建 Start
--------

pnpm install       // 安装依赖模块
pnpm run dev       // 运行开发环境
pnpm run build     // 正式打包，生成最终代码
pnpm run preview   // 本地运行正式打包后的最终代码
pnpm run prettier  // 一键格式化代码

最近更新
----

-   接入了vite打包，比自己配webpack要好多了

前后端分离，权限是怎么控制的
--------------

在数据库里存储着权限的信息，可以在页面里各种编辑。  
但最终实现，仍然是在页面里写死的，前端写在页面里的权限信息跟数据库里的信息一一对应就实现了权限控制。  
更好的方法除非是使用 SSR 服务端渲染，直接把权限注入到页面中，就像传统的 JSP 那样。

内置通用功能
------

用户管理 增删改查 分配角色  
  角色管理 增删改查 分配菜单和权限  
  权限管理 增删改查  
  菜单管理 增删改查  

关系：权限 依附于 菜单 依附于 角色 依附于 用户

预览地址 Demo
---------

https://isluo.com/work/admin/  
账号：admin / user  
密码：123456 / 123456

参考
--

react-luo: https://github.com/javaLuo/react-luo
