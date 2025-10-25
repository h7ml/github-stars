---
project: depcheck
stars: 4933
description: Check your npm module for unused dependencies
url: https://github.com/depcheck/depcheck
---

depcheck
========

Note

Depcheck is no longer actively maintained

While it has been widely used to identify unused dependencies in JavaScript and TypeScript projects, its lack of updates means it may not work well with modern tooling and frameworks. We strongly recommend switching to knip, a more actively maintained and feature-rich alternative. Knip provides better support for TypeScript, monorepos, and modern build tools, making it a more reliable choice for keeping your project dependencies clean. Check out knip.dev

Depcheck is a tool for analyzing the dependencies in a project to see: how each dependency is used, which dependencies are useless, and which dependencies are missing from `package.json`.

Status
------

Installation
------------

```
npm install -g depcheck
```

Or simply using npx which is a package runner bundled in `npm`:

```
$ npx depcheck
```

_Notice:_ depcheck needs node.js >= 10.

Syntax Support
--------------

Depcheck not only recognizes the dependencies in JavaScript files, but also supports these syntaxes:

-   JavaScript (ES5, ES6 and ES7)
-   React JSX
-   CoffeeScript
-   TypeScript (with `typescript` dependency)
-   SASS and SCSS
-   Vue.js (with `@vue/compiler-sfc` dependency)

To get the syntax support by external dependency, please install the corresponding package explicitly. For example, for TypeScript user, install depcheck with `typescript` package:

```
npm install -g depcheck typescript
```

Special
-------

The _special_ component is used to recognize the dependencies that are not generally used in the above syntax files. The following scenarios are supported by specials:

-   `babel` - Babel presets and plugins
-   `bin` - Dependencies used in npm commands, Travis scripts or other CI scripts
-   `commitizen` - Commitizen configuration adaptor
-   `eslint` - ESLint configuration presets, parsers and plugins
-   `feross-standard` - Feross standard format parser
-   `gatsby` - Gatsby configuration parser
-   `gulp-load-plugins` - Gulp-load-plugins lazy loaded plugins
-   `husky` - Husky configuration parser
-   `istanbul` - Istanbul nyc configuration extensions
-   `jest` - Jest properties in Jest Configuration
-   `karma` - Karma configuration frameworks, browsers, preprocessors and reporters
-   `lint-staged` - Lint-staged configuration parser
-   `mocha` - Mocha explicit required dependencies
-   `prettier` - Prettier configuration module
-   `tslint` - TSLint configuration presets, parsers and plugins
-   `ttypescript` - ttypescript transformers
-   `webpack` - Webpack loaders
-   `serverless`\- Serverless plugins

The logic of a special is not perfect. There might be false alerts. If this happens, please open an issue for us.

Usage
-----

```
depcheck [directory] [arguments]
```

The `directory` argument is the root directory of your project (where the `package.json` file is). If unspecified, defaults to current directory.

All of the arguments are optional:

`--ignore-bin-package=[true|false]`: A flag to indicate if depcheck ignores the packages containing bin entry. The default value is `false`.

`--skip-missing=[true|false]`: A flag to indicate if depcheck skips calculation of missing dependencies. The default value is `false`.

`--json`: Output results in JSON. When not specified, depcheck outputs in human friendly format.

`--oneline`: Output results as space separated string. Useful for copy/paste.

`--ignores`: A comma separated array containing package names to ignore. It can be glob expressions. Example, `--ignores="eslint,babel-*"`.

`--ignore-dirs`: DEPRECATED, use ignore-patterns instead. A comma separated array containing directory names to ignore. Example, `--ignore-dirs=dist,coverage`.

`--ignore-path`: Path to a file with patterns describing files to ignore. Files must match the .gitignore spec. Example, `--ignore-path=.eslintignore`.

`--ignore-patterns`: Comma separated patterns describing files to ignore. Patterns must match the .gitignore spec. Example, `--ignore-patterns=build/Release,dist,coverage,*.log`.

`--quiet`: Suppress the "No depcheck issue" log. Useful in a monorepo with multiple packages to focus only on packages with issues.

`--help`: Show the help message.

`--parsers`, `--detectors` and `--specials`: These arguments are for advanced usage. They provide an easy way to customize the file parser and dependency detection. Check the pluggable design document for more information.

`--config=[filename]`: An external configuration file (see below).

Usage with a configuration file
-------------------------------

Depcheck can be used with an rc configuration file. In order to do so, create a .depcheckrc file in your project's package.json folder, and set the CLI keys in YAML, JSON, and JavaScript formats. For example, the CLI arguments `--ignores="eslint,babel-*" --skip-missing=true` would turn into:

**_.depcheckrc_**

```
ignores: ["eslint", "babel-*"]
skip-missing: true
```

**Important:** if provided CLI arguments conflict with configuration file ones, the CLI ones will take precedence over the rc file ones.

The rc configuration file can also contain the following extensions: `.json`, `.yaml`, `.yml`.

API
---

Similar options are provided to `depcheck` function for programming:

import depcheck from 'depcheck';

const options \= {
  ignoreBinPackage: false, // ignore the packages with bin entry
  skipMissing: false, // skip calculation of missing dependencies
  ignorePatterns: \[
    // files matching these patterns will be ignored
    'sandbox',
    'dist',
    'bower\_components',
  \],
  ignoreMatches: \[
    // ignore dependencies that matches these globs
    'grunt-\*',
  \],
  parsers: {
    // the target parsers
    '\*\*/\*.js': depcheck.parser.es6,
    '\*\*/\*.jsx': depcheck.parser.jsx,
  },
  detectors: \[
    // the target detectors
    depcheck.detector.requireCallExpression,
    depcheck.detector.importDeclaration,
  \],
  specials: \[
    // the target special parsers
    depcheck.special.eslint,
    depcheck.special.webpack,
  \],
  package: {
    // may specify dependencies instead of parsing package.json
    dependencies: {
      lodash: '^4.17.15',
    },
    devDependencies: {
      eslint: '^6.6.0',
    },
    peerDependencies: {},
    optionalDependencies: {},
  },
};

depcheck('/path/to/your/project', options).then((unused) \=> {
  console.log(unused.dependencies); // an array containing the unused dependencies
  console.log(unused.devDependencies); // an array containing the unused devDependencies
  console.log(unused.missing); // a lookup containing the dependencies missing in \`package.json\` and where they are used
  console.log(unused.using); // a lookup indicating each dependency is used by which files
  console.log(unused.invalidFiles); // files that cannot access or parse
  console.log(unused.invalidDirs); // directories that cannot access
});

Example
-------

The following example checks the dependencies under `/path/to/my/project` folder:

$\> depcheck /path/to/my/project
Unused dependencies
\* underscore
Unused devDependencies
\* jasmine
Missing dependencies
\* lodash

It figures out:

-   The dependency `underscore` is declared in the `package.json` file, but not used by any code.
-   The devDependency `jasmine` is declared in the `package.json` file, but not used by any code.
-   The dependency `lodash` is used somewhere in the code, but not declared in the `package.json` file.

Please note that, if a subfolder has a `package.json` file, it is considered another project and should be checked with another depcheck command.

The following example checks the same project, however, outputs as a JSON blob. Depcheck's JSON output is in one single line for easy pipe and computation. The `json` command after the pipe is a node.js program to beautify the output.

$\> depcheck /path/to/my/project \--json | json
{
  "dependencies": \[
    "underscore"
  \],
  "devDependencies": \[
    "jasmine"
  \],
  "missing": {
    "lodash": \[
      "/path/to/my/project/file.using.lodash.js"
    \]
  },
  "using": {
    "react": \[
      "/path/to/my/project/file.using.react.jsx",
      "/path/to/my/project/another.file.using.react.jsx"
    \],
    "lodash": \[
      "/path/to/my/project/file.using.lodash.js"
    \]
  },
  "invalidFiles": {
    "/path/to/my/project/file.having.syntax.error.js": "SyntaxError: <call stack here>"
  },
  "invalidDirs": {
    "/path/to/my/project/folder/without/permission": "Error: EACCES, <call stack here>"
  }
}

-   The `dependencies`, `devDependencies` and `missing` properties have the same meanings in the previous example.
-   The `using` property is a lookup indicating each dependency is used by which files.
-   The value of `missing` and `using` lookup is an array. It means the dependency may be used by many files.
-   The `invalidFiles` property contains the files having syntax error or permission error. The value is the error details. However, only one error is stored in the lookup.
-   The `invalidDirs` property contains the directories having permission error. The value is the error details.

False Alert
-----------

Depcheck just walks through all files and tries to find the dependencies according to some predefined rules. However, the predefined rules may not be enough or may even be wrong.

There may be some cases in which a dependency is being used but is reported as unused, or a dependency is not used but is reported as missing. These are _false alert_ situations.

If you find that depcheck is reporting a false alert, please open an issue with the following information to let us know:

-   The output from `depcheck --json` command. Beautified JSON is better.
-   Which dependencies are considered as false alert?
-   How are you using those dependencies, what do the files look like?

Changelog
---------

We use the GitHub release page to manage changelog.

Contributors
------------

### Code Contributors

This project exists thanks to all the people who contribute. \[Contribute\].

### Financial Contributors

Become a financial contributor and help us sustain our community. \[Contribute\]

#### Individuals

#### Organizations

Support this project with your organization. Your logo will show up here with a link to your website. \[Contribute\]

License
-------

MIT License.
