---
project: utils
stars: 3
description: ataola's utils: maybe publish a feature one week, to record something i think or meet.
url: https://github.com/ataola/utils
---

utils
=====

ataola's utils: maybe publish a feature one week, to record something i think or meet.

Introduction
------------

site|docs

Modules
-------

Installation
------------

npm i @ataola/utils --save

Usage
-----

### es module

import \* as utils from '@ataola/utils';

utils.getVersion();

import { getVersion } from '@ataola/utils';
console.log(getVersion());

### commonjs

command:

npm init -y
npm i esm @ataola/utils --save

for example:

const utils \= require('@ataola/utils');
console.log(utils);

const { getVersion } \= require('@ataola/utils');
console.log(getVersion());

package.json

...
 "scripts": {
    "test": "echo \\"Error: no test specified\\" && exit 1",
    "esm": "node -r esm index.js"
  },
...
