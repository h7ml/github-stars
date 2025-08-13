---
project: vscode-goto-alias
stars: 265
description: Go to Definition following alias redirections.
url: https://github.com/antfu/vscode-goto-alias
---

vscode-goto-alias
=================

Go to Definition following alias redirections.

  

Usages
------

Install this extension from the VS Code Marketplace.

Set `editor.gotoLocation.multipleDefinitions` to `goto` in your VS Code settings for the best experience.

{
  "editor.gotoLocation.multipleDefinitions": "goto"
}

Motivation
----------

For example, in Nuxt 3 or Vitesse projects, we provide auto import for APIs and components. To provide types for these auto imports, the tools will generate a `.d.ts` file to declare those APIs as "global" type.

// generated.d.ts
declare global {
  const autoImported: typeof import('foobar')\['autoImported'\] // alias to provide type from package 'foobar'
  // ...
}

With this declaration file, we could have type safety using `autoImported` in our code without importing it.

// no need to import
const foo \= autoImported()

The only small downside is that when you use "Go to definition" in the code, the IDE will redirect you the the definition file we generated instead of the real definition source.

So, this extension is built to solve this. With this extension installed, when the "Go to definition" command hits the definition file, it will then redirect again to the definition source.

### Working with Vue Components

If you find trouble redirecting auto-registed components by Nuxt 3 or `unplugin-vue-components`, you might want to enable the Takeover mode of Volar.

Sponsors
--------

License
-------

MIT License © 2022 Anthony Fu
