---
project: vue3-tree-org
stars: 166
description: 基于vue3.x + typeScript 实现的组织架构图
url: https://github.com/sangtian152/vue3-tree-org
---

vue3-tree-org
=============

  

### 介绍

一个基于vue3.x的简易版组织架构图，vue2.x版本请访问zm-tree-org

-   架构图支持拖拽和通过鼠标滚轮缩放
-   支持新增/删除节点
-   支持编辑节点名称
-   支持拖动节点改变树结构
-   支持自定义右键菜单
-   支持slot自定义节点渲染内容
-   支持slot自定义展开按钮渲染内容

### 安装

```
npm install vue3-tree-org --save
# or 
yarn add vue3-tree-org
```

### 引入

```
import { createApp } from 'vue'
import vue3TreeOrg from 'vue3-tree-org';
import "vue3-tree-org/lib/vue3-tree-org.css";

const app = createApp(App)

app.use(vue3TreeOrg)
app.mount('#app')
```

### 使用示例

示例代码

### 最新版本

### 文档

说明文档.

### 友情链接

virtual-tree虚拟化树形控件，致力于解决数据量过大导致页面卡顿甚至崩溃问题  
watermark图片加水印，支持文字水印、图片水印，支持多行  
html2pdf将html生成pdf，依赖html2canvas和jspdf  
zm-sign一个简易签名组件，基于vue和canvas
