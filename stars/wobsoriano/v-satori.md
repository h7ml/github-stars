---
project: v-satori
stars: 39
description: Generate a satori-friendly VDOM from a Vue component
url: https://github.com/wobsoriano/v-satori
---

v-satori
========

Generate a satori\-friendly VDOM from a Vue component. Uses satori-html.

Installion
----------

npm install satori v-satori

Usage
-----

Nuxt 3

export default defineNuxtConfig({
  modules: \['v-satori/nuxt'\]
})

<script setup>
defineProps({
  title: String,
  website: String,
})
</script\>

<template\>
  <div tw\="h-full w-full flex items-start justify-start border border-blue-500 border-\[12px\] bg-gray-50"\>
    <div tw\="flex items-start justify-start h-full"\>
      <div tw\="flex flex-col justify-between w-full h-full'"\>
        <h1 tw\="text-\[80px\] p-20 font-black text-left"\>
          {{ title }}
        </h1\>
        <div tw\="text-2xl pb-10 px-20 font-bold mb-0"\>
          {{ website }}
        </div\>
      </div\>
    </div\>
  </div\>
</template\>

// server/api/og.ts

import { satori } from 'v-satori'
import Image from '@/components/Image.vue'
// https://github.com/wobsoriano/unplugin-font-to-buffer
import Roboto from '@/lib/fonts/Roboto-Regular.ttf'

export default eventHandler(async (event) \=> {
  const query \= getQuery(event)

  const svg \= await satori(Image, {
    props: {
      title: query.title,
      website: query.website
    },
    width: 1200,
    height: 630,
    fonts: \[{
      name: 'Roboto',
      data: Roboto,
      weight: 400,
      style: 'normal',
    }\]
  })

  setHeader(event, 'Content-Type', 'image/svg+xml')

  return svg
})

You can then create new dynamic images by passing the following parameters to the API endpoint:

<script setup>
const title \= 'OG Image Generator using Nuxt and Satori'
const website \= 'v3.nuxtjs.org'
</script\>

<template\>
  <Head\>
    <Meta property\="og:image" :content\="\`/api/og?title=${title}&website=${website}\`" />
  </Head\>
</template\>

Output:

License
-------

MIT
