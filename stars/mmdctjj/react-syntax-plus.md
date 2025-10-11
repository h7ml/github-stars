---
project: react-syntax-plus
stars: 10
description: react-syntax-plus 🚀🚀🚀
url: https://github.com/mmdctjj/react-syntax-plus
---

react-syntax-plus README
========================

react-syntax-plus: This is a syntax snippets plugin for React designed to simplify and accelerate the development process.

English | 简体中文

Features
--------

There are two core functions of the plugin

-   Quickly create basic variables based on 'useState' and 'useRef'
-   Behavior derived from basic variables: useMemo, useVNet, useEffect, and useLayoutEffect\`
-   Custom hooks starting with 'use'

When these methods are used, the corresponding method will be automatically introduced from the 'React' library (ignored if already introduced).

Additionally, it should be noted that the way to activate the corresponding method is to enter the corresponding keyword in the text, followed by the corresponding character recognition area.

method

keyword

`useRef`

`uf`

`useState`

`us`

`useMemo`

`um`

`useCallback`

`uc`

`useEffect`

`ue`

`useLayoutEffect`

`ul`

### useRef and useState

The characters after 'uf' and 'us' will be used as corresponding variable names. Note that variables after' us' will be placed in an array, and the second variable in the array will be automatically named with a camel hump.

### useMemo

The characters after 'um' will be used to match the base variables starting with this. After inserting the code, you need to input the variables and then press the 'tab' key to quickly jump to the custom logic after the 'return' statement.

### useCallback

The characters after 'uc' will be used to match base or derived variables that start with this, and variables need to be input after inserting the code.

### useEffect and useLayoutEffect

The characters after 'ue' and 'ul' will be used to match base or derived variables starting with this, and then listen for their changes,

### props

Use keywords with props to wake up, for example: `ueprops`, which will prompt a code prompt based on useEffect with props,

If a string is appended after `ueprops`, it will be considered a property of props, for example:

Of course, if you have already deconstructed props, the deconstructed properties will be automatically recognized, such as:

### Custom hooks

Custom hooks starting with 'use'.

Release Notes
-------------

https://github.com/mmdctjj/react-syntax-plus/releases

**Enjoy!**
