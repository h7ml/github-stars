---
project: dgiot_vue_amis
stars: 1
description: dgiot_vue_amis
url: https://github.com/dgiot/dgiot_vue_amis
---

dgiot\_vue\_amis
================

about
-----

-   This project is based on vuera and mainly focuses on the encapsulation of amis-editor
-   You can edit at this. The proxy mode is enabled. You can copy the JSON of amis. It supports direct rendering

  
  

Installation
------------

yarn add dgiot\_vue\_amis @fortawesome/fontawesome-free --save

Quick Start
-----------

### App.vue

<template\>
  <div id\='app'\>
    <dgiot\_vue\_amis
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

dgiot\_vue\_amis

amis

amis-editor

### repo

-   dgiot\_vue\_amis editor
-   dgiot\_vue\_amis repo
-   dgiot-dashboard
-   amis-vue-template
