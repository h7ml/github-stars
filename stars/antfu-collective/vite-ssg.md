---
project: vite-ssg
stars: 1495
description: Static site generation for Vue 3 on Vite
url: https://github.com/antfu-collective/vite-ssg
---

Vite SSG
========

Static-site generation for Vue 3 on Vite.

> ℹ️ **ESM-only from `v27.0.0` (CJS generation format also dropped).**
> 
> ℹ️ **Vite 2 is supported from `v0.2.x`, Vite 1's support is discontinued.**

Install
-------

> **This library requires Node.js version >= 14**

**npm i -D vite-ssg** _vue-router @unhead/vue_

// package.json
{
  "scripts": {
    "dev": "vite",
\-   "build": "vite build"
+   "build": "vite-ssg build"

    // OR if you want to use another vite config file
+   "build": "vite-ssg build -c another-vite.config.ts"
  }
}

// src/main.ts
import { ViteSSG } from 'vite-ssg'
import App from './App.vue'

// \`export const createApp\` is required instead of the original \`createApp(App).mount('#app')\`
export const createApp \= ViteSSG(
  // the root component
  App,
  // vue-router options
  { routes },
  // function to have custom setups
  ({ app, router, routes, isClient, initialState }) \=> {
    // install plugins etc.
  },
)

### How to allow Rollup tree-shake your client code

In order to allow Rollup tree-shake your client code at build time, you need to wrap your code using `import.meta.env.SSR`, that's, checking if the build is for the server: Rollup will remove the server code from the client build.

if (import.meta.env.SSR) {
  // your server code will be removed in the client build
}
else {
  // your client code will be removed in the server build
}

### Single Page SSG

For SSG of an index page only (i.e. without `vue-router`); import `vite-ssg/single-page` instead, and only install `@unhead/vue` (`npm i -D vite-ssg @unhead/vue`).

// src/main.ts
import { ViteSSG } from 'vite-ssg/single-page'
import App from './App.vue'

// \`export const createApp\` is required instead of the original \`createApp(App).mount('#app')\`
export const createApp \= ViteSSG(App)

### `<ClientOnly/>`

The `ClientOnly` component is registered globally when the app is created.

<client-only\>
  <your-client-side-components />
  <template #placeholder\>
    <your-placeholder-components />
  </template\>
</client-only\>

Document head
-------------

We ship `@unhead/vue v2` to manage the document-head out of the box. You can use it directly in your pages/components. For example:

<template\>
  <button @click\="count++"\>Click</button\>
</template\>

<script setup\>
import { useHead } from '@unhead/vue'

useHead({
  title: 'Website Title',
  meta: \[
    {
      name: 'description',
      content: 'Website description',
    },
  \],
})
</script\>

That's all! No configuration is needed. Vite SSG will automatically handle the server-side rendering and merging.

See `@unhead/vue v2`'s docs for more usage information about `useHead`.

Critical CSS
------------

Vite SSG has built-in support for generating Critical CSS inlined in the HTML via the `beasties` package. Install it with:

npm i -D beasties

Critical CSS generation will automatically be enabled for you.

To configure `beasties`, pass its options into `ssgOptions.beastiesOptions` in `vite.config.ts`:

// vite.config.ts
export default defineConfig({
  ssgOptions: {
    beastiesOptions: {
      // E.g., change the preload strategy
      preload: 'media',
      // Other options: https://github.com/danielroe/beasties#usage
    },
  },
})

Initial State
-------------

The initial state comprises data that is serialized with your server-side generated HTML and is hydrated in the browser when accessed. This data can be data fetched from a CDN, an API, etc, and is typically needed as soon as the application starts or is accessed for the first time.

The main advantage of setting the application's initial state is that the statically generated pages do not need to refetch the data as it is fetched and serialized into the page's HTML at build time.

The initial state is a plain JavaScript object that can be set during SSR. I.e. when statically generating the pages like this:

// src/main.ts

// ...

export const createApp \= ViteSSG(
  App,
  { routes },
  ({ app, router, routes, isClient, initialState }) \=> {
    // ...

    if (import.meta.env.SSR) {
      // Set initial state during server side
      initialState.data \= { cats: 2, dogs: 3 }
    }
    else {
      // Restore or read the initial state on the client side in the browser
      console.log(initialState.data) // => { cats: 2, dogs: 3 }
    }

    // ...
  },
)

Typically, you will use this with an application store, such as Vuex or Pinia. See below for examples:

When using Pinia

Following Pinia's guide, you will to adapt your `main.{ts,js}` file to look like this:

import { createPinia } from 'pinia'
import routes from 'virtual:generated-pages'
// main.ts
import { ViteSSG } from 'vite-ssg'

import App from './App.vue'
// use any store you configured that you need data from on start-up
import { useRootStore } from './store/root'

export const createApp \= ViteSSG(
  App,
  { routes },
  ({ app, router, initialState }) \=> {
    const pinia \= createPinia()
    app.use(pinia)

    if (import.meta.env.SSR)
      initialState.pinia \= pinia.state.value
    else
      pinia.state.value \= initialState.pinia || {}

    router.beforeEach((to, from, next) \=> {
      const store \= useRootStore(pinia)
      if (!store.ready)
        // perform the (user-implemented) store action to fill the store's state
        store.initialize()
      next()
    })
  },
)

When using Vuex

import routes from 'virtual:generated-pages'
// main.ts
import { ViteSSG } from 'vite-ssg'
import { createStore } from 'vuex'
import App from './App.vue'

// Normally, you should definitely put this in a separate file
// in order to be able to use it everywhere
const store \= createStore({
  // ...
})

export const createApp \= ViteSSG(
  App,
  { routes },
  ({ app, router, initialState }) \=> {
    app.use(store)

    if (import.meta.env.SSR)
      initialState.store \= store.state
    else
      store.replaceState(initialState.store)

    router.beforeEach((to, from, next) \=> {
      // perform the (user-implemented) store action to fill the store's state
      if (!store.getters.ready)
        store.dispatch('initialize')

      next()
    })
  },
)

For an example on how to use a store with an initial state in a single page app, see the single page example.

### State Serialization

By default, the state is deserialized and serialized by using `JSON.stringify` and `JSON.parse` respectively. If this approach works for you, you should definitely stick to it as it yields far better performance.

You may use the `transformState` option in the `ViteSSGClientOptions` options object as shown below. A valid approach besides `JSON.stringify` and `JSON.parse` is `@nuxt/devalue` (which is used by Nuxt.js):

import devalue from '@nuxt/devalue'
import { ViteSSG } from 'vite-ssg'

// ...
import App from './App.vue'

export const createApp \= ViteSSG(
  App,
  { routes },
  ({ app, router, initialState }) \=> {
    // ...
  },
  {
    transformState(state) {
      return import.meta.env.SSR ? devalue(state) : state
    },
  },
)

**A minor remark when using `@nuxt/devalue`:** In case, you are getting an error because of a `require` within the package `@nuxt/devalue`, you have to add the following piece of config to your Vite config:

// vite.config.ts
// ...

export default defineConfig({
  resolve: {
    alias: {
      '@nuxt/devalue': '@nuxt/devalue/dist/devalue.js',
    },
  },
  // ...
})

### Async Components

Some applications may make use of Vue features that cause components to render asynchronously (e.g. `suspense`). When these features are used in ways that can influence `initialState`, the `onSSRAppRendered` may be used in order to ensure that all async operations are complete during the initial application render. For example:

const { app, router, initialState, isClient, onSSRAppRendered } \= ctx

const pinia \= createPinia()
app.use(pinia)

if (import.meta.env.SSR) {
  onSSRAppRendered(() \=> {
    initialState.pinia \= pinia.state.value
  })
}
else {
  pinia.state.value \= (initialState.pinia) || {}
}

Configuration
-------------

You can pass options to Vite SSG in the `ssgOptions` field of your `vite.config.js`

// vite.config.js

export default {
  plugins: \[\],
  ssgOptions: {
    script: 'async',
  },
}

See src/types.ts. for more options available.

### Custom Routes to Render

You can use the `includedRoutes` hook to include or exclude route paths to render, or even provide some completely custom ones.

// vite.config.js

export default {
  plugins: \[\],
  ssgOptions: {
    includedRoutes(paths, routes) {
      // exclude all the route paths that contains 'foo'
      return paths.filter(i \=> !i.includes('foo'))
    },
  },
}

// vite.config.js

export default {
  plugins: \[\],
  ssgOptions: {
    includedRoutes(paths, routes) {
      // use original route records
      return routes.flatMap((route) \=> {
        return route.name \=== 'Blog'
          ? myBlogSlugs.map(slug \=> \`/blog/${slug}\`)
          : route.path
      })
    },
  },
}

Alternatively, you may export the `includedRoutes` hook from your server entry file. This will be necessary if fetching your routes requires the use of environment variables managed by Vite.

// main.ts

import { ViteSSG } from 'vite-ssg'
import App from './App.vue'

export const createApp \= ViteSSG(
  App,
  { routes },
  ({ app, router, initialState }) \=> {
    // ...
  },
)
export async function includedRoutes(paths, routes) {
  // Sensitive key is managed by Vite - this would not be available inside
  // vite.config.js as it runs before the environment has been populated.
  const apiClient \= new MyApiClient(import.meta.env.MY\_API\_KEY)

  return Promise.all(
    routes.flatMap(async (route) \=> {
      return route.name \=== 'Blog'
        ? (await apiClient.fetchBlogSlugs()).map(slug \=> \`/blog/${slug}\`)
        : route.path
    }),
  )
}

Comparison
----------

### Use Vitepress when you want:

-   Zero config, out of the box SSG
-   A single-purpose documentation site
-   Lightweight (No double payload)

### Use Vite SSG when you want:

-   More control on the build process and tooling
-   The flexible plugin system
-   Multi-purpose application with some SSG to improve SEO and loading speed

Cons:

-   Double payload

Example
-------

See Vitesse.

Thanks to the prior work
------------------------

-   vitepress
-   vue3-vite-ssr-example
-   vite-ssr

Contribution
------------

Please refer to https://github.com/antfu/contribute.

License
-------

MIT License © 2020-PRESENT Anthony Fu
