---
project: vue3-sfc-loader
stars: 1316
description: Single File Component loader for Vue2 and Vue3. Load .vue files directly from your HTML. No node.js environment, no build step.
url: https://github.com/FranckFreiburger/vue3-sfc-loader
---

vue3-sfc-loader
===============

###### API | FAQ | Examples | dist | Roadmap

Vue3/Vue2 Single File Component loader.  
Load .vue files dynamically at runtime from your html/js. No node.js environment, no (webpack) build step needed.

Key Features
------------

-   Supports Vue 3 and Vue 2 (see dist/)
-   Only requires Vue runtime-only build
-   **esm** and **umd** bundles available (example)
-   Embedded ES6 modules support ( including `import()` )
-   TypeScript support, JSX support
-   Custom CSS, HTML and Script language Support, see pug and stylus examples
-   SFC Custom Blocks support
-   Properly reports template, style or script errors through the log callback
-   Focuses on component compilation. Network, styles injection and cache are up to you (see example below)
-   Easily build your own version and customize browsers you need to support

Example
-------

<html\>
<body\>
  <div id\="app"\></div\>
  <script src\="https://unpkg.com/vue@latest"\></script\>
  <script src\="https://cdn.jsdelivr.net/npm/vue3-sfc-loader/dist/vue3-sfc-loader.js"\></script\>
  <script\>

    const options \= {
      moduleCache: {
        vue: Vue
      },
      async getFile(url) {
        
        const res \= await fetch(url);
        if ( !res.ok )
          throw Object.assign(new Error(res.statusText + ' ' + url), { res });
        return {
          getContentData: asBinary \=> asBinary ? res.arrayBuffer() : res.text(),
        }
      },
      addStyle(textContent) {

        const style \= Object.assign(document.createElement('style'), { textContent });
        const ref \= document.head.getElementsByTagName('style')\[0\] || null;
        document.head.insertBefore(style, ref);
      },
    }

    const { loadModule } \= window\['vue3-sfc-loader'\];

    const app \= Vue.createApp({
      components: {
        'my-component': Vue.defineAsyncComponent( () \=> loadModule('./myComponent.vue', options) )
      },
      template: '<my-component></my-component>'
    });

    app.mount('#app');

  </script\>
</body\>
</html\>

### More Examples

see all examples

Try It Online
-------------

https://codepen.io/franckfreiburger/project/editor/AqPyBr

Public API documentation
------------------------

**loadModule**(`path`: string, `options`: Options): `Promise<VueComponent>`

dist/
-----

  

-   `npm install vue3-sfc-loader`
-   jsDelivr CDN: https://cdn.jsdelivr.net/npm/vue3-sfc-loader/dist/vue3-sfc-loader.js
-   UNPKG CDN: https://unpkg.com/vue3-sfc-loader

**esm version**: `dist/vue3-sfc-loader.esm.js`  
**umd version**: `dist/vue3-sfc-loader.js`

  

-   `npm install vue3-sfc-loader` (use 'vue3-sfc-loader/dist/vue2-sfc-loader.js')
-   jsDelivr CDN: https://cdn.jsdelivr.net/npm/vue3-sfc-loader/dist/vue2-sfc-loader.js
-   UNPKG CDN: https://unpkg.com/vue3-sfc-loader/dist/vue2-sfc-loader.js

**esm version**: `dist/vue2-sfc-loader.esm.js`  
**umd version**: `dist/vue2-sfc-loader.js`

Build your own version
----------------------

Example: enable IE11 support  
`npx webpack --config ./build/webpack.config.js --mode=production --env targetsBrowsers="> 1%, last 8 versions, Firefox ESR, not dead, IE 11"` check

_see `package.json` "build" script_  
_see browserslist queries_

**preliminary steps:**

1.  clone `vue3-sfc-loader`
2.  (install yarn: `npm install --global yarn`)
3.  run `yarn install`

How It Works
------------

`vue3-sfc-loader.js` = `Webpack`( `@vue/compiler-sfc` + `@babel` )

### more details

1.  load the `.vue` file
2.  parse and compile template, script and style sections (`@vue/compiler-sfc`)
3.  transpile script and compiled template to es5 (`@babel`)
4.  parse scripts for dependencies (`@babel/traverse`)
5.  recursively resolve dependencies
6.  merge all and return the component

Any Questions
-------------

💬 ask in Discussions tab

Financial contributors
======================

Many thanks to people that support this project !
