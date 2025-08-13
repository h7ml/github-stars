---
project: be-full
stars: 195
description: 🛰 浏览器全屏 / full screen
url: https://github.com/any86/be-full
---

be-full
=======

**Full screen display**, support PC/mobile, less than **1kb**. 🚀Online demo

Language
--------

中文 | **English**

Install
-------

npm i -S be-full

⚡ quick start
-------------

##### web page full screen

import {beFull} from 'be-full';
beFull();

##### element fullscreen

const el \= document.getElementById('video');
beFull(el);

#### set css property ":fullscreen"

If there is a "black" gap (or other colors) when the element is full screen, the second parameter can be set to the specified color.

const el \= document.getElementById("video");
beFull(el, "#fff");

**Note:** After executing "**exitFull**" or "**toggleFull**", the setting of ":fullscreen" will be automatically canceled.

🔥 API
------

##### exitFull(Exit Full Screen)

exitFull();

##### toggleFull (toggle full screen/exit)

The method of use is the same as `beFull`, except that the second click will execute `exitFull`

toggleFull();

// Switch the specified element to full screen/exit
toggleFull(document.getElementById('video'));

##### isFull (whether the element is full screen)

isFull(document.getElementById('video')); // true or false
