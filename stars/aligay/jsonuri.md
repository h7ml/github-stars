---
project: jsonuri
stars: 161
description: 🌳 阿里剑鱼、iceluna、vanex 数据操作底层库，使用O(n) 复杂度回溯祖先节点
url: https://github.com/aligay/jsonuri
---

JSON URI
========

* * *

`Use URI style methods to operate data.` All operations friendly support Vue-like frameworks.

Use
---

$ npm install jsonuri --save

import \* as jsonuri from 'jsonuri'
// or
import { get, set, ... } from 'jsonuri' // recommended practice, friendly to tree-shaking

### Example Data:

{
  "menu": {
    "id": 123,
    "list": \[0, 1, 2, 3, 4\],
    "popup": {
      "menuitem": \[{
          "value": "New",
          "onclick": "CreateNewDoc()"
        },
        {
          "value": "Open",
          "onclick": "OpenDoc()"
        },
        {
          "value": "Close",
          "onclick": "CloseDoc()"
        }
      \]
    }
  }
}

Methods:
--------

### get (data, path)

Get the value of the specified data for the path.

**Example:**

jsonuri.get(data, 'menu/id')
// return 123

jsonuri.get(data, 'menu/popup/menuitem/0/value')
// return 'New'

jsonuri.get(data, 'menu/popup/menuitem/0/value/..')
// {value: "New", onclick: "CreateNewDoc()"}

see more

### set (data, path, value)

Set the value of the specified data for the path.

**Example:**

jsonuri.set(data, 'menu/id/', 789)
jsonuri.get(data, 'menu/id')
//789

see more

### rm (data, path)

Remove the value of the specified data for the path.

**Example:**

jsonuri.rm(data, 'menu/id')
jsonuri.get(data, 'menu/id') // undefined

see more

### mv (data, pathA, pathB, sequence)

Data A moved to target B before or after.

**Example:**

jsonuri.mv(data, 'menu/list/0', 'menu/list/3')
jsonuri.get(data, 'menu/list') // \[1, 2, 3, 0, 4\]
\[see more\](test/spec/mv\_spec.js)

jsonuri.set(data, 'menu/list/',\[0,1,2,3,4\])
jsonuri.mv(data, 'menu/list/0', 'menu/list/3', 'before')
jsonuri.get(data, 'menu/list') // \[1, 2, 0, 3, 4\]

see more

### swap (data, pathA, pathB)

Data swap in an array.

**Example:**

jsonuri.swap(data, 'menu/list/0', 'menu/list/4')
jsonuri.get(data, 'menu/list') // \[4, 1, 2, 3, 0\]

jsonuri.swap(data, 'menu/list/0', 'menu/list/4')
jsonuri.get(data, 'menu/list') // \[4, 1, 2, 3, 0\]

see more

### insert (data, pathA, value, direction)

Insert data into an `array` that is described in the path.

**Example:**

jsonuri.insert(data, 'menu/list/0', 9999, 'before') // \[9999, 0, 1, 2, 3, 4\]

see more

### up(data, path, gap)

see more

### down(data, path, gap)

see more

### walk(data, descentionFn, ascentionFn)

Traverse each data of each node and value.

**Example:**

jsonuri.walk({a:{a1:'x'}}, (value, key, parent, { path }) \=> {
  console.log(value, key, parent, path)
})

// { a1: 'x' } 'a' { a: { a1: 'x' } } 'a'
// x a1 { a1: 'x' } 'a/a1'

see more

### normalizePath(path1, path2, ...)

**Example:**

jsonuri.normalizePath('a', 'b') // a/b

jsonuri.normalizePath(\['a', 'b', '../'\], 'c') // a/c

see more

### isCircular(obj)

**Example:**

jsonuri.isCircular({}) // return false
jsonuri.isCircular(window) // return true

var a \= {}
jsonuri.set(a, '/b/c/d/e/f/g', a)
jsonuri.isCircular(a) // return true

see more
