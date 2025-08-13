---
project: fighting-design
stars: 571
description: 🌈 Fighting Design 可在 vue3 应用程序中快速构建交互界面，看起来还不错。(🌈 Fighting design can quickly build interactive interfaces in vue3 applications, which looks good.)
url: https://github.com/FightingDesign/fighting-design
---

Fighting Design
---------------

Fighting design can quickly build interactive interfaces in vue3 applications, which looks good.

Chinese | English

✨ Features
----------

-   🪐 60+ common components
-   💪 Developed with the latest features of Vue.js
-   🐆 Fully based on Vite, fast enough
-   🤟 Ultimate development experience
-   🥇 Ultra detailed JSDoc comments
-   🦩 Zero third party dependency
-   🪐 Different packaging modes which compatible with different projects
-   🏆 Support full import and on-demand import
-   ✅ Written with TypeScript & Template
-   🖍️ Strict TypeScript Type
-   ✔️ Easy to configure and easy to use
-   🚩 Complete and adequate unit tests
-   👍 Maintained by the community team
-   ❤️ Developed according to actual demand
-   📃 High quality detailed documentation
-   ☝️ Put forward demands and keep improving
-   🌍 More configuration options & flexible components
-   🛠 More features are under development

🔑 Install
----------

Use `pnpm` install

pnpm add --save-dev fighting-design

Use `npm` install

npm install --save-dev fighting-design

Use `yarn` install

yarn add --save-dev fighting-design

🎉 Quick Start
--------------

Put the following code into `main.ts`

import { createApp } from 'vue'
import App from './App.vue'

import FightingDesign from 'fighting-design'
import 'fighting-design/dist/index.css'

const app \= createApp(App)
app.use(FightingDesign)
app.mount('#app')

🪂 Quick experience
-------------------

<head\>
  <link
    rel\="stylesheet"
    href\="https://cdn.jsdelivr.net/npm/fighting-design/dist/index.css"
  />
</head\>

<body\>
  <div id\="app"\>
    <f-space\>
      <f-button round type\="default"\>默认按钮</f-button\>
      <f-button round type\="primary"\>主要按钮</f-button\>
      <f-button round type\="success"\>成功按钮</f-button\>
      <f-button round type\="danger"\>危险按钮</f-button\>
      <f-button round type\="warning"\>警告按钮</f-button\>
    </f-space\>

    <f-divider\>华丽的分隔线</f-divider\>

    <f-button type\="primary" @click\="visible = true"\>打开 Dialog</f-button\>
    <f-dialog title\="Title" v-model:visible\="visible"\>
      欢迎使用 Fighting Design！
    </f-dialog\>
  </div\>

  <script src\="https://cdn.jsdelivr.net/npm/vue/dist/vue.global.js"\></script\>
  <script src\="https://cdn.jsdelivr.net/npm/fighting-design/dist/index.umd.js"\></script\>
  <script\>
    const { createApp, ref } \= Vue

    const app \= createApp({
      setup() {
        const visible \= ref(false)

        return { visible }
      }
    })

    app.use(FightingDesign.default)
    app.mount('#app')
  </script\>
</body\>

🐳 Related links
----------------

-   Official documents
-   NPM
-   CONTRIBUTING
-   CHANGELOG

🌈 Join Fighting Design
-----------------------

Add WeChat & please note the `Github` username

💌 Special Thanks
-----------------

Thanks to everyone who has already contributed to `Fighting Design`!

💬 LICENSE
----------

MIT
