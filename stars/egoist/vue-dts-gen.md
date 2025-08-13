---
project: vue-dts-gen
stars: 218
description: Generate `d.ts` from `.vue` files.
url: https://github.com/egoist/vue-dts-gen
---

Please use vue-tsc instead: `vue-tsc --declaration --emitDeclarationOnly`
=========================================================================

**💛 You can help the author become a full-time open-source maintainer by sponsoring him on GitHub.**

* * *

vue-dts-gen
===========

Generate `d.ts` from `.vue` files.

Install
-------

Globally:

npm i -g vue-dts-gen

Or locally:

```
npm i -D vue-dts-gen
```

Usage
-----

Output directory is determined by `outDir` in `tsconfig.json`.

Assuming the `outDir` is `dist`:

vue-dts-gen src/App.vue
# Emits dist/App.d.ts

# Or glob patterns
vue-dts-gen "src/\*.{ts,vue}"
# Emits dist/\*.d.ts

Only `d.ts` files are emitted.

Example
-------

**Input:**

<script lang="ts">
import { defineComponent } from 'vue'
export default defineComponent({
  props: {
    /\*\* Initial number \*/
    start: {
      type: Number,
      required: true,
    },
  },
})
</script\>

**Output:**

declare const \_default: import("vue").DefineComponent<{
    /\*\* Initial number \*/
    start: {
        type: NumberConstructor;
        required: true;
    };
}, unknown, unknown, {}, {}, import("vue").ComponentOptionsMixin, import("vue").ComponentOptionsMixin, Record<string, any\>, string, import("vue").VNodeProps & import("vue").AllowedComponentProps & import("vue").ComponentCustomProps, Readonly<{
    start: number;
} & {}\>, {}\>;
export default \_default;

**Input:**

<template\>
  <div\>hi</div\>
</template\>

<script lang="ts" setup>
import { defineProps } from 'vue'
defineProps<{
  /\*\* The initial number \*/
  start: number
}>()
</script\>

**Output**:

declare const \_default: import("vue").DefineComponent<{
    /\*\* The initial number \*/
    start: number;
}, {}, {}, {}, {}, import("vue").ComponentOptionsMixin, import("vue").ComponentOptionsMixin, import("vue").EmitsOptions, string, import("vue").VNodeProps & import("vue").AllowedComponentProps & import("vue").ComponentCustomProps, Readonly<{} & {
    start?: number | undefined;
}\>, {}\>;
export default \_default;

License
-------

MIT © EGOIST
