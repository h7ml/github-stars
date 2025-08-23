---
project: vitepress-nav-template
stars: 357
description: 基于 VitePress 的个人前端导航页面模板
url: https://github.com/maomao1996/vitepress-nav-template
---

vitepress-nav-template
======================

基于 **VitePress** 的个人前端导航页面模板

基础教程 | 作者博客

* * *

预览地址
----

-   https://fe-nav.netlify.app/nav/
-   https://maomao1996.github.io/vitepress-nav-template/nav/

功能
--

-   新增 `layout-class` 方便更好的自定义样式
-   默认中文
-   自带前端导航模块
-   支持访客统计
-   支持 giscus 评论
-   支持日夜颜色模式自适应切换
-   支持 Github Pages 直接部署上线
    -   1.  开启 github actions
    -   1.  配置 Pages 的 Branch 为 `gh-pages` 分支，文件夹为 `/(root)`
    -   1.  访问地址为 `https://<username>.github.io/<repository>/` 或自定义域名
-   支持 tailwindcss
-   支持查看 vue 示例组件源码（使用 vite-plugin-markdown-preview）

#### 使用自定义域名部署

当 Github Pages 使用自定义域名时，需要修改 `.github/workflows/deploy.yml` 脚本中的 `APP_BASE_PATH` 为 `/`

更**推荐使用第三方服务绑定域名来部署**

-   Netlify
-   Vercel
-   Cloudflare Pages

使用仪表板创建新项目并更改这些设置：

-   **构建命令：** `npm run build`
-   **输出目录：** `dist`
-   **node 版本：** `18` (或更高版本)

更多部署指南请查看 VitePress 各平台部署指南

### 开启访客统计

需在 `docs/.vitepress/config.ts` 中配置 `themeConfig.visitor`

export default defineConfig({
  themeConfig: {
    /\* 访客统计 \*/
    visitor: {
      /\*\* 统计 id（单独页面的统计会作为前缀使用）\*/
      badgeId: 'maomao1996.vitepress-nav-template',
    },
  },
})

### 开启 giscus 评论

需在 `docs/.vitepress/config.ts` 中配置 `themeConfig.comment`

export default defineConfig({
  themeConfig: {
    /\*\*
     \* giscus 评论配置
     \*  请根据 https://giscus.app/zh-CN 生成内容填写
     \*/
    comment: {
      /\*\* github 仓库地址 \*/
      repo: '',
      /\*\* giscus 仓库 ID \*/
      repoId: '',
      /\*\* Discussion 分类 \*/
      category: '',
      /\*\* giscus 分类 ID \*/
      categoryId: '',
    },
  },
})

#### 在指定页面关闭评论

需在指定页面的 `markdown` 文件中添加如下 `frontmatter` 配置

\---
comment: false
\---

\# 功能测试页

docs: 更新 README

说明
--

前端导航模块由 茂茂 | maomao 开发，如有引用、借鉴的请保留版权声明：https://github.com/maomao1996/vitepress-nav-template
