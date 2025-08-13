---
project: n-page-frame
stars: 1
description: 多页 webpack 配置，内置 react vue
url: https://github.com/lvyueyang/n-page-frame
---

基本之外的操作
-------

1.  可以在 package.json script.start 后面添加参数，只编译指定的页面

"webpack serve --env development --env include=vue-demo"

1.  可以使用 `npm run create [页面名称] [页面类型]` 来快速创建新的页面

# 创建一个 无框架 类型的页面
npm run create pageName  
# 创建一个 vue 类型的页面
npm run create pageName vue  
# 创建一个 react 类型的页面
npm run create pageName react
