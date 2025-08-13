---
project: vite-plugin-vue-page-route
stars: 16
description: vite插件，根据页面文件生成路由声明文件
url: https://github.com/soybeanjs/vite-plugin-vue-page-route
---

@soybeanjs/vite-plugin-vue-page-route
=====================================

中文 | English

Vite 插件，根据页面文件自动生成路由声明、路由组件的导入、路由模块的定义。

用法
--

import { defineConfig } from "vite";
import pageRoute from "@soybeanjs/vite-plugin-vue-page-route";

export default defineConfig({
  plugins: \[
    pageRoute({
      pageDir: "src/views", // 默认
      pageGlobs: \["\*\*/index.{vue,tsx,jsx}", "!\*\*/components/\*\*"\], // 默认
      routeDts: "src/typings/page-route.d.ts", // 默认
      routeModuleDir: "src/router/modules", // 默认
      routeModuleExt: "ts", // 默认
      routeModuleType: "AuthRoute.Route", // 默认
      /\*\*
       \* @example \_builtin\_login => login
       \*/
      routeNameTansformer: (name) \=>
        name.replace(/^\_(\[a\-zA\-Z\]|\[0\-9\]|$)+\_\*/, ""), // 默认
      /\*\*
       \* 路由懒加载
       \* @param name 路由名称
       \* @example
       \* - 直接导入
       \* \`\`\`ts
       \* import Home from './views/home/index.vue';
       \* \`\`\`
       \* - 懒加载导入
       \* \`\`\`ts
       \* const Home = import('./views/home/index.vue');
       \* \`\`\`
       \*/
      lazyImport: (\_name) \=> true, // 默认
      /\*\*
       \* 是否生成路由模块
       \* @param name 未转换过的路由名称(没有调用函数routeNameTansformer)
       \* @returns 是否生成路由模块的代码
       \*/
      onRouteModuleGenerate: (name) \=> !name.includes("\_builtin"), // 对于系统内置路由不生成路由模块, 其他的都生成
    }),
  \],
});
