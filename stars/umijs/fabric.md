---
project: fabric
stars: 640
description: 💪严格但是不严苛的编码规范
url: https://github.com/umijs/fabric
---

umi-fabric
==========

一个包含 prettier，eslint，stylelint 的配置文件合集

A collection of configuration files containing prettier, eslint, stylelint

Use
===

安装

npm i @umijs/fabric --save-dev
yarn add @umijs/fabric -D

in `.eslintrc.js`

module.exports \= {
  extends: \[require.resolve('@umijs/fabric/dist/eslint')\],

  // in antd-design-pro
  globals: {
    ANT\_DESIGN\_PRO\_ONLY\_DO\_NOT\_USE\_IN\_YOUR\_PRODUCTION: true,
    page: true,
  },

  rules: {
    // your rules
  },
};

in `.stylelintrc.js`

module.exports \= {
  extends: \[require.resolve('@umijs/fabric/dist/stylelint')\],
  rules: {
    // your rules
  },
};

in `.prettierrc.js`

const fabric \= require('@umijs/fabric');

module.exports \= {
  ...fabric.prettier,
};
