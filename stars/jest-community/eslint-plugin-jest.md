---
project: eslint-plugin-jest
stars: 1164
description: ESLint plugin for Jest 
url: https://github.com/jest-community/eslint-plugin-jest
---

eslint-plugin-jest
==================

ESLint plugin for Jest

Installation
------------

yarn add --dev eslint eslint-plugin-jest

**Note:** If you installed ESLint globally then you must also install `eslint-plugin-jest` globally.

Usage
-----

If you're using flat configuration:

With flat configuration, just import the plugin and away you go:

const pluginJest \= require('eslint-plugin-jest');

module.exports \= \[
  {
    // update this to match your test files
    files: \['\*\*/\*.spec.js', '\*\*/\*.test.js'\],
    plugins: { jest: pluginJest },
    languageOptions: {
      globals: pluginJest.environments.globals.globals,
    },
    rules: {
      'jest/no-disabled-tests': 'warn',
      'jest/no-focused-tests': 'error',
      'jest/no-identical-title': 'error',
      'jest/prefer-to-have-length': 'warn',
      'jest/valid-expect': 'error',
    },
  },
\];

With legacy configuration, add `jest` to the plugins section of your `.eslintrc` configuration file. You can omit the `eslint-plugin-` prefix:

{
  "plugins": \["jest"\],
  "env": {
    "jest/globals": true
  },
  "rules": {
    "jest/no-disabled-tests": "warn",
    "jest/no-focused-tests": "error",
    "jest/no-identical-title": "error",
    "jest/prefer-to-have-length": "warn",
    "jest/valid-expect": "error"
  }
}

Note

You only need to explicitly include our globals if you're not using one of our shared configs

#### Aliased Jest globals

You can tell this plugin about any global Jests you have aliased using the `globalAliases` setting:

{
  "settings": {
    "jest": {
      "globalAliases": {
        "describe": \["context"\],
        "fdescribe": \["fcontext"\],
        "xdescribe": \["xcontext"\]
      }
    }
  }
}

#### Aliased `@jest/globals`

You can tell this plugin to treat a different package as the source of Jest globals using the `globalPackage` setting:

{
  "settings": {
    "jest": {
      "globalPackage": "bun:test"
    }
  }
}

Warning

While this can be used to apply rules when using alternative testing libraries and frameworks like `bun`, `vitest` and `node`, there's no guarantee the semantics this plugin assumes will hold outside of Jest

### Running rules only on test-related files

The rules provided by this plugin assume that the files they are checking are test-related. This means it's generally not suitable to include them in your top-level configuration as that applies to all files being linted which can include source files.

For `.eslintrc` configs you can use overrides to have ESLint apply additional rules to specific files:

{
  "extends": \["eslint:recommended"\],
  "overrides": \[
    {
      "files": \["test/\*\*"\],
      "plugins": \["jest"\],
      "extends": \["plugin:jest/recommended"\],
      "rules": { "jest/prefer-expect-assertions": "off" }
    }
  \],
  "rules": {
    "indent": \["error", 2\]
  }
}

For `eslint.config.js` you can use `files` and `ignores`:

const jest \= require('eslint-plugin-jest');

module.exports \= \[
  ...require('@eslint/js').configs.recommended,
  {
    files: \['test/\*\*'\],
    ...jest.configs\['flat/recommended'\],
    rules: {
      ...jest.configs\['flat/recommended'\].rules,
      'jest/prefer-expect-assertions': 'off',
    },
  },
  // you can also configure jest rules in other objects, so long as some of the \`files\` match
  {
    files: \['test/\*\*'\],
    rules: { 'jest/prefer-expect-assertions': 'off' },
  },
\];

### Jest `version` setting

The behaviour of some rules (specifically `no-deprecated-functions`) change depending on the version of Jest being used.

By default, this plugin will attempt to determine to locate Jest using `require.resolve`, meaning it will start looking in the closest `node_modules` folder to the file being linted and work its way up.

Since we cache the automatically determined version, if you're linting sub-folders that have different versions of Jest, you may find that the wrong version of Jest is considered when linting. You can work around this by providing the Jest version explicitly in nested ESLint configs:

{
  "settings": {
    "jest": {
      "version": 27
    }
  }
}

To avoid hard-coding a number, you can also fetch it from the installed version of Jest if you use a JavaScript config file such as `.eslintrc.js`:

module.exports \= {
  settings: {
    jest: {
      version: require('jest/package.json').version,
    },
  },
};

Shareable configurations
------------------------

Note

`eslint.config.js` compatible versions of configs are available prefixed with `flat/` and may be subject to small breaking changes while ESLint v9 is being finalized.

### Recommended

This plugin exports a recommended configuration that enforces good testing practices.

To enable this configuration with `.eslintrc`, use the `extends` property:

{
  "extends": \["plugin:jest/recommended"\]
}

To enable this configuration with `eslint.config.js`, use `jest.configs['flat/recommended']`:

const jest \= require('eslint-plugin-jest');

module.exports \= \[
  {
    files: \[
      /\* glob matching your test files \*/
    \],
    ...jest.configs\['flat/recommended'\],
  },
\];

### Style

This plugin also exports a configuration named `style`, which adds some stylistic rules, such as `prefer-to-be-null`, which enforces usage of `toBeNull` over `toBe(null)`.

To enable this configuration use the `extends` property in your `.eslintrc` config file:

{
  "extends": \["plugin:jest/style"\]
}

To enable this configuration with `eslint.config.js`, use `jest.configs['flat/style']`:

const jest \= require('eslint-plugin-jest');

module.exports \= \[
  {
    files: \[
      /\* glob matching your test files \*/
    \],
    ...jest.configs\['flat/style'\],
  },
\];

### All

If you want to enable all rules instead of only some you can do so by adding the `all` configuration to your `.eslintrc` config file:

{
  "extends": \["plugin:jest/all"\]
}

To enable this configuration with `eslint.config.js`, use `jest.configs['flat/all']`:

const jest \= require('eslint-plugin-jest');

module.exports \= \[
  {
    files: \[
      /\* glob matching your test files \*/
    \],
    ...jest.configs\['flat/all'\],
  },
\];

While the `recommended` and `style` configurations only change in major versions the `all` configuration may change in any release and is thus unsuited for installations requiring long-term consistency.

Rules
-----

💼 Configurations enabled in.  
⚠️ Configurations set to warn in.  
✅ Set in the `recommended` configuration.  
🎨 Set in the `style` configuration.  
🔧 Automatically fixable by the `--fix` CLI option.  
💡 Manually fixable by editor suggestions.

Name                             

Description

💼

⚠️

🔧

💡

consistent-test-it

Enforce `test` and `it` usage conventions

🔧

expect-expect

Enforce assertion to be made in a test body

✅

max-expects

Enforces a maximum number assertion calls in a test body

max-nested-describe

Enforces a maximum depth to nested describe calls

no-alias-methods

Disallow alias methods

✅

🔧

no-commented-out-tests

Disallow commented out tests

✅

no-conditional-expect

Disallow calling `expect` conditionally

✅

no-conditional-in-test

Disallow conditional logic in tests

no-confusing-set-timeout

Disallow confusing usages of jest.setTimeout

no-deprecated-functions

Disallow use of deprecated functions

✅

🔧

no-disabled-tests

Disallow disabled tests

✅

no-done-callback

Disallow using a callback in asynchronous tests and hooks

✅

💡

no-duplicate-hooks

Disallow duplicate setup and teardown hooks

no-export

Disallow using `exports` in files containing tests

✅

no-focused-tests

Disallow focused tests

✅

💡

no-hooks

Disallow setup and teardown hooks

no-identical-title

Disallow identical titles

✅

no-interpolation-in-snapshots

Disallow string interpolation inside snapshots

✅

no-jasmine-globals

Disallow Jasmine globals

✅

🔧

no-large-snapshots

Disallow large snapshots

no-mocks-import

Disallow manually importing from `__mocks__`

✅

no-restricted-jest-methods

Disallow specific `jest.` methods

no-restricted-matchers

Disallow specific matchers & modifiers

no-standalone-expect

Disallow using `expect` outside of `it` or `test` blocks

✅

no-test-prefixes

Require using `.only` and `.skip` over `f` and `x`

✅

🔧

no-test-return-statement

Disallow explicitly returning from tests

no-untyped-mock-factory

Disallow using `jest.mock()` factories without an explicit type parameter

🔧

padding-around-after-all-blocks

Enforce padding around `afterAll` blocks

🔧

padding-around-after-each-blocks

Enforce padding around `afterEach` blocks

🔧

padding-around-all

Enforce padding around Jest functions

🔧

padding-around-before-all-blocks

Enforce padding around `beforeAll` blocks

🔧

padding-around-before-each-blocks

Enforce padding around `beforeEach` blocks

🔧

padding-around-describe-blocks

Enforce padding around `describe` blocks

🔧

padding-around-expect-groups

Enforce padding around `expect` groups

🔧

padding-around-test-blocks

Enforce padding around `test` and `it` blocks

🔧

prefer-called-with

Suggest using `toBeCalledWith()` or `toHaveBeenCalledWith()`

prefer-comparison-matcher

Suggest using the built-in comparison matchers

🔧

prefer-each

Prefer using `.each` rather than manual loops

prefer-ending-with-an-expect

Prefer having the last statement in a test be an assertion

prefer-equality-matcher

Suggest using the built-in equality matchers

💡

prefer-expect-assertions

Suggest using `expect.assertions()` OR `expect.hasAssertions()`

💡

prefer-expect-resolves

Prefer `await expect(...).resolves` over `expect(await ...)` syntax

🔧

prefer-hooks-in-order

Prefer having hooks in a consistent order

prefer-hooks-on-top

Suggest having hooks before any test cases

prefer-importing-jest-globals

Prefer importing Jest globals

🔧

prefer-jest-mocked

Prefer `jest.mocked()` over `fn as jest.Mock`

🔧

prefer-lowercase-title

Enforce lowercase test names

🔧

prefer-mock-promise-shorthand

Prefer mock resolved/rejected shorthands for promises

🔧

prefer-snapshot-hint

Prefer including a hint with external snapshots

prefer-spy-on

Suggest using `jest.spyOn()`

🔧

prefer-strict-equal

Suggest using `toStrictEqual()`

💡

prefer-to-be

Suggest using `toBe()` for primitive literals

🎨

🔧

prefer-to-contain

Suggest using `toContain()`

🎨

🔧

prefer-to-have-length

Suggest using `toHaveLength()`

🎨

🔧

prefer-todo

Suggest using `test.todo`

🔧

require-hook

Require setup and teardown code to be within a hook

require-to-throw-message

Require a message for `toThrow()`

require-top-level-describe

Require test cases and hooks to be inside a `describe` block

valid-describe-callback

Enforce valid `describe()` callback

✅

valid-expect

Enforce valid `expect()` usage

✅

🔧

valid-expect-in-promise

Require promises that have expectations in their chain to be valid

✅

valid-title

Enforce valid titles

✅

🔧

### Requires Type Checking

Name          

Description

💼

⚠️

🔧

💡

unbound-method

Enforce unbound methods are called with their expected scope

In order to use the rules powered by TypeScript type-checking, you must be using `@typescript-eslint/parser` & adjust your eslint config as outlined here.

Note that unlike the type-checking rules in `@typescript-eslint/eslint-plugin`, the rules here will fallback to doing nothing if type information is not available, meaning it's safe to include them in shared configs that could be used on JavaScript and TypeScript projects.

Also note that `unbound-method` depends on `@typescript-eslint/eslint-plugin`, as it extends the original `unbound-method` rule from that plugin.

Credit
------

-   eslint-plugin-mocha
-   eslint-plugin-jasmine

Related Projects
----------------

### eslint-plugin-jest-extended

This is a sister plugin to `eslint-plugin-jest` that provides support for the matchers provided by `jest-extended`.

https://github.com/jest-community/eslint-plugin-jest-extended

### eslint-plugin-jest-formatting

This project aims to provide formatting rules (auto-fixable where possible) to ensure consistency and readability in jest test suites.

https://github.com/dangreenisrael/eslint-plugin-jest-formatting

### eslint-plugin-istanbul

A set of rules to enforce good practices for Istanbul, one of the code coverage tools used by Jest.

https://github.com/istanbuljs/eslint-plugin-istanbul
