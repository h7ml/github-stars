---
project: taro-hooks
stars: 452
description: Hooks Library for Taro
url: https://github.com/innocces/taro-hooks
---

  

### V2 | V1

### 

  

  

Hooks Library for Taro

✨ Features
----------

-   Fully matched Taro
-   Extending common hooks with ahooks
-   Separate abstraction useRequest
-   Complete type tips
-   Extended h5 missing apis

🚀 Quick Start
--------------

# npm
$ npm i taro-hooks
# yarn
$ yarn add taro-hooks
# pnpm
$ pnpm add taro-hooks

We use plugins for extending different frameworks. So you need to install the corresponding plugins according to the framework you are currently using

-   React/PReact/Nerv

# npm
$ npm i @taro-hooks/plugin-react
# yarn
$ yarn add @taro-hooks/plugin-react
# pnpm
$ pnpm add @taro-hooks/plugin-react

// config/index.js
module.exports \= {
  // ...
  plugins: \['@taro-hooks/plugin-react'\],
  // ...
};

-   Vue3

# npm
$ npm i @taro-hooks/plugin-vue
# yarn
$ yarn add @taro-hooks/plugin-vue
# pnpm
$ pnpm add @taro-hooks/plugin-vue

// config/index.js
module.exports \= {
  // ...
  plugins: \['@taro-hooks/plugin-vue'\],
  // ...
};

⌨️ Usage
--------

-   React/PReact/Nerv

import { useEnv } from 'taro-hooks';

function Index() {
  const env \= useEnv();

  return <View\>current env: {env}</View\>;
}

-   Vue3

<template\>
  <view\>current env: {{env}}</view\>
</template\>

<script setup lang\="ts"\>
  import { useEnv } from 'taro-hooks';

  const env \= useEnv();
</script\>

🎰 auto-import
--------------

We provide the @taro-hooks/plugin-auto-import plugin to help you quickly use the unplugin-auto-import capability.

# npm
$ npm i @taro-hooks/plugin-auto-import
# yarn
$ yarn add @taro-hooks/plugin-auto-import
# pnpm
$ pnpm add @taro-hooks/plugin-auto-import

// config/index.js
const config \= {
  // ...
  // The main prerequisite is that you have installed the plugin for the corresponding framework.
  plugins: \[
    // If you are using vue3, please install the @taro-hooks/plugin-vue plugin beforehand.
    '@taro-hooks/plugin-vue'，
    // If using React/PReact/Nerv, please pre-install the @taro-hooks/plugin-react plugin.
    '@taro-hooks/plugin-react',
    // Finally, the auto-import plugin is configured
    \[
      '@taro-hooks/plugin-auto-import',
      {
        // your options, see configuration: https://github.com/antfu/unplugin-auto-import#configuration
      }
    \]
  \],
  // ...
};

-   React/PReact/Nerv

function Index() {
  const env \= useEnv();

  return <View\>current env: {env}</View\>;
}

-   Vue3

<template\>
  <view\>current env: {{env}}</view\>
</template\>

<script setup lang\="ts"\>
  const env \= useEnv();
</script\>

📦 Packages
-----------

packages

downloads

version

license

🗨️ Communication
-----------------

🤸 Contribution
---------------

See Contributing Guide.

🍻 Contributors
---------------

  
**innocces**  
💬 📖 👀 📢 🤔 ⚠️ 📦 📋 🎨

  
**ryan**  
📖 📢 🤔 💻

more contributors

📑 License
----------

MIT.

💰 Sponsoring
-------------

📈 Star History
---------------
