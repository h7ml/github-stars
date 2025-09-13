---
project: idraw
stars: 1062
description: A simple JavaScript framework for Drawing on the web.(一个面向Web绘图的JavaScript框架)
url: https://github.com/idrawjs/idraw
---

iDraw.js
========

iDraw.js is a simple JavaScript framework for Drawing on the web.

一个面向Web绘图的JavaScript框架

idrawjs.com

* * *

-   Documents | 中文文档
-   Online Playground | 在线API示例
-   Online Studio | 在线绘图演示

Sponsors
--------

iDraw.js is an MIT-licensed open source project with its ongoing development made possible entirely by the support of these awesome backers. If you'd like to join them, please consider sponsoring iDrawjs's development.

@idraw/studio Preview
---------------------

The preview of `@idraw/studo`. Click here to get it.

Install
-------

```
npm i idraw
```

Getting Started
---------------

### Common

import { iDraw } from 'idraw';

const idraw \= new iDraw(
  document.querySelector('#app'),
  {
    width: 600,
    height: 400,
    devicePixelRatio: 1,
  }
);
idraw.addElement({
  name: "rect-1",
  x: 140,
  y: 120,
  w: 200,
  h: 100,
  type: "rect",
  detail: {
    background: "#f7d3c1",
    borderRadius: 20,
    borderWidth: 4,
    borderColor: "#ff6032",
  },
});

### React

import { iDraw } from 'idraw';
import { useEffect, useRef } from 'react';

function Demo() {
  const ref \= useRef(null);
  useEffect(() \=> {
    const idraw \= new iDraw(ref.current, {
      width: 600,
      height: 400, 
      devicePixelRatio: 1,
    });
    idraw.addElement({
      name: "rect-001",
      x: 140,
      y: 120,
      w: 200,
      h: 100,
      type: "rect",
      detail: {
        background: "#f7d3c1",
        borderRadius: 20,
        borderWidth: 4,
        borderColor: "#ff6032",
      },
    })
  }, \[\]);

  return (
    <div ref\={ref}\></div\>
  )
}

### Vue

<template\>
  <div ref\="mount"\></div\>
</template\>

<script setup \>
import { iDraw } from 'idraw';
import { ref, onMounted } from 'vue'
const mount \= ref();

onMounted(() \=> {
  const idraw \= new iDraw(mount.value, {
    width: 600,
    height: 400, 
    devicePixelRatio: 1,
  });
  idraw.addElement({
    name: "rect-001",
    x: 140,
    y: 120,
    w: 200,
    h: 100,
    type: "rect",
    detail: {
      background: "#f7d3c1",
      borderRadius: 20,
      borderWidth: 4,
      borderColor: "#ff6032",
    },
  })
})
</script\>

Contributing
------------

We appreciate your help!

To contribute, please follow the steps:

-   `git clone git@github.com:idrawjs/idraw.git`
-   `cd idraw`
-   `pnpm i`
-   `npm run dev`
