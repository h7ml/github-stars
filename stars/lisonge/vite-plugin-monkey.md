---
project: vite-plugin-monkey
stars: 1768
description: A vite plugin server and build your.user.js for userscript engine like Tampermonkey, Violentmonkey, Greasemonkey, ScriptCat
url: https://github.com/lisonge/vite-plugin-monkey
---

vite-plugin-monkey
==================

README | 中文文档

A vite plugin server and build your.user.js for userscript engine like Tampermonkey and Violentmonkey, Greasemonkey, ScriptCat

Feature
-------

-   support Tampermonkey, Violentmonkey, Greasemonkey, ScriptCat, etc
-   inject userscript comment to build bundle
-   auto open \*.user.js in default browser when userscript change
-   external cdn url inject to userscript @require
-   external module inject to userscript @resource
-   use GM\_api by ESM import with type hints
-   intelligently collect GM\_api that is used and automatically configure userscript @grant comment
-   support `top level await` and `dynamic import` in single file
-   when vite preview, auto open browser install dist.user.js
-   full typescript support and vite feature

Quick Start
-----------

just like vite create

pnpm create monkey
# npm create monkey
# yarn create monkey

then you can choose the following template

JavaScript

TypeScript

empty (only js)

empty-ts (only ts)

vanilla (js + css)

vanilla-ts (ts + css)

vue

vue-ts

react

react-ts

preact

preact-ts

svelte

svelte-ts

solid

solid-ts

Sample: Initializing a Template

Sample: Hot Module Replacement

Sample: Build & Preview

Installation
------------

pnpm add -D vite-plugin-monkey
# npm i -D vite-plugin-monkey
# yarn add -D vite-plugin-monkey

note: vite-plugin-monkey must be the `last item` of plugin list

graph LR;
    A(your code) -- "others plugins/vite build" -->B(esm)
    B -- "vite-plugin-monkey/vite build library mode" --> C{has DynamicImport}
    C -- yes --> D(systemjs)
    C -- no --> E(iife)

Loading

Config
------

export interface MonkeyOption {
  /\*\*
   \* userscript entry file path
   \*/
  entry: string;

  /\*\*
   \* userscript comment
   \*/
  userscript?: MonkeyUserScript;

  /\*\*
   \* @deprecated use {@link align} or {@link generate} instead
   \*/
  format?: {
    /\*\*
     \* @deprecated use {@link align} instead
     \*/
    align?: unknown;

    /\*\*
     \* @deprecated use {@link generate} instead
     \*/
    generate?: unknown;
  };

  /\*\*
   \* align userscript comment
   \* @default 2
   \*/
  align?: number | false;

  /\*\*
   \* custom generate userscript comment
   \*/
  generate?: (options: {
    userscript: string;
    mode: \`serve\` | \`build\` | \`meta\`;
  }) \=> Thenable<string\>;

  /\*\*
   \* alias of vite-plugin-monkey/dist/client
   \* @default '$'
   \* @example
   \* // vite-env.d.ts for type hint
   \*
   \* // if you use default value \`$\`
   \* /// <reference types="vite-plugin-monkey/client" />
   \*
   \* // if you use other\_alias
   \* declare module other\_alias {
   \*   export \* from 'vite-plugin-monkey/dist/client';
   \* }
   \*/
  clientAlias?: string;

  /\*\*
   \* handle CSS imports as style nodes(\[HTMLStyleElement\](https://developer.mozilla.org/docs/Web/API/HTMLStyleElement))
   \*
   \* If you use \[Shadow DOM\](https://developer.mozilla.org/docs/Web/API/Web\_components/Using\_shadow\_DOM) (style isolation) to place your interface application, this is very useful.
   \*
   \* Support \`.css?style\`, \`.less?style\`, \`.sass?style\`, \`.scss?style\`, \`.styl?style\`, \`.stylus?style\`, \`.pcss?style\`, \`.postcss?style\` and \`.sss?style\` imports
   \*
   \* add \`/// <reference types="vite-plugin-monkey/style" />\` to vite-env.d.ts for type hint
   \*
   \* @example
   \* import style1 from './style1.css?style':
   \* import style2 from 'normalize.css?style';
   \* const container = document.createElement('div').attachShadow({ mode: 'open' });
   \* container.append(style1, style2); // with hmr when change style1.css
   \* const style3 = style1.cloneNode(true); // it will still have hmr
   \*
   \* @default
   \* true
   \*/
  styleImport?: boolean;

  server?: {
    /\*\*
     \* auto open install url in default browser when userscript comment change
     \*
     \* and set \`viteConfig.server.open ??= monkeyConfig.server.open\`
     \* @default
     \* process.platform == 'win32' || process.platform == 'darwin' // if platform is Win/Mac
     \*/
    open?: boolean;

    /\*\*
     \* name prefix, distinguish server.user.js and build.user.js in monkey extension install list, if you not want prefix, set false
     \* @default 'server:'
     \*/
    prefix?: string | ((name: string) \=> string) | false;

    /\*\*
     \* mount GM\_api to unsafeWindow, not recommend it, you should use GM\_api by ESM import, or use \[unplugin-auto-import\](https://github.com/antfu/unplugin-auto-import)
     \* @default false
     \* @example
     \* // if set true, you can use \`vite-plugin-monkey/global\` for type hint
     \* // vite-env.d.ts
     \* /// <reference types="vite-plugin-monkey/global" />
     \*/
    mountGmApi?: boolean;
  };
  build?: {
    /\*\*
     \* build bundle userscript file name
     \*
     \* it should end with '.user.js'
     \* @default (package.json.name??'monkey')+'.user.js'
     \*/
    fileName?: string;

    /\*\*
     \* build bundle userscript comment file name, this file is only include comment
     \*
     \* it can be used by userscript.updateURL, when checking for updates, just download this small file instead of downloading the entire script
     \*
     \* it should end with '.meta.js', if set false, will not generate this file
     \*
     \* if set true, will equal to fileName.replace(/\\\\.user\\\\.js$/,'.meta.js')
     \*
     \* @default false
     \*/
    metaFileName?: string | boolean | ((fileName: string) \=> string);

    /\*\*
     \* this config can be array or object, array=Object.entries(object)
     \*
     \* if value is string or function, it or its return value is exportVarName
     \*
     \* if value is Array, the first \[item or its return value\] is exportVarName, the items after it all are url that is \[require url\]
     \*
     \* if module is unimported, plugin will not add require url to userscript
     \*
     \* @example
     \* { // map structure
     \*  vue:'Vue',
     \*  // if set this
     \*  // you need manually set userscript.require = \['https://unpkg.com/vue@3.0.0/dist/vue.global.js'\], when \`vite build\`
     \*
     \*  vuex:\['Vuex', (version, name)=>\`https://unpkg.com/${name}@${version}/dist/vuex.global.js\`\],
     \*  // plugin will auto add this url to userscript.require
     \*
     \*  'prettier/parser-babel': \[
     \*    'prettierPlugins.babel',
     \*    (version, name, importName) => {
     \*      // name == \`prettier\`
     \*      // importName == \`prettier/parser-babel\`
     \*      const subpath = \`${importName.split('/').at(-1)}.js\`;
     \*      return \`https://cdn.jsdelivr.net/npm/${name}@${version}/${subpath}\`;
     \*    },
     \*  \],
     \*  // sometimes importName deffers from package name
     \* }
     \* @example
     \* \[ // array structure, this example come from \[playground/ex-vue-demi\](https://github.com/lisonge/vite-plugin-monkey/tree/main/playground/ex-vue-demi)
     \*   \[
     \*     'vue',
     \*     cdn
     \*       .jsdelivr('Vue', 'dist/vue.global.prod.js')
     \*       .concat('https://unpkg.com/vue-demi@latest/lib/index.iife.js')
     \*       .concat(util.dataUrl('window.Vue=Vue')),
     \*   \],
     \*   \['pinia', cdn.jsdelivr('Pinia', 'dist/pinia.iife.prod.js')\],
     \*   \[
     \*     'element-plus',
     \*     cdn.jsdelivr('ElementPlus', 'dist/index.full.min.js'),
     \*   \],
     \* \]
     \*/
    externalGlobals?: ExternalGlobals;

    /\*\*
     \* according to final code bundle, auto inject GM\_\* or GM.\* to userscript comment grant
     \*
     \* @default true
     \*/
    autoGrant?: boolean;

    /\*\*
     \* @example
     \* {  // resourceName default value is pkg.importName
     \*   'element-plus/dist/index.css': pkg=>\`https://unpkg.com/${pkg.name}@${pkg.version}/${pkg.resolveName}\`,
     \*   'element-plus/dist/index.css': {
     \*     resourceName: pkg=>pkg.importName,
     \*     resourceUrl: pkg=>\`https://unpkg.com/${pkg.name}@${pkg.version}/${pkg.resolveName}\`,
     \*     loader: pkg=>{ // there are default loaders that support \[css, json, the assets that vite support, ?url, ?raw\] file/name suffix
     \*        const css = GM\_getResourceText(pkg.resourceName);
     \*        GM\_addStyle(css);
     \*        return css;
     \*     },
     \*     nodeLoader: pkg=>{
     \*        return \[
     \*          \`export default (()=>{\`,
     \*          \`const css = GM\_getResourceText(${JSON.stringify(pkg.resourceName)});\`,
     \*          \`GM\_addStyle(css);\`,
     \*          \`return css;\`,
     \*          \`})();\`
     \*        \].join('');
     \*     },
     \*   },
     \*   'element-plus/dist/index.css': \[
     \*      (version, name, importName, resolveName)=>importName,
     \*      (version, name, importName, resolveName)=>\`https://unpkg.com/${name}@${version}/${resolveName}\`,
     \*       // for compat externalGlobals cdn function, if (version/name/importName/resolveName) == '', plugin will use their own default values
     \*   \],
     \*   'element-plus/dist/index.css': cdn.jsdelivr(),
     \* }
     \*/
    externalResource?: ExternalResource;

    /\*\*
     \* when use dynamic-import, plugin will use systemjs build your code
     \*
     \* \`cdn.jsdelivr()\[1\]\` example -> \[dynamic-import.user.js\](https://github.com/lisonge/vite-plugin-monkey/blob/7645b185605faf9b48c43116db5ea01726188e03/playground/dynamic-import/dist/dynamic-import.user.js)
     \*
     \* \`'inline'\` exmple -> \[test-v3.user.js\](https://github.com/lisonge/vite-plugin-monkey/blob/7645b185605faf9b48c43116db5ea01726188e03/playground/test-v3/dist/test-v3.user.js)
     \*
     \* @default
     \* cdn.jsdelivr()\[1\]
     \*/
    systemjs?: 'inline' | ModuleToUrlFc;

    /\*\*
     \* @default
     \* const importCss = (css: string): void => {
     \*   if (typeof GM\_addStyle === 'function') {
     \*     GM\_addStyle(css);
     \*   } else {
     \*     document.head.appendChild(document.createElement('style')).append(css)
     \*   }
     \* };
     \* @example
     \* // example1
     \* importCss.toString()
     \*
     \* // example2
     \* \`(a)=>GM\_addStyle(a)\`
     \*/
    cssSideEffects?: string | ((css: string) \=> void);
  };
}

CDN util for external
---------------------

import { defineConfig } from 'vite';
import monkey, { cdn } from 'vite-plugin-monkey';
export default defineConfig({
  plugins: \[
    monkey({
      build: {
        externalGlobals: {
          react: cdn.jsdelivr('React', 'umd/react.production.min.js'),
        },
        externalResource: {
          'element-plus/dist/index.css': cdn.jsdelivr(),
        },
      },
    }),
  \],
});

there is the following cdn to use, full detail see cdn.ts

-   jsdelivr
-   unpkg
-   cdnjs
-   zhimg
-   npmmirror

if you want use other cdn, you can see external-scripts

Minify
------

because of the code-rules of greasyfork

> Code posted to Greasy Fork must not be obfuscated or minified

so plugin will change the default value of viteConfig.build.minify to `false`

if you want to enable minify, just set `viteConfig.build.minify=true`

GM\_api usage
-------------

### ESM usage

we can use GM\_api by esm module

// main.ts
import { GM\_cookie, unsafeWindow, monkeyWindow, GM\_addElement } from '$';
// $ is the default alias of vite-plugin-monkey/dist/client
// if you want use 'others', set monkeyConfig.clientAlias='others'

// whatever it is serve or build mode, monkeyWindow is always the window of \[UserScript Scope\]
console.log(monkeyWindow);

GM\_addElement(document.body, 'div', { innerHTML: 'hello' });

// whatever it is serve or build mode, unsafeWindow is always host window
if (unsafeWindow \== window) {
  console.log('scope->host, host esm scope');
} else {
  console.log('scope->monkey, userscript scope');
}

GM\_cookie.list({}, (cookies, error) \=> {
  if (error) {
    console.log(error);
  } else {
    const \[cookie\] \= cookies;
    if (cookie) {
      console.log(cookie);
    }
  }
});

### Global variables usage

set `monkeyConfig.server.mountGmApi=true`

// vite.config.ts
import { defineConfig } from 'vite';
import monkey from 'vite-plugin-monkey';

export default defineConfig({
  plugins: \[
    monkey({
      // ...
      server: { mountGmApi: true },
    }),
  \],
});

GM\_api will mount to the property of `host window/globalThis`

// main.ts
console.log(GM\_cookie \== globalThis.GM\_cookie);
console.log({ GM\_cookie, unsafeWindow, monkeyWindow, GM\_addElement });

### Auto import usage

use unplugin-auto-import

// vite.config.ts
import { defineConfig } from 'vite';
import monkey, { util } from 'vite-plugin-monkey';
import AutoImport from 'unplugin-auto-import/vite';

export default defineConfig({
  plugins: \[
    AutoImport({
      imports: \[util.unimportPreset\],
    }),
    monkey({
      // ...
    }),
  \],
});

// main.ts
// auto import example
console.log({ GM\_cookie, unsafeWindow, monkeyWindow, GM\_addElement });

Example
-------

test examples, see /playground

and preact/react/svelte/vanilla/vue/solid examples, see create-monkey

Some note
---------

### Work with other plugins

plugin will rebuild your code by generateBundle hook

please ensure that the order of the plugin is **the last one**

### CSP

in `vite serve` mode, the code entry is added as script to target host document.head, code need work between two origins

but the browser will prevent the execution of this script according to the CSP strategy

now just use browser extension Disable-CSP

### Mixed IIFE and UMD at @require

the variable declared by `var` from iife-cdn will not become the property of window at monkeyWindow scope, because monkeyWindow scope is not global scope

so if an umd lib is dependent on an iife lib, such as `element-plus` is dependent on `vue`, `element-plus` cdn will not work

detail see issues/5 or greasyfork#1084

the solution is that we append a dataUrl script that will set iife-variable as the property of window after iife-cdn

import { defineConfig } from 'vite';
import monkey, { cdn, util } from 'vite-plugin-monkey';

export default defineConfig(async ({ command, mode }) \=> ({
  plugins: \[
    monkey({
      // ...
      build: {
        externalGlobals: {
          vue: cdn
            .jsdelivr('Vue', 'dist/vue.global.prod.js')
            .concat(util.dataUrl(';window.Vue=Vue;')),
          'element-plus': cdn.jsdelivr('ElementPlus', 'dist/index.full.min.js'),
        },
      },
    }),
  \],
}));

### Polyfill

when plugin works with vite legacy, it is necessary to set `renderLegacyChunks=false`

// vite.config.ts
import legacy from '@vitejs/plugin-legacy';
import { defineConfig } from 'vite';
import monkey from 'vite-plugin-monkey';

export default defineConfig({
  plugins: \[
    legacy({
      renderLegacyChunks: false,
      modernPolyfills: true,
    }),
    monkey({
      entry: './src/main.ts',
    }),
  \],
});

How to Properly Build a Library Using GM\_api
---------------------------------------------

If you want to encapsulate GM\_api to build a library for others to use

The previous practice generally involved accessing GM\_api as a global variable directly in the library code and then referencing and loading it in userscript through `@require`.

However, this approach does not allow us to manage this dependency through npm or other package managers, and it is not compatible with the usage of ESM GM\_api in vite-plugin-monkey.

Now, you only need to import GM\_api normally from `vite-plugin-monkey/dist/client` in your library code. Modify your build config and exclude `vite-plugin-monkey/dist/client`.

This way, you can build a library that can be used in vite-plugin-monkey. Users of this library only need to install it via npm and use it normally with `import`.

Of course, if you directly bundle `vite-plugin-monkey/dist/client` into the build artifact, the library can also be referenced directly through `@require`.

However, to make the build artifact more concise, it is recommended that you redirect `vite-plugin-monkey/dist/client` to `vite-plugin-monkey/dist/native` during the build.

Below is an example using tsup to simultaneously package ESM and IIFE formats. ESM is provided to vite-plugin-monkey users, and IIFE is provided to users who want to reference it through `@require`.

Additionally, the IIFE format can also be used as a configuration for vite-plugin-monkey's externalGlobals to reduce the size of the build artifact.

// /src/index.ts
import { GM\_setValue } from 'vite-plugin-monkey/dist/client';

export const setValue \= (name: string, value: unknown) \=> {
  console.log('you invoke setValue', name, value);
  GM\_setValue(name, value);
};

// tsup.config.ts
import { defineConfig } from 'tsup';

const outExtension \= (ctx: { format: 'esm' | 'cjs' | 'iife' }) \=> ({
  js: { esm: '.mjs', cjs: '.cjs', iife: '.iife.js' }\[ctx.format\],
});

export default defineConfig(\[
  {
    // for vite import
    entry: \['src/index.ts'\],
    outDir: 'dist',
    sourcemap: true,
    platform: 'browser',
    outExtension,
    dts: true,
    format: \['esm'\],
    external: \['vite-plugin-monkey/dist/client'\],
  },
  {
    // for userscript @require
    entry: \['src/index.ts'\],
    outDir: 'dist',
    sourcemap: true,
    platform: 'browser',
    outExtension,
    dts: false,
    format: \['iife'\],
    minify: true,
    globalName: \`GmExtra\`,
    target: 'es2015',
    esbuildOptions: (options) \=> {
      options.alias \= {
        'vite-plugin-monkey/dist/client': 'vite-plugin-monkey/dist/native',
      };
    },
  },
\]);
