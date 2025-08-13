---
project: vue3-amis
stars: 1
description: vue3的amis组件库
url: https://github.com/zy598586050/vue3-amis
---

vue3-amis组件
===========

### 功能

✅ AmisEditer 编辑器  
✅ AmisRender 解析器  

安装
--

# with npm
npm install vue3-amis
# with pnpm
pnpm add vue3-amis

使用
--

```
// 编辑器
<template>
  <AmisEditer></AmisEditer>
</template>

<script setup lang="ts">
import { AmisEditer } from 'vue3-amis'
import 'vue3-amis/dist/index.css'
</script>

// 解析器
<template>
  <AmisRender :option="option"></AmisRender>
</template>

<script setup lang="ts">
import { AmisRender } from 'vue3-amis'
import 'vue3-amis/dist/index.css'
const option = {
  "type": "page",
  "body": {
    "type": "form",
    "title": "custom 组件",
    "body": [
      {
        "type": "input-text",
        "name": "username",
        "label": "姓名"
      },
      {
        "name": "username",
        "type": "custom",
        "label": "自定义组件",
        "onMount": "const button = document.createElement('button'); button.innerText = '点击修改姓名'; button.onclick = event => { onChange('new name', 'username'); event.preventDefault(); }; dom.appendChild(button);"
      }
    ]
  }
}
</script>
```
