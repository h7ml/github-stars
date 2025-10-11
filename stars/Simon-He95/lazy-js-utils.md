---
project: lazy-js-utils
stars: 78
description: 工具函数库 | Tool library
url: https://github.com/Simon-He95/lazy-js-utils
---

🚀 Lazy JS Utils
================

**🎯 专为现代开发者打造的轻量级 JavaScript 工具库**

📖 在线文档 • English • 快速开始 • 特色功能

* * *

✨ 为什么选择 Lazy JS Utils？
----------------------

🎯 **告别繁琐** - 200+ 精选函数，解决 90% 的日常开发需求 ⚡ **开箱即用** - 零配置，直接在任何 JS 环境中使用 🧩 **按需引入** - Tree-shaking 友好，只打包你用到的代码 🛡️ **类型安全** - 完整的 TypeScript 支持，IDE 智能提示 🔄 **自动清理** - 智能内存管理，告别内存泄漏烦恼

🚀 快速开始
-------

# 安装
npm install lazy-js-utils

import {
  insertElement,
  useEventListener,
  useMutationObserver,
} from 'lazy-js-utils'

// 🎯 一行代码添加事件监听，自动清理
const stopListening \= useEventListener('#button', 'click', () \=> {
  console.log('点击了按钮！')
})

// 🔍 监听 DOM 变化，无需 ref
useMutationObserver('#container', (mutations) \=> {
  console.log('容器内容发生变化:', mutations)
})

// ➕ 简单的元素操作
insertElement('#container', '<div>新内容</div>')

🎯 特色功能
-------

### 🎪 DOM 操作更简单

// 传统方式 😵
const container \= document.querySelector('#container')
const newElement \= document.createElement('div')
newElement.innerHTML \= 'Hello World'
container?.appendChild(newElement)

// Lazy JS Utils 方式 😎
insertElement('#container', '<div>Hello World</div>')

### 🎮 事件管理更智能

// 自动清理的事件监听
const stop \= useEventListener(window, 'resize', () \=> {
  console.log('窗口大小改变')
})

// 页面卸载时自动调用 stop()，无需手动清理！

### 🎬 动画更流畅

// 高性能动画帧控制
useRaf(
  (timestamp) \=> {
    // 每秒执行一次的动画
    updateAnimation(timestamp)
  },
  {
    delta: 1000,
    autoStop: true, // 执行一次后自动停止
  },
)

📦 核心模块
-------

模块

功能

示例

🎯 **DOM**

元素操作、选择器

`insertElement`, `removeElement`

🎮 **Events**

事件监听、自动清理

`useEventListener`, `useMutationObserver`

🎬 **Animation**

动画帧、缓动函数

`useRaf`, `useInterval`

🔧 **Utils**

工具函数、类型判断

`deepCompare`, `throttle`, `debounce`

📝 **String**

字符串处理

`camelCase`, `kebabCase`

🔢 **Math**

数学计算

`clamp`, `random`

🎨 实际应用场景
---------

// 📱 响应式设计
useEventListener(
  window,
  'resize',
  throttle(() \=> {
    // 节流处理窗口缩放
    updateLayout()
  }, 300),
)

// 🖼️ 图片懒加载
useMutationObserver('.image-container', (mutations) \=> {
  mutations.forEach((mutation) \=> {
    // 自动处理新增的图片元素
    lazyLoadImages(mutation.addedNodes)
  })
})

// 🎪 动态表单
insertElement(
  '.form-container',
  createFormField({
    type: 'input',
    placeholder: '请输入内容',
  }),
)

📈 性能对比
-------

场景

原生 JS

Lazy JS Utils

性能提升

事件监听清理

手动管理

自动清理

⚡ 100%

DOM 操作

10+ 行代码

1 行代码

🚀 90%

内存使用

容易泄漏

智能管理

💾 80%

🎯 Browser Support
------------------

Chrome ✅

Firefox ✅

Safari ✅

Edge ✅

🤝 参与贡献
-------

我们欢迎任何形式的贡献！

-   🐛 报告 Bug
-   💡 提出新功能
-   📖 改进文档
-   ⭐ 给项目点个 Star

📚 相关链接
-------

-   📖 完整文档
-   🎮 在线演示
-   💬 讨论区
-   ☕ 请作者喝咖啡

📄 License
----------

MIT © 2024 Simon He

* * *

Built with ❤️ by Simon He
