---
project: electron-app
stars: 716
description: 💅 An Electron app boilerplate with React 19, TypeScript 5, Tailwind 4, shadcn/ui, Electron Vite, Biome, GitHub Action releases and more.
url: https://github.com/daltonmenezes/electron-app
---

Electron App
============

💅 An Electron app boilerplate with React v19, TypeScript v5, Tailwind v4, shadcn/ui, Electron Vite, Biome, **GitHub Action releases** and more.  
  

Features
========

-   **Stands out**
    -   🔥 Fast and Ready-to-go with a well-thought-out structure
    -   🚀 Auto reload for main and **Fast Refresh** for renderer process
    -   🎉 Window/Screen routing included
    -   😎 Preload (context bridge) already configured
    -   🔮 GitHub Action releases with `Windows`, `Mac` and `Linux` binaries
    -   🔒 Source Code Protection support
    -   🍪 Absolute paths support
-   **Technologies**:
    -   🔋 Electron
    -   🔥 ReactJS v19
    -   🌎 React Router DOM v7 and Electron Router DOM v2
    -   🧐 React Developer Tools
    -   🔍 Code inspector (holding `Alt` or `Option` key on DOM element and clicking on it)
    -   💙 TypeScript v5
    -   📦 Electron Vite
    -   ✨ TailwindCSS v4
    -   🎨 shadcn/ui
    -   🍦 lucide-icons
    -   💫 Biome / EditorConfig
    -   📦 Electron Builder
    -   🔮 action-electron-builder

  

> ⚠️ If **Windows 7** and **8** support is important for your project, you should know that Electron in a version greater than 22x no longer supports it. You can read more about it here. Therefore, you must downgrade Electron to 22x version if it's important for you!

Requirements
============

-   Node.js 20
-   pnpm 10

Installation
============

npx degit daltonmenezes/electron-app/template project\_name

cd project\_name
pnpm install
pnpm dev

Now, look at the **package.json** file in the root directory, you should update some of that settings with your project branding.

Adding new dependencies
=======================

For security reasons, **pnpm** has the onlyBuiltDependenciesFile property where only dependencies listed in the trusted-dependencies-scripts.json file can perform the postscripts execution. So, if you want to add a new dependency that needs to run a postscript, you should add it to the trusted-dependencies-scripts.json file list.

Distribution
============

Note

this section refers to local distribution, to release your app from GitHub Actions, see Releasing section.

### For all platforms

> **Note**: Check Electron Builder docs for more knowledge

```
pnpm build
```

### For a specific one

pnpm build --mac
# OR
pnpm build --win
# OR
pnpm build --linux

The builded apps will be available in the `dist` folder.

Documents
=========

Routing

Structure Overview

Source Code Protection

Releasing

Running released unsigend apps

FAQ - Frequently Asked Questions

Contributing
============

> **Note**: contributions are always welcome, but always **ask first**, — please — before work on a PR.

That said, there's a bunch of ways you can contribute to this project, like by:

-   🪲 Reporting a bug
-   📄 Improving this documentation
-   🚨 Sharing this project and recommending it to your friends
-   💵 Supporting this project on GitHub Sponsors or Patreon
-   🌟 Giving a star on this repository

License
=======

MIT © Dalton Menezes
