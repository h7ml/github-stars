---
project: vue3-cron
stars: 49
description: Corn expression plugin based on vue3+elementplus（基于vue3+elementplus的corn表达式插件）
url: https://github.com/sugdove/vue3-cron
---

vue3-cron
=========

这是一个 cron 表达式生成插件,基于 vue3.0 与 element-plus 实现 demo

项目地址
----

-   github : https://github.com/sugdove/vue3-cron
    
-   github 项目启动: 1.yarn install 2.yarn serve
    

依赖
--

-   Vue 3.0.0+
-   elementplus

安装方式
----

```
npm install vue3-cron
```

全局引入方式
------

//前置配置
import { createApp } from 'vue'
import ElementPlus from 'element-plus'
import 'element-plus/lib/theme-chalk/index.css'
import App from './App.vue'
//全局引入
import vue3Cron from 'vue3-cron'
import 'vue3-cron/lib/vue3Cron.css' // 引入样式
const app \= createApp(App)
app
  .use(ElementPlus)
  .use(vue3Cron)
  .mount('#app') //使用方式：<vue3Cron></vue3Cron>

局部引入方式
------

//局部引入
import { vue3Cron } from 'vue3-cron'
import 'vue3-cron/lib/vue3Cron.css' // 引入样式
export default {
  template: '<vue3Cron/>',
  components: { vue3Cron },
}

示例
--

<template\>
  <div class\="cron"\>
    <h1\>vue3-cron</h1\>
    <el-popover
      v-model:visible\="state.cronPopover"
      width\="700px"
      trigger\="manual"
    >
      <vue3Cron
        @change\="changeCron"
        @close\="togglePopover(false)"
        max-height\="400px"
        i18n\="cn"
      ></vue3Cron\>
      <template #reference\>
        <el-input
          @focus\="togglePopover(true)"
          v-model\="state.cron"
          placeholder\="\* \* \* \* \* ? \*"
        ></el-input\>
      </template\>
    </el-popover\>
  </div\>
</template\>

<script\>
import { reactive, defineComponent, watch } from 'vue'
export default defineComponent({
  setup() {
    const state \= reactive({
      cronPopover: false,
      cron: '',
    })
    const changeCron \= (val) \=> {
      if (typeof val !== 'string') return false
      state.cron \= val
    }
    const togglePopover \= (bol) \=> {
      state.cronPopover \= bol
    }
    return {
      state,
      changeCron,
      togglePopover,
    }
  },
})
</script\>

<style lang="scss" scoped>
.cron {
  width: 400px;
  margin: 0 auto;
  margin-top: 100px;
  h1 {
    font-size: 50px;
    text-align: center;
  }
}
</style\>

在示例中我使用了 es6(es2015)语法,你可能需要引入 babel-polyfill 才能正常运行,或者你也可以用 es5 的写法

参数
--

-   i18n
    
    -   参数 `{String} language` 目前仅支持`en|cn`
    
    国际化支持
    
-   max-height
    
    -   参数 `{String} height`
    
    设定 vue3-cron 的 max-height, 默认没有该属性
    

事件
--

-   change(cronText)
    
    -   参数：`{String} cronText` cron 表达式的值
    
    当 corn 表达式的值发生变化变化时触发
    
-   close()
    
    -   参数：无
    
    当点击 corn 表达式选择框取消按钮时触发
    

联系方式
----

邮箱 : 849809724@qq.com

欢迎大家关注我做的网站: http://www.githubs.cloud/

如果对您有帮助, 欢迎 star

有任何问题请发 Issues 或者邮箱联系我-.- 谢谢!
