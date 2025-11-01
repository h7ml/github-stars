---
project: zova
stars: 124
description: A more intuitive framework with the pros of Vue3, React and Angular, empowers developers to build elegant, fast and reliable applications
url: https://github.com/zovajs/zova
---

English | 简体中文

Zova
====

Zova is a more intuitive framework with the pros of Vue3, React and Angular, empowers developers to build elegant, fast and reliable applications

With UI libraries
-----------------

Zova can be used with any UI library and comes with built-in project templates for several UI libraries, making it easy to use out of the box, including:

-   antdv
-   element-plus
-   quasar
-   vuetify
-   empty： Other UI libraries can be used based on this empty template

Demo online
-----------

-   vue3 + ts + tsx + tailwindcss + daisyui

Documentation
-------------

-   Get Started
-   Why Vue3+IOC?

Coding style: Vue+React+Angular
-------------------------------

Zova refines the pros of `Vue3/React/Angular` and avoid their cons to make our development experience more elegant and reduce the mental burden

1.  `Vue3`: Zova still uses Vue3's convenient responsive api system, but defining responsive variables is just like defining native variables, without the need to use `ref/reactive`, and naturally without `ref.value`
2.  `React`: Zova uses the `tsx` syntax to write rendering logic in a `Render Class`, which not only perfectly matches the TS type system, but also supports the splitting of rendering code, and can keep the code clean and elegant even in the face of complex business. In Zova, there are no many hook apis like React, which greatly reduces the mental burden
3.  `Angular`: In actual development, there are three scenarios of state sharing: `state sharing of component internal`, `state sharing between components` and `global state sharing`. In the traditional Vue3, different mechanisms are used to achieve these state sharing scenes, while only a unified IOC container mechanism is needed in Zova. The IOC container provided by Zova abandons the cumbersome design of Angular, with clearer concepts and more powerful functions

Features
--------

-   SSR: Built-in out-of-the-box SSR solution, supporting both front-end applications and admin management systems
-   Modularization: The basis for building large business systems
-   IOC: The basis for business abstraction and modeling
-   Module Scope: Access strategy based on dependency lookup
-   Route Query: Routes with TS types
-   Mock: More convenient Mock Mechanism
-   Icon: UI library-independent icon engine
-   CSS-in-JS: Style & Theme: More flexible style engine based on TypeStyle
-   Model: Unified Data Source: Data management strategy based on Tanstack Query
-   Env: Env file loading strategy based on multi-dimensional variables

How to do
---------

$ npm run init
$ cd ./zova-dev
$ npm run dev

How to do: ui-antdv
-------------------

$ cd zova-ui-antdv
$ pnpm install
$ npm run dev

How to do: ui-element
---------------------

$ cd zova-ui-element
$ pnpm install
$ npm run dev

How to do: ui-quasar
--------------------

$ cd zova-ui-quasar
$ pnpm install
$ npm run dev

How to do: ui-vuetify
---------------------

$ cd zova-ui-vuetify
$ pnpm install
$ npm run dev

How to do: ui-empty
-------------------

$ cd zova-ui-empty
$ pnpm install
$ npm run dev

Stay In Touch
-------------

-   Twitter
-   Wechat

Thanks
------

-   Thanks to Angular that ioc container of Zova was in part inspired by Angular
-   Thanks to React that React’s pioneering JSX syntax has significantly improved the efficiency and experience of front-end development
-   Thanks to Vue that Vue provides a very powerful reactive system and ecosystem. Without the support of these ecosystems, Zova would be difficult to implement

License
-------

MIT

Copyright (c) 2016-present, Zova
