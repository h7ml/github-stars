---
project: vite-plugin-pages
stars: 2029
description: File system based route generator for ⚡️Vite
url: https://github.com/hannoeru/vite-plugin-pages
---

vite-plugin-pages
=================

> File system based routing for Vue 3 / React / Solid applications using Vite

Getting Started
---------------

### Vue

**🚨Important Notes🚨**

We recommend that Vue users use unplugin-vue-router instead of this plugin.

unplugin-vue-router is a unplugin library created by @posva, same auther as vue-router. It provide almost same feature as vite-plugin-pages but better intergration with vue-router, include some cool feature like auto generate route types base on your route files to provide autocomplete for vue-router.

#### Install:

npm install -D vite-plugin-pages
npm install vue-router

### React

> since v0.19.0 we only support react-router v6, if you are using react-router v5 use v0.18.2.

#### Install:

npm install -D vite-plugin-pages
npm install react-router react-router-dom

### Solid

#### Install:

npm install -D vite-plugin-pages
npm install @solidjs/router

### Vite config

Add to your `vite.config.js`:

import Pages from 'vite-plugin-pages'

export default {
  plugins: \[
    // ...
    Pages(),
  \],
}

Overview
--------

By default a page is a Vue component exported from a `.vue` or `.js` file in the `src/pages` directory.

You can access the generated routes by importing the `~pages` module in your application.

### Vue

import { createRouter } from 'vue-router'
import routes from '~pages'

const router \= createRouter({
  // ...
  routes,
})

**Type**

// vite-env.d.ts
/// <reference types="vite-plugin-pages/client" />

### React

**experimental**

import { StrictMode, Suspense } from 'react'
import { createRoot } from 'react-dom/client'
import {
  BrowserRouter,
  useRoutes,
} from 'react-router-dom'

import routes from '~react-pages'

function App() {
  return (
    <Suspense fallback\={<p\>Loading...</p\>}\>
      {useRoutes(routes)}
    </Suspense\>
  )
}

const app \= createRoot(document.getElementById('root')!)

app.render(
  <StrictMode\>
    <BrowserRouter\>
      <App />
    </BrowserRouter\>
  </StrictMode\>,
)

**Type**

// vite-env.d.ts
/// <reference types="vite-plugin-pages/client-react" />

### Solid

#### Passing routes to solid-router

This guide is for solid-router v0.10.x and newer. For older versions see the migration guide.

import { Router } from '@solidjs/router'
import { render } from 'solid-js/web'
import routes from '~solid-pages'

render(
  () \=> {
    return (
      <Router
        root\={props \=> (
          <Suspense\>
            {props.children}
          </Suspense\>
        )}
      \>
        {routes}
      </Router\>
    )
  },
  document.getElementById('root') as HTMLElement,
)

#### Configuring vite-plugin with SolidJS

Remember to check the `dirs` is set to the correct routes directory in `vite.config.ts`:

import { defineConfig } from 'vite'
import Pages from 'vite-plugin-pages'
import solidPlugin from 'vite-plugin-solid'

export default defineConfig({
  plugins: \[
    Pages({
      dirs: \['src/pages'\],
    }),
    solidPlugin()
  \],
})

**Type**

// vite-env.d.ts
/// <reference types="vite-plugin-pages/client-solid" />

Configuration
-------------

To use custom configuration, pass your options to Pages when instantiating the plugin:

// vite.config.js
import Pages from 'vite-plugin-pages'

export default {
  plugins: \[
    Pages({
      dirs: 'src/views',
    }),
  \],
}

### dirs

-   **Type:** `string | (string | PageOptions)[]`
-   **Default:** `'src/pages'`

Paths to the pages directory. Supports globs.

Can be:

-   single path: routes point to `/`
-   array of paths: all routes in the paths point to `/`
-   array of `PageOptions`, Check below 👇

interface PageOptions {
  /\*\*
   \* Page base directory.
   \* @default 'src/pages'
   \*/
  dir: string
  /\*\*
   \* Page base route.
   \*/
  baseRoute: string
  /\*\*
   \* Page file pattern.
   \* @example \`\*\*\\/\*.page.vue\`
   \*/
  filePattern?: string
}

Specifying a glob or an array of `PageOptions` allow you to use multiple pages folder, and specify the base route to append to the path and the route name.

Additionally, you can specify a `filePattern` to filter the files that will be used as pages.

#### Example

Folder structure

src/
  ├── features/
  │  └── dashboard/
  │     ├── code/
  │     ├── components/
  │     └── pages/
  ├── admin/
  │   ├── code/
  │   ├── components/
  │   └── pages/
  └── pages/

Config

// vite.config.js
export default {
  plugins: \[
    Pages({
      dirs: \[
        // basic
        { dir: 'src/pages', baseRoute: '' },
        // features dir for pages
        { dir: 'src/features/\*\*/pages', baseRoute: 'features' },
        // with custom file pattern
        { dir: 'src/admin/pages', baseRoute: 'admin', filePattern: '\*\*/\*.page.\*' },
      \],
    }),
  \],
}

### extensions

-   **Type:** `string[]`
-   **Default:**
    -   Vue: `['vue', 'ts', 'js']`
    -   React: `['tsx', 'jsx', 'ts', 'js']`
    -   Solid: `['tsx', 'jsx', 'ts', 'js']`

An array of valid file extensions for pages. If multiple extensions match for a file, the first one is used.

### exclude

-   **Type:** `string[]`
-   **Default:** `[]`

An array of glob patterns to exclude matches.

# folder structure
src/pages/
  ├── users/
  │  ├── components
  │  │  └── form.vue
  │  ├── \[id\].vue
  │  └── index.vue
  └── home.vue

// vite.config.js
export default {
  plugins: \[
    Pages({
      exclude: \['\*\*/components/\*.vue'\],
    }),
  \],
}

### importMode

-   **Type:** `'sync' | 'async' | (filepath: string, pluginOptions: ResolvedOptions) => 'sync' | 'async')`
-   **Default:**
    -   Top level index file: `'sync'`, others: `async`.

Import mode can be set to either `async`, `sync`, or a function which returns one of those values.

To get more fine-grained control over which routes are loaded sync/async, you can use a function to resolve the value based on the route path. For example:

// vite.config.js
export default {
  plugins: \[
    Pages({
      importMode(filepath, options) {
        // default resolver
        // for (const page of options.dirs) {
        //   if (page.baseRoute === '' && filepath.startsWith(\`/${page.dir}/index\`))
        //     return 'sync'
        // }
        // return 'async'

        // Load about page synchronously, all other pages are async.
        return filepath.includes('about') ? 'sync' : 'async'
      },
    }),
  \],
}

If you are using `async` mode with `react-router`, you will need to wrap your route components with `Suspense`:

function App() {
  return (
    <Suspense fallback\={<p\>Loading...</p\>}\>
      {useRoutes(routes)}
    </Suspense\>
  )
}

### importPath

-   **Type:** `'absolute' | 'relative'`
-   **Default:** `'relative'`

Import page components from absolute or relative paths. The default behavior is to import from relative paths, but in some special cases, it can be set to `'absolute'` to import from absolute paths.

For example, if your page components are located in the `app/pages` directory and you have set `base: /app/` in your `vite.config.js`, you should set `importPath` to `'absolute'` in order to correctly import the page components.

// vite.config.js
export default {
  base: '/app/',
  plugins: \[
    Pages({
      dirs: 'app/pages',

      // It should be set to 'absolute' in this case.
      importPath: 'absolute',
    }),
  \],
}

See #492 for more details.

### routeBlockLang

-   **Type:** `string`
-   **Default:** `'json5'`

Default SFC route block parser.

### routeStyle

-   **Type:** `'next' | 'nuxt' | 'remix'`
-   **Default:** `next`

Use file system dynamic routing supporting:

-   Nextjs Routing
-   Nuxtjs Routing
-   Remix Routing

### routeNameSeparator

-   **Type:** `string`
-   **Default:** `-`

Separator for generated route names.

### resolver

-   **Type:** `'vue' | 'react' | 'solid' | PageResolver`
-   **Default:** `'auto detect'`

Route resolver, support `vue`, `react`, `solid` or custom `PageResolver`.

### moduleId

-   **Type:** `string`
-   **Default:**
    -   Vue: `'~pages'`
    -   React: `'~react-pages'`
    -   Solid: `'~solid-pages'`

Module id for routes import, useful when you what to use multiple pages plugin in one project.

### extendRoute

-   **Type:** `(route: any, parent: any | undefined) => any | void`

A function that takes a route and optionally returns a modified route. This is useful for augmenting your routes with extra data (e.g. route metadata).

// vite.config.js
export default {
  // ...
  plugins: \[
    Pages({
      extendRoute(route, parent) {
        if (route.path \=== '/') {
          // Index is unauthenticated.
          return route
        }

        // Augment the route with meta that indicates that the route requires authentication.
        return {
          ...route,
          meta: { auth: true },
        }
      },
    }),
  \],
}

### onRoutesGenerated

-   **Type:** `(routes: any[]) => Awaitable<any[] | void>`

A function that takes a generated routes and optionally returns a modified generated routes.

### onClientGenerated

-   **Type:** `(clientCode: string) => Awaitable<string | void>`

A function that takes a generated client code and optionally returns a modified generated client code.

### SFC custom block for Route Data

Add route meta to the route by adding a `<route>` block to the SFC. This will be directly added to the route after it is generated, and will override it.

You can specific a parser to use using `<route lang="yaml">`, or set a default parser using `routeBlockLang` option.

-   **Supported parser:** JSON, JSON5, YAML
-   **Default:** JSON5

JSON/JSON5:

<route\>
{
  name: "name-override",
  meta: {
    requiresAuth: false
  }
}
</route\>

YAML:

<route lang\="yaml"\>
name: name-override
meta:
  requiresAuth: true
</route\>

#### Syntax Highlighting `<route>`

To enable syntax highlighting `<route>` in VS Code using Vetur's Custom Code Blocks add the following snippet to your preferences...

1.  update setting

```
"vetur.grammar.customBlocks": {
   "route": "json"
 }
```

1.  Run the command in vscode

`Vetur: Generate grammar from vetur.grammar.customBlocks`

1.  Restart VS Code to get syntax highlighting for custom blocks.

### JSX/TSX YAML format comments for Route Data(In Vue)

Add route meta to the route by adding a comment block starts with `route` to the JSX or TSX file(In Vue). This will be directly added to the route after it is generated, and will override it.

This feature only support JSX/TSX in vue, and will parse only the first block of comments which should also start with `route`.

Now only `yaml` parser supported.

-   **Type:** `'vue'`
-   **Supported parser:** YAML

/\*
route
name: name-override
meta:
  requiresAuth: false
  id: 1234
  string: "1234"
\*/

File System Routing
-------------------

Inspired by the routing from NuxtJS 💚

Pages automatically generates an array of routes for you to plug-in to your instance of Vue Router. These routes are determined by the structure of the files in your pages directory. Simply create `.vue` files in your pages directory and routes will automatically be created for you, no additional configuration required!

For more advanced use cases, you can tailor Pages to fit the needs of your app through configuration.

-   Basic Routing
-   Index Routes
-   Dynamic Routes
-   Nested Routes
-   Catch-all Routes

### Basic Routing

Pages will automatically map files from your pages directory to a route with the same name:

-   `src/pages/users.vue` -> `/users`
-   `src/pages/users/profile.vue` -> `/users/profile`
-   `src/pages/settings.vue` -> `/settings`

### Index Routes

Files with the name `index` are treated as the index page of a route:

-   `src/pages/index.vue` -> `/`
-   `src/pages/users/index.vue` -> `/users`

### Dynamic Routes

Dynamic routes are denoted using square brackets. Both directories and pages can be dynamic:

-   `src/pages/users/[id].vue` -> `/users/:id` (`/users/one`)
-   `src/pages/[user]/settings.vue` -> `/:user/settings` (`/one/settings`)

Any dynamic parameters will be passed to the page as props. For example, given the file `src/pages/users/[id].vue`, the route `/users/abc` will be passed the following props:

{ "id": "abc" }

### Nested Routes

We can make use of Vue Routers child routes to create nested layouts. The parent component can be defined by giving it the same name as the directory that contains your child routes.

For example, this directory structure:

```
src/pages/
  ├── users/
  │  ├── [id].vue
  │  └── index.vue
  └── users.vue
```

will result in this routes configuration:

\[
  {
    "path": "/users",
    "component": "/src/pages/users.vue",
    "children": \[
      {
        "path": "",
        "component": "/src/pages/users/index.vue",
        "name": "users"
      },
      {
        "path": ":id",
        "component": "/src/pages/users/\[id\].vue",
        "name": "users-id"
      }
    \]
  }
\]

### Catch-all Routes

Catch-all routes are denoted with square brackets containing an ellipsis:

-   `src/pages/[...all].vue` -> `/*` (`/non-existent-page`)

The text after the ellipsis will be used both to name the route, and as the name of the prop in which the route parameters are passed.

Sitemap generation
------------------

If you need to generate a sitemap from generated routes, you can use vite-plugin-pages-sitemap. This plugin allow you to automatically generate sitemap.xml and robots.xml files with customization.

License
-------

MIT License © 2021-PRESENT hannoeru
