---
project: aumi
stars: 13
description: null
url: https://github.com/atom-yang/aumi
---

AUmi
====

Build Umi based on Rsbuild

English | 简体中文

AUmi switches Umi's default bundler from Webpack to Rsbuild

Features
--------

-   10x performance improvement;
-   Retain Umi plugin system and the same user experience;
-   Migration Umi project in 5 minutes.

Migration
---------

**Notice: Make sure your Umi version is >= 4.0**

**Notice: V**

### Installation

npm add @aumi/aumi@latest -S

### File changes

#### Updating `.umirc.ts` :

\- import { defineConfig } from 'umi';
+ import {defineAUMIConfig} from "@aumi/aumi";

\- export default defineConfig({
+ export default defineAUMIConfig({
  ...,
});

Due to compatibility or lacking of testing, cannot support the following configurations.

Field

Unsupported Reason

Replacement method

autoprefixer

Use another approach

1\. use browserlist  
2\. `targets` configuration of `.umirc.ts`

cssMinifier

Use another approach

`minify` configuration of `.umirc.ts`

classPropertiesLoose

This is a babel configuration in Umi, Rsbuild uses swc by default

`swcLoader` configuration of `.umirc.ts`

deadCode

Webpack plugin, rspack compatibility is no tested

None

depTranspiler

Not used in `@umijs/bundler-webpack`

None

esbuildMinifyIIFE

Fix the namespace conflict caused by global variables automatically introduced by the esbuild compressor, not needed

None

extraBabelIncludes

Switching to `extraIncludes` configuration

`extraIncludes` configuration of `.umirc.ts`

extraBabelPlugins

Switching to `swcLoader` configuration

Use `swcLoader` configuration of `.umirc.ts`, check Rsbuild for details

extraBabelPresets

As above

As above

exportStatic

Not tested

无

extraPostCSSPlugins

Switching to `postcssLoader` configuration

Use `postcssLoader` configuration of `.umirc.ts`, check Rsbuild for details

forget

Not tested

None

jsMinifier

Switching to `minify` configuration

Use `minify` configuration of `.umirc.ts`, check Rsbuid for details

jsMinifierOptions

As above

As above

legacy

Not supported

None

mdx

Not supported

Use `chainWebpack` function of `.umirc.ts`

mfsu

Not tested

Use new added configuration `moduleFederation` of `.umirc.ts`, check Rsbuild for details

runtimePublicPath

Hasn't test compatibility of webpack plugin `RuntimePublicPathPlugin`

None

srcTranspiler

Not supported, use `swcLoader`

None

srcTranspilerOptions

As above

None

`defineAUMIConfig` has comprehensive TypeScript typing support except Umi plugins' typing

### Updating `package.json`

Updating `scripts` field of `package.json`.

{
  "scripts": {
\-   "dev": "umi dev",
+   "dev": "aumi dev",
\-   "build": "umi build",
+   "build": "aumi build",
+   "analyze": "RSDOCTOR=true aumi build",
\-   "postinstall": "umi setup",
+   "postinstall": "aumi setup",
\-   "setup": "umi setup",
+   "setup": "aumi setup",
    "start": "npm run dev"
  }
}

The `analyze` command replaces Umi's `analyze` functionality by using Rsdoctor.

Start a new Project
-------------------

Take Umi Getting Started as a reference to start a new project, and follow instructions above Migration

Other changes
-------------

### New configuration in `.umirc.ts`

Field

Default value

Usage

rsbuildConfig

undefined

Full RsbuildConfig and has higher priority than other configs, will be merged by mergeRsbuildConfig, Reference

aliasStrategy

'prefer-alias'

The strategy of `alias` configuration, Reference

transformImport

undefined

Similar to `babel-plugin-import`, Reference

react

reference

The configuration of Rsbuild plugin `@rsbuild/plugin-react`, Reference

rspack

undefined

Modify rspack configuration, Reference

### Changes of Umi plugins' extended methods

Umi provides massive extended methods by its plugin mechanism Umi Plugin Api. Due to we switch the bundler from `@umijs/bundler-webpack` to `Rsbuild`, some underlying build processes are inconsistent with `@umijs/bundler-webpack`. As a result, certain custom methods have been removed, if any removed methods are called, an error will be thrown out.

Remove extended methods as below, most are `Babel` related:

-   addExtraBabelPresets
-   addExtraBabelPlugins
-   addBeforeBabelPresets
-   addBeforeBabelPlugins
-   modifyWebpackConfig
-   modifyViteConfig
-   modifyServerRendererPath
-   modifyBabelPresetOpts

Add new extended methods for `Rsbuild`

-   `modifyRsbuildPlugins`: modifying `Rsbuild` plugins

Example:

api.modifyRsbuildPlugins(plugins \=> {
  return plugins.slice(1);
});

-   `modifyRsbuildConfig`: modifying `RsbuildConfig` with the highest priority

example:

api.modifyRsbuildConfig(config \=> {
  config.root \= './';
  return config;
});

Remain issues
-------------

TODO
