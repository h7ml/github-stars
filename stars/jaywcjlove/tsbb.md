---
project: tsbb
stars: 106
description: TSBB is a CLI tool for developing, testing and publishing modern TypeScript projects with zero configuration, and can also be used for module or react component development. @tsbbjs
url: https://github.com/jaywcjlove/tsbb
---

Quick Start · Example · Command Help · npm · License

TSBB is a CLI tool for developing, testing and publishing modern TypeScript projects with zero configuration, and can also be used for module or react component development.

`TypeScript + Babel` = `TSBB`

Migrate from tsbb 3.x to 4.x.

`Features`
----------

-   🔥 Single dependency zero-configuration
-   ⏱ Quick initialization of example projects and entering development mode
-   ♻️ Automatic recompilation of code when files are added, modified, or removed
-   📚 Readable source code that encourages learning and contribution
-   🚀 Faster compilation speeds
-   ⚛️ Support for React and Vue 3 component compilation
-   ⛑ Jest test runner setup with defaults of `tsbb test`

Quick Start
-----------

You will need `Node.js` installed on your system.

$ yarn create tsbb \[appName\]
# or npm
$ npm create tsbb@latest my-app -- -e express
# --- Example name ------┴ˇˇˇˇˇ
# or npx
$ npx create-tsbb@latest my-app -e koa

# npm 7+, extra double-dash is needed:
$ npm init tsbb my-app -- --example typenexus
# npm 6.x
$ npm init tsbb my-app --example typenexus

$ cd my-project

$ npm run watch # Listen compile .ts files.
$ npm run build # compile .ts files.
$ npm start

1️⃣ Installation & Setup

$ npm i -D microbundle

2️⃣ Set up your `package.json`:

{
  "name": "@pkg/basic",
  "version": "1.0.0",
  "main": "./cjs/index.js",      // where to generate the CommonJS bundle
  "module": "./esm/index.js",    // where to generate the ESM bundle
  "exports": {
    "require": "./cjs/index.js", // used for require() in Node 12+
    "default": "./esm/index.js"  // where to generate the modern bundle (see below)
  },
  "scripts": {
    "watch": "tsbb watch",
    "build": "tsbb build --bail",
    "test": "tsbb test",
    "coverage": "tsbb test --coverage --bail"
  },
  "devDependencies": {
    "tsbb": "4.1.14"
  }
}

3️⃣ Try it out by running npm run build.

Example
-------

create-tsbb initialize the project from one of the examples:

$ npx create-tsbb my-app -e <Example Name\>
# --- E.g: ----------------┴ˇˇˇˇˇˇˇˇˇˇˇˇˇˇ
# npx create-tsbb my-app -e Basic

You can download the following examples directly. Download page.

-   **`basic`** - The Node.js base application example.
-   **`babel-transform-ts`** - Babel Transform Typescript Example.
-   **`express`** - The Express base application example.
-   **`typenexus`** - The Express & TypeORM base application example.
-   **`koa`** - The Koa base application example.
-   **`hapi`** - The Hapi base application example.
-   **`react-component`** - The react component base application example.
-   **`react-component-tsx`** - The react component and website base application example.
-   **`transform-typescript`** - Reconfigure the babel configuration example.
-   **`umd`** - umd bundle example.
-   **`vue`** - To add Vue 3 JSX support.

TypeScript Project
------------------

To configure the **`tsconfig.json`** properly, you must first define either the **`include`** or **`files`** field(s) to specify which files need to be compiled. Once you've done that, you can then specify the **`outDir`** for the output directory in the configuration.

{
  "$schema": "http://json.schemastore.org/tsconfig",
  "compilerOptions": {
    "module": "commonjs",
    "target": "esnext",
    "outDir": "./lib",
    "strict": true,
    "skipLibCheck": true
  },
  "include": \["src/\*\*/\*"\],
  "exclude": \[
    "node\_modules",
    "\*\*/\*.spec.ts"
  \]
}

After completing `tsconfig.jso` configuration, you can configure _scripts_ in `package.json`:

{
  "scripts": {
    "watch": "tsbb watch",
    "build": "tsbb build"
  },
  "devDependencies": {
    "tsbb": "\*"
  }
}

Babel Project
-------------

Adding the parameter `--use-babel` to your project enables babel to compile and output **`cjs`**/**`esm`** files simultaneously, while **`ts`** is only needed for _type_ output.

$ tsbb build "src/\*ts" --use-babel

You can change the built-in settings of Babel by adding a **`.babelrc`** configuration file. Additionally, you can modify the **Babel** configurations for **`esm`** and **`cjs`** separately through environment variables. Please refer to the example below:

{
  "env": {
    "cjs": {
      "presets": \["@babel/preset-typescript"\]
    },
    "esm": {
      "presets": \["@babel/preset-env", {
        "modules": false,
        "loose": true,
        "targets": {
          "esmodules": true,
        },
      }\]
    }
  } 
}

At compile time, specify the environment variable `--envName='xxx'` to enable reading of relevant configurations from the settings. This environment variable can also be customized.

{
  "env": {
    "xxx": { ... }
  } 
}

Command Help
------------

Below is a help of commands you might find useful.

### `tsbb`

▶ tsbb --help

Usage: tsbb <command\>

Commands:

  tsbb build \[source…\] \[options\]   Build your project once and exit.
  tsbb watch \[source…\] \[options\]   Recompile files on changes.
  tsbb test \[options\]              Run jest test runner in watch mode.
  tsbb copy|cpy <source …\> \[options\]   Copy files.

Options:\[build|watch\]

  --bail                     Exit the compile as soon as the compile fails(default: true).
  --use-babel                Use Babel.(works in babel)
  --source-maps              Enables the generation of sourcemap files.(works in babel)
  --env-name                 The current active environment used during configuration loading.(works in babel)
  --esm                      Output "esm" directory.(works in babel)
  --cjs                      Output "cjs" directory.(works in babel)
  --use-vue                  Supports "Vue3", requires "\--use-babel" to be used together.
Options:

  --version, -v              Show version number
  --help, -h                 Show help

Examples:

  $ tsbb build src/\*.ts                    Build your project.
  $ tsbb build src/main.ts src/good.ts     Specify the entry directory.
  $ tsbb build src/\*.ts --use-babel --no-source-maps   No ".js.map" file is generated. (works in babel)
  $ tsbb watch src/\*.ts --use-babel --cjs ./cjs        Watch Output directory.
  $ tsbb build src/\*.ts --use-babel --esm ./es         Output directory.
  $ tsbb build src/\*.ts --use-babel --use-vue          To add Vue JSX support.
  $ tsbb test                              Run test suites related
  $ tsbb test --coverage --bail            Test coverage information should be collected
  $ tsbb copy  'src/\*.png' '!src/goat.png' --output dist     Copy files.
  $ tsbb copy  'src/\*.png' 'src/goat.{js,d.ts}' --output dist --watch

  Copyright 2023

### `tsbb create`

Please use create-tsbb to create an example.

### `tsbb test`

Runs the test watcher (Jest) in an interactive mode.

$ tsbb test                          Run test suites related
$ tsbb test --coverage --no-color    Test coverage information should be collected

export declare type Argv \= Arguments<Partial<{
  all: boolean;
  automock: boolean;
  bail: boolean | number;
  cache: boolean;
  cacheDirectory: string;
  changedFilesWithAncestor: boolean;
  changedSince: string;
  ci: boolean;
  clearCache: boolean;
  clearMocks: boolean;
  collectCoverage: boolean;
  collectCoverageFrom: string;
  collectCoverageOnlyFrom: Array<string\>;
  color: boolean;
  colors: boolean;
  config: string;
  coverage: boolean;
  coverageDirectory: string;
  coveragePathIgnorePatterns: Array<string\>;
  coverageReporters: Array<string\>;
  coverageThreshold: string;
  debug: boolean;
  env: string;
  expand: boolean;
  findRelatedTests: boolean;
  forceExit: boolean;
  globals: string;
  globalSetup: string | null | undefined;
  globalTeardown: string | null | undefined;
  haste: string;
  init: boolean;
  injectGlobals: boolean;
  json: boolean;
  lastCommit: boolean;
  logHeapUsage: boolean;
  maxWorkers: number | string;
  moduleDirectories: Array<string\>;
  moduleFileExtensions: Array<string\>;
  moduleNameMapper: string;
  modulePathIgnorePatterns: Array<string\>;
  modulePaths: Array<string\>;
  noStackTrace: boolean;
  notify: boolean;
  notifyMode: string;
  onlyChanged: boolean;
  onlyFailures: boolean;
  outputFile: string;
  preset: string | null | undefined;
  projects: Array<string\>;
  prettierPath: string | null | undefined;
  resetMocks: boolean;
  resetModules: boolean;
  resolver: string | null | undefined;
  restoreMocks: boolean;
  rootDir: string;
  roots: Array<string\>;
  runInBand: boolean;
  selectProjects: Array<string\>;
  setupFiles: Array<string\>;
  setupFilesAfterEnv: Array<string\>;
  showConfig: boolean;
  silent: boolean;
  snapshotSerializers: Array<string\>;
  testEnvironment: string;
  testFailureExitCode: string | null | undefined;
  testMatch: Array<string\>;
  testNamePattern: string;
  testPathIgnorePatterns: Array<string\>;
  testPathPattern: Array<string\>;
  testRegex: string | Array<string\>;
  testResultsProcessor: string;
  testRunner: string;
  testSequencer: string;
  testURL: string;
  testTimeout: number | null | undefined;
  timers: string;
  transform: string;
  transformIgnorePatterns: Array<string\>;
  unmockedModulePathPatterns: Array<string\> | null | undefined;
  updateSnapshot: boolean;
  useStderr: boolean;
  verbose: boolean;
  version: boolean;
  watch: boolean;
  watchAll: boolean;
  watchman: boolean;
  watchPathIgnorePatterns: Array<string\>;
}\>\>;

Development
-----------

$ npm i
$ npm run build

Contributors
------------

As always, thanks to our amazing contributors!

Made with contributors.

License
-------

MIT © Kenny Wong
