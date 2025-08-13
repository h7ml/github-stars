---
project: vemix
stars: 21
description: Simple Vue SSR framework
url: https://github.com/yisar/vemix
---

venti
=====

Simple Vue SSR framework.

### Run

yarn dev

### Usage

<template\>
  <div\>{{ msg }}</div\>
</template\>
<script\>
import { useLoaderData } from 'venti'
import { computed } from 'vue'
export function loader() {
  return {
    msg: 'Hello world!',
  }
}
export default {
  setup() {
    const data \= useLoaderData()
    const msg \= computed(() \=> data.value.msg)
    return {
      msg,
    }
  },
}
</script\>
