---
project: chatmoss-open
stars: 2
description: chatmoss 开放平台
url: https://github.com/AICCOF/chatmoss-open
---

Vue 3 + TypeScript + Vite
=========================

This template should help get you started developing with Vue 3 and TypeScript in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the script setup docs to learn more.

Recommended IDE Setup
---------------------

-   VS Code + Volar (and disable Vetur) + TypeScript Vue Plugin (Volar).

Type Support For `.vue` Imports in TS
-------------------------------------

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need TypeScript Vue Plugin (Volar) to make the TypeScript language service aware of `.vue` types.

If the standalone TypeScript plugin doesn't feel fast enough to you, Volar has also implemented a Take Over Mode that is more performant. You can enable it by the following steps:

1.  Disable the built-in TypeScript Extension
    1.  Run `Extensions: Show Built-in Extensions` from VSCode's command palette
    2.  Find `TypeScript and JavaScript Language Features`, right click and select `Disable (Workspace)`
2.  Reload the VSCode window by running `Developer: Reload Window` from the command palette.
