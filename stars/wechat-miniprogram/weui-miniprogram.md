---
project: weui-miniprogram
stars: 2351
description: 小程序WeUI组件库
url: https://github.com/wechat-miniprogram/weui-miniprogram
---

WeUI组件库简介
---------

这是一套基于样式库weui-wxss开发的小程序扩展组件库，同微信原生视觉体验一致的扩展组件库，由微信官方设计团队和小程序团队为微信小程序量身设计，令用户的使用感知更加统一。

如何使用
----

详细使用参考文档

开发
--

1.  初始化

```
npm run init
```

1.  执行命令：

```
npm run dev
```

1.  构建组件库：

```
npm run build
```

适配 DarkMode
-----------

在根结点（或组件的外层结点）增加属性 `data-weui-theme="dark"`，即把 WeUI 组件切换到 DarkMode 的表现，如:

<view data-weui-theme\="dark"\>
    ...
</view\>
