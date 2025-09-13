---
project: vitesse
stars: 9298
description: 🏕 Opinionated Vite + Vue Starter Template
url: https://github.com/antfu-collective/vitesse
---

Mocking up web app with **Vitesse**_(speed)_  

  

Live Demo

  

> **Note**: This template is created during the early transition of Vue 3 and Vite. At this moment, if you are seeking for better Vue developer experience and more consistent maintenance, we recommend using Nuxt instead (it also works perfectly with SPA or SSG as needed). This template still serves as a reference, but expect slower updates.

  

**English** | 简体中文

  

Features
--------

-   ⚡️ Vue 3, Vite, pnpm, esbuild - born with fastness
    
-   🗂 File based routing
    
-   📦 Components auto importing
    
-   🍍 State Management via Pinia
    
-   📑 Layout system
    
-   📲 PWA
    
-   🎨 UnoCSS - the instant on-demand atomic CSS engine
    
-   😃 Use icons from any icon sets with classes
    
-   🌍 I18n ready
    
-   🔎 Component Preview
    
-   🗒 Markdown Support
    
-   🔥 Use the new `<script setup>` syntax
    
-   📥 APIs auto importing - use Composition API and others directly
    
-   🖨 Static-site generation (SSG) via vite-ssg
    
-   🦔 Critical CSS via beasties
    
-   🦾 TypeScript, of course
    
-   ⚙️ Unit Testing with Vitest, E2E Testing with Cypress on GitHub Actions
    
-   ☁️ Deploy on Netlify, zero-config
    

  

Pre-packed
----------

### UI Frameworks

-   UnoCSS - The instant on-demand atomic CSS engine.

### Icons

-   Iconify - use icons from any icon sets 🔍Icônes
-   Pure CSS Icons via UnoCSS

### Plugins

-   Vue Router
    -   `unplugin-vue-router` - file system based routing
    -   `vite-plugin-vue-layouts` - layouts for pages
-   Pinia - Intuitive, type safe, light and flexible Store for Vue using the composition api
-   `unplugin-vue-components` - components auto import
-   `unplugin-auto-import` - Directly use Vue Composition API and others without importing
-   `unplugin-vue-macros` - Explore and extend more macros and syntax sugar to Vue.
-   `vite-plugin-pwa` - PWA
-   `unplugin-vue-markdown` - Markdown as components / components in Markdown
    -   `@shikijs/markdown-it` - Shiki for syntax highlighting
-   Vue I18n - Internationalization
    -   `unplugin-vue-i18n` - unplugin for Vue I18n
-   VueUse - collection of useful composition APIs
-   `vite-ssg-sitemap` - Sitemap generator
-   `@unhead/vue v2` - manipulate document head reactively
-   `vite-plugin-vue-devtools` - Designed to enhance the Vue developer experience.

### Coding Style

-   Use Composition API with `<script setup>` SFC syntax
-   ESLint with @antfu/eslint-config, single quotes, no semi.

### Dev tools

-   TypeScript
-   Vitest - Unit testing powered by Vite
-   Cypress - E2E testing
-   pnpm - fast, disk space efficient package manager
-   `vite-ssg` - Static-site generation
    -   beasties - Critical CSS
-   Netlify - zero-config deployment
-   VS Code Extensions
    -   Vite - Fire up Vite server automatically
    -   Volar - Vue 3 `<script setup>` IDE support
    -   Iconify IntelliSense - Icon inline display and autocomplete
    -   i18n Ally - All in one i18n support
    -   ESLint

Variations
----------

As this template is strongly opinionated, the following provides a curated list for community-maintained variations with different preferences and feature sets. Check them out as well. PR to add yours is also welcome!

###### Official

-   vitesse-lite - Lightweight version of Vitesse
-   vitesse-nuxt3 - Vitesse for Nuxt 3
-   vitesse-nuxt-bridge - Vitesse for Nuxt 2 with Bridge
-   vitesse-webext - WebExtension Vite starter template

###### Community

-   vitesse-ssr-template by @frandiox - Vitesse with SSR
-   vitailse by @zynth17 - Like Vitesse but with TailwindCSS
-   vitesse-modernized-chrome-ext by @xiaoluoboding - ⚡️ Modernized Chrome Extension Manifest V3 Vite Starter Template
-   vitesse-stackter-clean-architect by @shamscorner - A modular clean architecture pattern in vitesse template
-   vitesse-enterprise by @FranciscoKloganB - Consistent coding styles regardless of team-size.
-   vitecamp by @nekobc1998923 - Like Vitesse but without SSG/SSR/File based routing, includes Element Plus
-   vitesse-h5 by @YunYouJun - Vitesse for Mobile
-   bat by @olgam4 - Vitesse for SolidJS
-   vitesse-solid by @xbmlz - Vitesse for SolidJS, build with `SolidStart`, includes UnoCSS and HopeUI.
-   vue3-vant-mobile by CharleeWa - Like Vitesse but without SSG/SSR, includes Vant

Try it now!
-----------

> Vitesse requires Node >=14.18

### GitHub Template

Create a repo from this template on GitHub.

### Clone to local

If you prefer to do it manually with the cleaner git history

npx degit antfu-collective/vitesse my-vitesse-app
cd my-vitesse-app
pnpm i # If you don't have pnpm installed, run: npm install -g pnpm

Checklist
---------

When you use this template, try follow the checklist to update your info properly

-   Change the author name in `LICENSE`
-   Change the title in `App.vue`
-   Change the hostname in `vite.config.ts`
-   Change the favicon in `public`
-   Remove the `.github` folder which contains the funding info
-   Clean up the READMEs and remove routes

And, enjoy :)

Usage
-----

### Development

Just run and visit http://localhost:3333

pnpm dev

### Build

To build the App, run

pnpm build

And you will see the generated file in `dist` that ready to be served.

### Deploy on Netlify

Go to Netlify and select your clone, `OK` along the way, and your App will be live in a minute.

### Docker Production Build

First, build the vitesse image by opening the terminal in the project's root directory.

docker buildx build . -t vitesse:latest

Run the image and specify port mapping with the `-p` flag.

docker run --rm -it -p 8080:80 vitesse:latest

Why
---

I have created several Vite apps recently. Setting the configs up is kinda the bottleneck for me to make the ideas simply come true within a very short time.

So I made this starter template for myself to create apps more easily, along with some good practices that I have learned from making those apps. It's strongly opinionated, but feel free to tweak it or even maintain your own forks. (see community maintained variation forks)
