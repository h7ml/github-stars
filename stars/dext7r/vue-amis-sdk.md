---
project: vue-amis-sdk
stars: 38
description: 基于amis-editor封装的vue版本，支持vue2，vue3
url: https://github.com/dext7r/vue-amis-sdk
---

vue-amis-sdk
============

about
-----

-   This project is based on vuera and mainly focuses on the encapsulation of amis-editor
-   You can edit at this. The proxy mode is enabled. You can copy the JSON of amis. It supports direct rendering

  
  

Installation
------------

yarn add vue-amis-sdk @fortawesome/fontawesome-free --save

Quick Start
-----------

### App.vue

<template\>
  <div id\='app'\>
    <vue-amis-sdk
      id\='editorName'
      theme\='cxd'
      className\='is-fixed'
      :preview\='isPreview'
      :isMobile\='isMobile'
      @onChange\='onChange'
      :value\='schema'
    />
  </div\>
</template\>
<script\>
import "amis-ui/lib/themes/cxd.css";
import "amis-ui/lib/themes/ang.css";
import "amis-editor/dist/style.css";
export default {
  name: 'App',
  data() {
    return {
      isPreview: false,
      isMobile: false,
      schema: {}
    }
  },
  methods: {
    onChange(e) {
      console.log(e)
    }
  }
}
</script\>

### version

vue-amis-sdk

amis

amis-editor

### repo

-   vue-amis-sdk editor
-   vue-amis-sdk repo
-   dgiot-dashboard
-   amis-vue-template
