---
project: b-tween
stars: 28
description: A simple but powerful tweening engine for Javascript.
url: https://github.com/PengJiyuan/b-tween
---

b-tween
=======

A simple but powerful tweening engine for Javascript.

Install
-------

npm i b-tween

Usage
-----

#### ES Module

import BTween from 'b-tween';
const tween \= new BTween({
  from: {
    left: 0
  },
  to: {
    left: 700
  },
  duration: 500,
  easing: 'bounceOut',
  onUpdate: (keys) \=> {
    // You can do everything with keys
    block.style.left \= keys.left + 'px';
  }
});
tween.start();

#### Commonjs

const BTween \= require('b-tween');
...

#### Browser

https://unpkg.com/b-tween/dist/b-tween.umd.js

<script src\="https://unpkg.com/b-tween/dist/b-tween.umd.js"\></script\>
<script\>
  const tween \= new BTween({
    ...
  });
  tween.start();
</script\>

Api
---

### new Tween(options)

#### options.from (object)

#### options.to (object)

#### options.duration (number)

#### options.delay (number)

#### options.easing (string)

-   linear
-   quadIn
-   quadOut
-   quadInOut
-   cubicIn
-   cubicOut
-   cubicInOut
-   quartIn
-   quartOut
-   quartInOut
-   quintIn
-   quintOut
-   quintInOut
-   sineIn
-   sineOut
-   sineInOut
-   bounceIn
-   bounceOut
-   bounceInOut

#### options.onStart ( function(keys) {} )

#### options.onUpdate ( function(keys) {} )

#### options.onFinish ( function(keys) {} )

### Start Animation

const tween \= new Btween({...});
tween.start();

LICENSE
-------

MIT © PengJiyuan
