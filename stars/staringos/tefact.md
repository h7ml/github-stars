---
project: tefact
stars: 346
description: 🏭 (Beta) 轻量级无代码/低代码 H5、表单编辑器。Lightweight no-code/low-code editor for website、H5 page and Form. Build your page without code! 
url: https://github.com/staringos/tefact
---

⚠️ Warning
==========

This project is not maintain. You can check our new version Low-Code Editor in staringos/mtbird  
这个项目将不在维护，您可以查看我们的新版本开源低代码编辑器 staringos/mtbird

  
  
  

Website | Usage | Documents | Example | Community | Support

  

Tefact
======

Lightweight no-code editor for `website`、`H5 page` and `Form`. Build your application without code!

\[中文文档\]

\[Example\]

Dependencies:

-   Vue 2.x
-   ElementUI
-   Sass

Getting Start
-------------

Recommend: Fork example project to getting start. or manually import:

1.  Install dependency:

yarn add @tefact/editor

1.  Import styles to your css or less file:

import "@tefact/editor/lib/index.css"

1.  Add `@tefact` package to your webpack transport.

`webpack.config.js` or `nuxt.config.js`

{
    "build": {
        "transpile": \[
          /@tefact\\/\*/
        \],
    }
}

1.  Import Editor to you.

<template\>
  <Editor
      :value\="target"
      :editorSetting\="editorSetting"
  ></Editor\>
</template\>
<script lang="ts">
import Vue from "vue";
import Editor, { getDefaultFeature } from "@tefact/editor";
export default Vue.extends({
  data() {
    return {
      target: getDefaultFeature("page"),
      editorSetting: {}
    }
  },
  components: {
    Editor
  }
})
</script\>

Core Concept
------------

### Target

Target is an object that we edit for. It can be a H5 Page / Form Page or website Page. It's a JSON data structure for descript how a Page for Form looks like.

You can use `getDefaultFeature` in `@tefact/editor` to generate default target data. And save it to somewhere, it can be used directly to `@tefact/feature-form` or `@tefact/feature-page`

### Editor

`@tefact/editor` is a Edit view for feature page or form.

#### Parameters

-   value: the edit target
-   editorSetting: Setting of editor

#### Event

-   addTarget: Add target within the editor
-   editTarget: after editor target basic information
-   share: toggle target share
-   save: When save target
-   back: When editor within the editor back toggle

### Page

`@tefact/feature-page` is a view component for those `target` has a `featureType = page`. To preview a page, you can do:

<template\>
  <Page :value\="target"\></Page\>
</template\>
<script lang="ts">
import Vue from "vue";
import Page, { DFFAULT } from "@tefact/feature-page";
export default Vue.extends({
  data() {
    return {
      target: DFFAULT
    }
  },
  components: {
    Page
  }
})
</script\>

### Form

Same like `page`, `@tefact/feature-form` is use for preview or display those target has a `featureType = form`, you can do:

<template\>
  <Form :value\="target"\></Form\>
</template\>
<script lang="ts">
import Vue from "vue";
import Form, { DFFAULT } from "@tefact/feature-page";
export default Vue.extends({
  data() {
    return {
      target: DFFAULT
    }
  },
  components: {
    Form
  }
})
</script\>

Contributing
------------

PRs & Issues are all welcome, feel free to ask question or submit your code.

CONTRIBUTING

### Join Community

Scan with wechat, join our group.

#### Discord
