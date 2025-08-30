---
project: vue-cli-plugin-tailwind
stars: 208
description: vue-cli plugin for Tailwind CSS
url: https://github.com/forsartis/vue-cli-plugin-tailwind
---

vue-cli-plugin-tailwind
=======================

A plugin that adds Tailwind CSS to your vue-cli project.

Getting started
---------------

Inside your vue-cli project folder add the plugin via:

```
vue add tailwind
```

Choose what Tailwind config you want to generate:

-   **none** - Won't create a config file. Useful if you already have a config (make sure to configure PurgeCSS).
-   **minimal** _(default)_ - Will create a minimal `tailwind.config.js` file where you can define your customizations.
-   **full** - Will generate a `tailwind.config.js` file containing the entire default configuration.

See Tailwinds configuration guide for more info.

PostCSS Configuration
---------------------

Tailwind CSS will be added as plugins in your PostCSS config.

// postcss.config.js
module.exports \= {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
};

License
-------

MIT
