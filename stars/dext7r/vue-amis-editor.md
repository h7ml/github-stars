---
project: vue-amis-editor
stars: 5
description: vue-amis-editor  不支持 vue-antd-pro
url: https://github.com/dext7r/vue-amis-editor
---

vue-amis-editor
===============

  
  

Installation
------------

yarn add vue-amis-editor --save

Quick Start
-----------

### Serve.vue

import VueAmisEditor from 'vue-amis-editor'
export default Vue.extend({
  name: 'ServeDev',
  components: {
    VueAmisEditor,
  },
  data() {
    return {
      preview: true,
      schema: {
        type: 'tasks',
        name: 'tasks',
        items: \[
          {
            label: 'hive 任务',
            key: 'hive',
            status: 4,
            remark: '查看详情<a target="\_blank" href="http://www.baidu.com">日志</a>。',
          },
          {
            label: '小流量',
            key: 'partial',
            status: 4,
          },
          {
            label: '全量',
            key: 'full',
            status: 4,
          },
        \],
        id: 'u:5f649ab86d6a',
      },
    }
  },
})
</script\>
<template\>
  <div id\="app"\>
    <vue-amis-editor :is-preview\="preview" :value\="schema" /\>
  </div\>
</template\>

prop

isPreview

isMobile

navHeight

isTools

sources

theme

loop

toolbar

value

onChange

obtain

copy

clear

getSchema

setSchema

togggeMobile

togglePreview

type

Boolean

Boolean

Number

Boolean

Array

Boolean

Boolean

Object

Object

Function

Function

Function

Function

Function

Function

Function

Function

default

false

false

50

true

\[\]

false

false

\` {title: 'vue-amis-editor',preview: 'preview',release: 'release',edit: 'edit',obtain: 'obtain',copy: "copy",clear: 'clear',set: "set"}\`

\`{message: 'message'}\`

\`onChange(e)\`

\`obtain\`

\`copy\`

\`clear\`

\`getSchema\`

\`setSchema(Schema)\`

\`togggeMobile(Boolean) \`

\`togglePreview(Boolean)\`'

explain

Whether it is in preview

Is it mobile

Toolbar height

Show and hide the toolbar

video's source link

autoplay when video is loaded

amis theme

Toolbar configuration, support for internationalization

schemanode

amis onChange

Get the data in the current amis-editor

Copy the data of amis-editor

data for clearamis-editor

Get the data of amis-editor

set the data of amis-editor

Switch between pc and mobile mode

Preview and edit mode switching

### Online examples

-   amis-admin-vue Online examples
-   amis-admin-vue repo
