---
project: create-vue
stars: 4203
description: 🛠️ The recommended way to start a Vite-powered Vue project
url: https://github.com/vuejs/create-vue
---

create-vue
==========

The recommended way to start a Vite-powered Vue project

Usage
-----

To create a new Vue project using `create-vue`, simply run the following command in your terminal:

npm create vue@latest

Important

(`@latest` or `@legacy`) MUST NOT be omitted, otherwise `npm` may resolve to a cached and outdated version of the package.

By default, the command runs in interactive mode with prompts. You can skip these prompts by providing feature flags as CLI arguments. To see all available feature flags and options:

npm create vue@latest -- --help

This will show you various feature flags (like `--typescript`, `--router`) and options (like `--bare` for creating a project with minimal boilerplate).

**PowerShell users:** You'll need to quote the double dashes: `npm create vue@latest '--' --help`

### Creating Vue 2 Projects

If you need to support IE11, you can create a Vue 2 project with:

npm create vue@legacy

Warning

Vue 2 Has Reached End of Life

Difference from Vue CLI
-----------------------

-   Vite-Powered: Vue CLI is based on webpack, while `create-vue` is based on Vite. Vite supports most of the configured conventions found in Vue CLI projects out of the box, and provides a significantly better development experience due to its extremely fast startup and hot-module replacement speed. Learn more about why we recommend Vite over webpack here.
    
-   Scaffolding Tool: Unlike Vue CLI, `create-vue` itself is just a scaffolding tool. It creates a pre-configured project based on the features you choose, and delegates the rest to Vite. Projects scaffolded this way can directly leverage the Vite plugin ecosystem which is Rollup-compatible.
    

Migrating from Vue CLI
----------------------

If you're transitioning from Vue CLI to Create Vue, we've got you covered. Here are some resources to help you with the migration: How to Migrate from Vue CLI to Vite

-   Vue CLI to Vite Migration Guide: A comprehensive guide on migrating from Vue CLI to Vite, available on VueSchool.io
-   Tools and Plugins for Migration: For a smoother transition, check out the list of tools and plugins designed to assist with the migration process on the Awesome Vite GitHub page.
