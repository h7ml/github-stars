---
project: query-templates
stars: 9
description: query templates based on swagger-typescript-api for @tanstack/query
url: https://github.com/croatialu/query-templates
---

query-templates
===============

useQuery code generation template based on swagger-typescript-api and @tanstack/query

Install
-------

pnpm i @croatialu/query-templates -D

Usage
-----

### Script

generateApi({
  input: resolve(process.cwd(), 'swagger.json'),
  output: resolve(process.cwd(), '\_\_generated\_\_/api'),
  name: 'api',
  modular: true,
  typePrefix: 'Type',
  templates: resolve(process.cwd(), 'templates/modular'),
  extraTemplates: \[
    // change the template file name
    {
      name: 'Queries',
      // change the template file path
      path: resolve(process.cwd(), 'node\_modules/@croatialu/query-templates/dist/vue-query.ejs'),
    },
  \],
})

### Vite

# install vite plugin
pnpm i vite-plugin-swagger-typescript-api -D

// vite.config.ts
import { vitePluginSwaggerTypescriptApi } from 'vite-plugin-swagger-typescript-api'

export default defineConfig({
  plugins: \[
    // ...
    vitePluginSwaggerTypescriptApi({
      // ...
      extraTemplates: \[
        // change the template file name
        {
          name: 'Queries',
          // change the template file path
          path: resolve(process.cwd(), 'node\_modules/@croatialu/query-templates/dist/vue-query.ejs'),
        },
      \],
      // ...
    }),
    // ...
  \],
})

Features
--------

-   Automatically generate the queryKey creator
-   Automatically encapsulate api requests into useQuery and useMutation.
-   Typescript type hint in setQueryData

template

react-query

vue-query

default

✅ react-query.ejs

✅ vue-query.ejs

modular

✅ react-query-modular.ejs

✅ vue-query-modular.ejs

Usage
-----

`default` template

import { createApiQuery } from '../../\_\_generated\_\_/api-react-default/Queries'
import { Api } from '../../\_\_generated\_\_/api-react-default/api'

const api \= new Api()

const apiQuery \= createApiQuery(api)

const { data: \_data } \= apiQuery.pet.useFindPetsByStatus({
  //            ^?  AxiosResponse<TypePet\[\], void>> | undefined
  query: {
    status: \['sold'\],
  //  ^? ("available" | "pending" | "sold")\[\]
  },
})

const petQueryUpdate \= apiQuery.pet.useQueryUpdate()

petQueryUpdate(
  apiQuery.pet.createFindPetsByStatusQueryKey({
    query: {
      status: \['sold'\],
    //  ^? ("available" | "pending" | "sold")\[\]
    },
  }),
  (oldValue) \=> {
    // ^? AxiosResponse<TypePet\[\], void>
    return oldValue
  },
)

const mutation \= apiQuery.store.usePlaceOrderMutation(
  {
    onSuccess(\_data, { body: \_body }) {
      //                ^? TypeOrder
      //        ^? AxiosResponse<TypeOrder>
    },
  },
)

mutation.mutateAsync({
  body: {},
  // ^? TypeOrder
})

`modular` template

import { createPetApiQuery, createStoreApiQuery, usePetApiQueryUpdate } from '../../\_\_generated\_\_/api-react-modular/Queries'
import { Store } from '../../\_\_generated\_\_/api-react-modular/Store'
import { Pet } from '../../\_\_generated\_\_/api-react-modular/Pet'

const petApi \= new Pet()

const petQuery \= createPetApiQuery(petApi)

const { data: \_data } \= petQuery.useFindPetsByStatus({
  //            ^? AxiosResponse<TypePet\[\], void> | undefined
  query: {
    status: \['sold'\],
  //  ^? ("available" | "pending" | "sold")\[\]
  },
})

const petQueryUpdate \= usePetApiQueryUpdate()

petQueryUpdate(
  petQuery.createFindPetsByStatusQueryKey({
    query: {
      status: \['sold'\],
    //  ^? ("available" | "pending" | "sold")\[\]
    },
  }),
  (oldValue) \=> {
    // ^? AxiosResponse<TypePet\[\], void>
    return oldValue
  },
)

const storeApi \= new Store()
const storeQuery \= createStoreApiQuery(storeApi)
const mutation \= storeQuery.usePlaceOrderMutation(
  {
    onSuccess(\_data, { body: \_body }) {
      //                ^? TypeOrder
      //        ^? AxiosResponse<TypeOrder, void>
    },
  },
)

mutation.mutateAsync({
  body: {},
  // ^? TypeOrder
})

### Install

pnpm i swagger-typescript-api -D

### Copy template

Download the template to your project

# default template
npx dgit --ref main croatialu/query-templates/templates/default ./templates

# or modular template
npx dgit --ref main croatialu/query-templates/templates/modular ./templates

### Create script file (modular)

// scripts/gen-api/index.mjs

import { resolve } from 'node:path'
import process from 'node:process'
import { generateApi } from 'swagger-typescript-api'

generateApi({
  input: resolve(process.cwd(), 'swagger.json'),
  output: resolve(process.cwd(), '\_\_generated\_\_/api'),
  name: 'api',
  modular: true,
  typePrefix: 'Type',
  templates: resolve(process.cwd(), 'templates/modular'),
  extraTemplates: \[
    {
      name: 'Queries',
      path: resolve(process.cwd(), 'templates/modular/vue-query.ejs'),
    },
  \],
})

### Generate ts file

node ./scripts/gen-api/index.mjs

Setup
-----

pnpm install

pnpm start

Thanks
------

-   acacode/swagger-typescript-api
-   @tanstack/query
-   antfu/starter-ts
