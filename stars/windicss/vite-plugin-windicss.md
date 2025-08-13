---
project: vite-plugin-windicss
stars: 853
description: 🍃 Windi CSS for Vite ⚡️
url: https://github.com/windicss/vite-plugin-windicss
---

**⚠️ Windi CSS is Sunsetting ⚠️**  
We are sunsetting Windi CSS and we recommend new projects to seek for alternatives. Read the full blog post.

* * *

vite-plugin-windicss
====================

Windi CSS for Vite, it's fast! ⚡️  

Features
--------

-   ⚡️ **It's FAST** - 20~100x times faster than Tailwind on Vite
-   🧩 On-demand CSS utilities (Fully compatible with Tailwind CSS v2)
-   📦 On-demand native elements style reseting (preflight)
-   🔥 Hot module replacement (HMR)
-   🍃 Load configurations from `tailwind.config.js`
-   🤝 Framework-agnostic - Vue, React, Svelte and vanilla!
-   📄 CSS `@apply` / `@screen` directives transforms (also works for Vue SFC's `<style>`)
-   🎳 Support Variant Groups - e.g. `bg-gray-200 hover:(bg-gray-100 text-red-300)`
-   😎 "Design in Devtools" - if you work this way in the traditional Tailwind, no reason we can't!

Documentation
-------------

Read the documentation for more details.

New Features in v3.0
--------------------

### Attributify Mode

Enabled it by

// windi.config.ts
export default {
  attributify: true,
}

And use them as you would like:

<button 
  bg\="blue-400 hover:blue-500 dark:blue-500 dark:hover:blue-600"
  text\="sm white"
  font\="mono light"
  p\="y-2 x-4"
  border\="2 rounded blue-200"
\>
  Button
</button\>

#### Prefix

If you are concerned about naming confliction, you can add custom prefix to attributify mode by:

// windi.config.ts
export default {
  attributify: {
    prefix: 'w:',
  },
}

<button 
  w:bg\="blue-400 hover:blue-500 dark:blue-500 dark:hover:blue-600"
  w:text\="sm white"
  w:font\="mono light"
  w:p\="y-2 x-4"
  w:border\="2 rounded blue-200"
\>
  Button
</button\>

### Alias Config

// windi.config.ts
export default {
  alias: {
    'hstack': 'flex items-center',
    'vstack': 'flex flex-col',
    'icon': 'w-6 h-6 fill-current',
    'app': 'text-red',
    'app-border': 'border-gray-200 dark:border-dark-300',
  },
}

Sponsors
--------

License
-------

MIT License © 2021 Anthony Fu
