---
project: lowcode-engine-ext
stars: 187
description: An enterprise-class low-code technology stack with scale-out design / 一套面向扩展设计的企业级低代码技术体系
url: https://github.com/alibaba/lowcode-engine-ext
---

### @alilc/lowcode-engine-ext

### 简介

lowcode-engine-ext 是阿里低代码引擎官方提供的 setter 和 setter 必须依赖的插件集合

setter(设置器) 是用来展示每个物料的属性，setter使用说明手册 官方setter列表说明

### 使用方式

使用 CDN 方式引用，下方是官方提供的两个稳定 CDN

#### 方式 1：alifd cdn

1: alifd cdn

https://alifd.alicdn.com/npm/@alilc/lowcode-engine-ext@1.0.5/dist/css/engine-ext.css

https://alifd.alicdn.com/npm/@alilc/lowcode-engine-ext@1.0.5/dist/js/engine-ext.js

#### 方式 2: uipaas cdn

https://uipaas-assets.com/prod/npm/@alilc/lowcode-engine-ext/1.0.5/dist/css/engine-ext.css

https://uipaas-assets.com/prod/npm/@alilc/lowcode-engine-ext/1.0.5/dist/js/engine-ext.js

#### 拓展变量绑定面板

通过传入extraDataMap拓展属性绑定面板

ctx.skeleton.add({
  area: 'centerArea',
  type: 'Widget',
  content: pluginMap.VariableBindDialog,
  name: 'variableBindDialog',
  props: {
    getSchema: () \=> editorController.getSchema(),
    // 拓展变量绑定
    extraDataMap: {
      props: {
        name: 'Props', // 变量组展示名
        key: 'props', // 属性名，例如 this.props
        getChildren: () \=> \[
          {
            label: 'prop1',
            value: 'value1',
          },
          {
            label: 'prop2',
            children: \[
              { label: 'propxxx', value: 1 }
            \]
          }
        \],
      }
    }
  },
});
