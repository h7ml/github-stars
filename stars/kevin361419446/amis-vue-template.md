---
project: amis-vue-template
stars: 12
description: Use vue-admin-template as the base and integrate Baidu's low code tool amis
url: https://github.com/kevin361419446/amis-vue-template
---

amis-vue-template
=================

English | 简体中文

> This is built according to the vue-admin-template minimalist management background of huaunderpants great God. It only integrates the most basic dependency of Amis low code development, and can support vue+amis mixed development to achieve Amis code development rendering with minimal invasion of the original project. Its construction and operation fully comply with vue-admin-template. It should be noted that when jumping to the page of low code development of Amis, only one of the following parameters needs to be configured in the routing meta information, as follows:

```

  {
    path: '/amis',
    component: Layout,
    redirect: '/amis/theme',
    name: 'Amis',
    meta: {
      title: 'Amis',
      icon: 'nested'
    },
    children: [
      {
        path: '/tabs',
        name: 'tabs',
        component: () => import('@/views/amis/index'),
        meta: { title: 'tabs', icon: 'form', amisComponent: '/amis/tabs' }
      },
      {
        path: '/table',
        name: 'table',
        component: () => import('@/views/amis/index'),
        meta: { title: 'table', icon: 'form', amisComponent: '/amis/table' }
      }
    ]
  },

```

We have added the amiscomponent parameter in the routing meta information meta to point to the .json file of Amis low code development, which should be located in the directory views and can be compared with Vue files can also be stored together in a new directory, but they must be under the directory views. The end of the path should point to the .json file without adding the file extension .json

To learn more about vue-admin-template, please continue to read it or move to author's home page

**Live demo:** http://panjiachen.github.io/vue-admin-template

**The current version is `v4.0+` build on `vue-cli`. If you want to use the old version , you can switch branch to tag/3.11.0, it does not rely on `vue-cli`**

**SPONSORED BY**

Build Setup
-----------

# clone the project
git clone https://github.com/PanJiaChen/vue-admin-template.git

# enter the project directory
cd vue-admin-template

# install dependency
npm install

# develop
npm run dev

This will automatically open http://localhost:9528

Build
-----

# build for test environment
npm run build:stage

# build for production environment
npm run build:prod

Advanced
--------

# preview the release environment effect
npm run preview

# preview the release environment effect + static resource analysis
npm run preview -- --report

# code format check
npm run lint

# code format check and auto fix
npm run lint -- --fix

Refer to Documentation for more information

Demo
----

Extra
-----

If you want router permission && generate menu by user roles , you can use this branch permission-control

For `typescript` version, you can use vue-typescript-admin-template (Credits: @Armour)

Related Project
---------------

-   vue-element-admin
    
-   electron-vue-admin
    
-   vue-typescript-admin-template
    
-   awesome-project
    

License
-------

MIT license.
