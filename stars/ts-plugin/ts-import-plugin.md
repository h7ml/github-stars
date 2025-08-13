---
project: ts-import-plugin
stars: 609
description: babel-import-plugin TypeScript Implement
url: https://github.com/ts-plugin/ts-import-plugin
---

ts-import-plugin
================

Modular import plugin for TypeScript, compatible with antd, antd-mobile and so on.

webpack template `./webpack.config.js`, run: `npm start` to see the bundle analyzer.

> This plugin is not work if your are using `import * as _ from 'lodash'` or `import _ from 'lodash'`

Why use this
============

transform such code:

import { Alert, Card as C } from 'antd'

into:

import Alert from 'antd/lib/alert'
import 'antd/lib/alert/style/index.less'
import { default as C } from 'antd/lib/card'
import 'antd/lib/card/style/index.less'

Usage
=====

With ts-loader
--------------

//tsconfig.json
{
  ...
  "module": "ESNext",
  ...
}

// webpack.config.js
const tsImportPluginFactory \= require('ts-import-plugin')

module.exports \= {
  // ...
  module: {
    rules: \[
      {
        test: /\\.(jsx|tsx|js|ts)$/,
        loader: 'ts-loader',
        options: {
          transpileOnly: true,
          getCustomTransformers: () \=> ({
            before: \[tsImportPluginFactory(/\*\* options \*/)\],
          }),
          compilerOptions: {
            module: 'es2015',
          },
        },
        exclude: /node\_modules/,
      },
    \],
  },
  // ...
}

With awesome-typescript-loader ( >= 3.5.0 )
-------------------------------------------

//tsconfig.json
{
  ...
  "module": "ESNext",
  ...
}

// webpack.config.js
const tsImportPluginFactory \= require('ts-import-plugin')

module.exports \= {
  // ...
  module: {
    rules: \[
      {
        test: /\\.tsx?$/,
        loader: 'awesome-typescript-loader',
        options: {
          getCustomTransformers: () \=> ({
            before: \[tsImportPluginFactory(/\*\* options \*/)\],
          }),
        },
        exclude: /node\_modules/,
      },
    \],
  },
  // ...
}

With rollup
-----------

import typescript from 'rollup-plugin-typescript2' // or '@rollup/plugin-typescript'
import createTransformer from 'ts-import-plugin'

const transformer \= createTransformer({
  libraryDirectory: 'es',
  libraryName: 'antd',
  style: true,
})

export default {
  input: \`./test/fixtures/index.tsx\`,
  plugins: \[
    typescript({
      clean: true,
      transformers: \[
        () \=> ({
          before: transformer,
        }),
      \],
    }),
  \],
  output: \[
    {
      file: \`./dist/rollup.dist.js\`,
      format: 'esm',
    },
  \],
}

Options
-------

`options` can be an object:

-   libraryName `string` - The name of the library in the import. e.g. If using `import { foo } from 'Bar'` the library should be set to 'bar'.
    
    default `'antd'`
    
-   style `boolean | string | ((path: string) => string)`
    
    default `false`
    
-   libraryDirectory `string | ((name: string) => string)` - The directory within the library to replace the import with. e.g. If you have `import { foo } from 'Bar'`, it will be replaced to `import foo from` \`Bar/${libraryDirectory}/foo\`\`
    
    default `'lib'`
    
-   camel2DashComponentName `boolean` - Builtin method to use to transform the component name. This does transform the component name from camelCase to dashed. e.g. `FooBar` gets transformed to `foo-bar`
    
    default `true`
    
-   camel2UnderlineComponentName `boolean` - Builtin method to use to transform the component name. This does transform the component name from camelCase to snake\_case. e.g. `FooBar` gets transformed to `foo_bar`
    
    default `false`
    
-   libraryOverride `boolean` - Setting to false (default) prepends the `libraryName` to the `libraryDirectory` (with a path separator) set to true if you want to use the `libraryDirectory` as the full path for the import.
    
    default `false`
    
-   failIfNotFound `boolean` - If the component is not found in the library, the full library is imported by default. set to true to fail the build.
    
    default `false`
    

example:

tsImportPluginFactory({
  libraryName: 'antd',
  libraryDirectory: 'lib',
  style: true,
})

{
  libraryName: '@material-ui/core',
  libraryDirectory: '',
  camel2DashComponentName: false
}

`options` can be an array:

example:

;\[
  {
    libraryName: 'antd',
    libraryDirectory: 'lib',
    style: true,
  },
  {
    libraryName: '@material-ui/core',
    libraryDirectory: '',
    camel2DashComponentName: false,
  },
\]

Compatible libs:
================

ant-design
----------

const transformerFactory \= require('ts-import-plugin')
// with less
transformerFactory({ style: true })
// with css
transformerFactory({ style: 'css' })
// without style
transformerFactory()

lodash
------

> notice you should manual `import 'lodash/core'` in your project if your are using `import { chain } from 'lodash'` .

transformerFactory({
  style: false,
  libraryName: 'lodash',
  libraryDirectory: null,
  camel2DashComponentName: false,
})

antd-mobile
-----------

// with css.web
transformerFactory({ libraryName: 'antd-mobile', style: 'css', styleExt: 'css.web' })

// antd-mobile recently changed styleExt. If error occurs with prev, try next.
transformerFactory({ libraryName: 'antd-mobile', style: 'css' })

material-ui
-----------

import { Button } from '@material-ui/core'
import { Remove, Refresh, Add } from '@material-ui/icons'

transformerFactory({
  libraryName: '@material-ui/core',
  libraryDirectory: '',
  camel2DashComponentName: false,
})

// svg-icons
transformerFactory({
  libraryDirectory: (importName) \=> {
    const stringVec \= importName
      .split(/(\[A\-Z\]\[a\-z\]+|\[0\-9\]\*)/)
      .filter((s) \=> s.length)
      .map((s) \=> s.toLocaleLowerCase())

    return stringVec.reduce((acc, cur, index) \=> {
      if (index \> 1) {
        return acc + '-' + cur
      } else if (index \=== 1) {
        return acc + '/' + cur
      }
      return acc + cur
    }, '')
  },
  libraryName: '@material-ui/icons',
  style: false,
  camel2DashComponentName: false,
})

element-ui
----------

import { Button } from 'element-ui'

transformerFactory({
  libraryName: 'element-ui',
  libraryDirectory: 'lib',
  camel2DashComponentName: true,
  style: (path: string) \=> join('element-ui', 'lib', 'theme-chalk', \`${camel2Dash(basename(path, '.js'))}.css\`),
})

RxJS
----

see rxjs-webpack-treeshaking-example for more details

> only compatible for 5.5+

-   RxJS v5:

transformerFactory({
  libraryDirectory: '../\_esm2015/operators',
  libraryName: 'rxjs/operators',
  style: false,
  camel2DashComponentName: false,
  transformToDefaultImport: false,
})

-   RxJS v6:

transformerFactory(\[
  {
    libraryDirectory: '../\_esm5/internal/operators',
    libraryName: 'rxjs/operators',
    camel2DashComponentName: false,
    transformToDefaultImport: false,
  },
  {
    libraryDirectory: '../\_esm5/internal/observable',
    libraryName: 'rxjs',
    camel2DashComponentName: false,
    transformToDefaultImport: false,
  },
\])

Contributors
------------

### Code Contributors

This project exists thanks to all the people who contribute. \[Contribute\].

### Financial Contributors

Become a financial contributor and help us sustain our community. \[Contribute\]

#### Individuals

#### Organizations

Support this project with your organization. Your logo will show up here with a link to your website. \[Contribute\]
