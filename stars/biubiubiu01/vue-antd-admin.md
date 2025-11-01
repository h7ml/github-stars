---
project: vue-antd-admin
stars: 420
description: vue-antd-admin基于vue-cli4+vuex+ant-design-vue开发的后台管理系统，包括权限管理，布局方式，国际化，动态路由和后台管理系统常用的table表和表单等功能，包含echarts图的各种展示，第一版已完成，有兴趣可以了解下。
url: https://github.com/biubiubiu01/vue-antd-admin
---

vue antd admin
==============

**探索本项目的文档 »**  
  
在线预览 · 提出Bug · 提出建议

最近更新
----

vue3-basic-admin 已完成：`vue3-basic-admin` 是一款开源开箱即用的中后台管理系统。基于 `Vue3`、`Vite`、`Element-Plus`、`TypeScript`、`Pinia` 等主流技术开发，内置许多开箱即用的组件，能快速构建中后台管理系统，目前决定完全开源，如果角色该项目对你有所帮助，可以点一个star,如果有一定的经济能力，可以请作者喝一杯咖啡，开源不易！ 欢迎预览和使用：vue3-basic-admin

```

1.优化之前版本的权限控制，菜单通过角色控制，可以给用户对应的角色和多角色
2.优化mock数据部分，建立用户常量和角色常量
3.添加tag标签页鼠标滚动功能
4.添加真正的整体换肤功能
5.添加外链
6.添加可视化图，饼图，柱状图等拖拽
```

简介（有好的idea可以提issues,灵感丧失了...）
-----------------------------

vue-antd-admin是一个后台管理系统，基于vue+ant-design-vue开发，包含动态路由+权限管理解决用户权限问题，提供基础固定权限：admin、test、editor和自定义用户权限，可自定义修改角色对应的菜单,可定义用户多角色，布局方面提供左右布局和上下布局两种，可自由切换；系统内置了混合主题、浅色主题，深色主题，可随意切换；还有一些后台管理系统常用的功能如表单，table表等；

测试账号
----

```
过一段时间后才发现忘记放测试账号和密码了，哈哈哈


1.  用户名：admin  密码 任意6位数 （如果你喜欢，可以用123456） 拥有admin的权限可以查看所有页面
2.  用户名：test   密码 任意6位数 （如果你喜欢，可以用123456） 拥有test的页面权限，可以查看部分页面
3.  用户名：editor 密码 任意6位数 （如果你喜欢，可以用123456） 拥有editor的页面权限，可以查看富文本等页面
4.  使用手机号验证码登录 ，默认拥有admin的权限

```

已实现基础版node+express+mysql后台，地址：vue-antd-server

react版本，地址：reacct-antd-admin

前序准备
----

-   该项目采用vue+vue-cli4+vuex+ant-design-vue和axios开发，数据采用mock.js进行模拟,后期打算使用node写后台；
-   webpack大幅度优化了下，首屏加载速度更快；
-   系统内置了echarts常用的图表展示和arcgis地图；
-   使用了jest单元测试，目前覆盖率还比较低，有时间再写；
-   格式化方面采用 ESlint+prettier。

功能
--

```
- 登录  用户名密码/手机号验证码
- 权限  
- 动态路由
- echarts各种图表
- arcgis地图
- 克里金插值分析图
- 全景图
- 富文本
- Markdown
- 错误页面 403 404 500
- 个人设置
- 系统设置
- 更换主题
- 两种布局方式
- 面包屑
- 标签页
- webSocket 
- svg图标
- 全屏
- 返回顶部
- webpack优化
- 抽奖页
- table表
- form表单
- 上传Excel
- 上传头像和裁剪
- htmlcanvas2截屏
- 封装自定义loading
```

webpack优化
---------

```
- 关闭生产环境sourceMap;
- 关闭预加载(vue会预加载后面的页面，会导致首屏加载比较慢)
- g-zip压缩(需要nginx配置);
- 生产环境CDN加载部分插件
- 去除生产环境console和debugger;
- 公共代码抽离
- 打包大小分析
- 打包缓存
- 部分依赖使用异步cdn加载

```

使用说明
----

```
- 拥有 admin、test和editor三种权限，每个权限对应的路由和左侧菜单不同；
- 点击个人设置个性化或者右边设置，可以更改页面的设置，如果标签页是否开启，布局方式,主题颜色等；
- 系统管理员拥有所有权限，可以更改用户对应的菜单路由和角色对应的权限。
......
```

### 文件目录说明

```

├── mock                             ---mock模拟数据
├── public                           ---静态资源文件
├── src          
│  ├── api                           ---接口     
│  ├── assets                        ---图片
│  ├── components                    ---可复用的vue组件
│  ├── layouts                       ---布局方式
│  ├── router                        ---路由
│  ├── store                         ---vuex
│  ├── styles                        ---sass样式
│  ├── utils                         ---方法函数
│  ├── vendor                        ---导出excel
│  ├── views                         ---页面
│  ├── App.vue                       
│  ├── main.js            
│  ├── permission.js                 ---路由拦截           
├── tests                            ---单元测试文件
├── .browserslistrc
├── .env
├── .eslintrc.js
├──  babel.config.js
├── .jest.config.js                  ---jest的配置
├──  package.json
├──  package-lock.json
├──  README.md
└──  vue.config.js                   ---webpack的配置


```

安装
--

```
# 克隆项目
git clone https://github.com/biubiubiu01/vue-antd-admin.git
# 进入项目目录
cd vue-antd-admin
# 安装依赖
npm install
# 本地开发 启动项目
npm run serve
```

### 部署

```
# 打包项目
npm run build
# 单元测试
npm run test:unit
```

Online Demo
-----------

在线 Demo

最后
--

这个项目参考了 vue-element-admin 和 ant-design-pro,发现了好多好用的写法和方法，建议如果真想提升自己的代码水平，可以多看看大佬们的代码。 开源不易，若觉得这个项目对你有用，可以点个star，欢迎提出建议和bug 😄 。

捐赠
--

开源不易，若觉得这个项目对你有用，可以点个star，欢迎提出建议和bug 😄 。如果这个项目对你有所帮助，可以给作者买杯咖啡，欢迎投喂，任意金额捐赠加好友问题咨询。

扫码领大红包啦，有朋友领到88元大红包
-------------------
