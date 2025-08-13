---
project: vitepress-plugin-sandpack
stars: 54
description: Use sandpack-vue3 in vitepress as directive.
url: https://github.com/jerrywu001/vitepress-plugin-sandpack
---

install
=======

This is plugin for vitepress that give you the power of editable sandboxes that run in the browser.

Language support: `angular` | `react` | `react-ts` | `vanilla` | `vanilla-ts` | `vue` | `vue3` | `vue3-ts` | `svelte` | `solid` | `test-ts`.

-   install package
    
    cd project-folder
    
    npm i vitepress-plugin-sandpack -D
    
    TIPS: for `pnpm`
    
    you need:
    
    pnpm add markdown-it-container -D
    
-   edit theme config, register global component
    
    `docs/.vitepress/theme/index.ts`
    
    import DefaultTheme from 'vitepress/theme';
    +import { Sandbox } from 'vitepress-plugin-sandpack';
    +import 'vitepress-plugin-sandpack/dist/style.css';
    
    export default {
      ...DefaultTheme,
      enhanceApp(ctx) {
        DefaultTheme.enhanceApp(ctx);
    +    ctx.app.component('Sandbox', Sandbox);
      },
    }
    
-   edit config
    
    `docs/.vitepress/config.ts`
    
    import { defineConfig } from 'vitepress';
    import container from 'markdown-it-container';
    import { renderSandbox } from 'vitepress-plugin-sandpack';
    
    // rule of 'html tag name' to 'component name'
    // 'sanbox' -> 'Sandbox'
    // 'my-sandbox' -> MySandbox
    // 'sandbox-react-demo' -> SandboxReactDemo
    
    export default defineConfig({
      // ...
    
      markdown: {
        config(md) {
          md
            // the second parameter is html tag name
            .use(container, 'sandbox', {
              render (tokens, idx) {
                return renderSandbox(tokens, idx, 'sandbox');
              },
            });
        },
      },
    
      // ...
    })
    

document
========

Full document

Custom usage

vite-templates (from @0.3.0)

大陆备用地址

how to use
----------

online demo

-   code in markdown file
    
-   preview in browser
    
    light mode
    
    dark mode
    

use file snippets
-----------------

File snippets

Sponsor
-------

### Special Sponsor
