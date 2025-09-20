---
project: awesome-eslint
stars: 4632
description: A list of awesome ESLint plugins, configs, etc.
url: https://github.com/dustinspecker/awesome-eslint
---

Awesome ESLint
==============

> A list of awesome ESLint configs, plugins, etc.

If you want to contribute, please read the contribution guidelines.

Contents
--------

-   Configs
    -   Configs by Well-Known Companies/Organizations
    -   Other Prominent Configs (100 stars or so)
    -   Other Configs
-   Preconfigured Configs with ESLint Set up
-   Plugins
    -   Code Quality
    -   Compatibility
    -   CSS in JS
    -   Deprecation
    -   Embedded
    -   Frameworks
    -   Languages and Environments
    -   Libraries
    -   Misc
    -   Practices and Specific ES Features
    -   Performance
    -   Security
    -   Style
    -   Testing Tools
-   Parsers
-   Formatters
-   Globals
-   Tools
-   Developing for ESLint
-   Tutorials
-   Installation and Setup

Configs
-------

### Configs by Well-Known Companies/Organizations

-   Airbnb - Shareable config for Airbnb's style guide.
-   Airbnb-babel - Airbnb's ESLint config with Babel Support.
-   Alloy - Progressive ESLint config for your React/Vue/TypeScript projects.
-   ESLint - Contains the ESLint configuration used for projects maintained by the ESLint team.
-   Facebook - Sharable config for Facebook's style guide.
-   Feedzai - Feedzai's shareable config for JavaScript/React projects.
-   Shopify - Shareable config for Shopify's style guide.
-   Wikimedia - Shareable config for Wikimedia's style guide, used by MediaWiki.

### Other Prominent Configs (100 stars or so)

-   Auto - Automatically configure ESLint based on your project's dependencies.
-   Canonical - Shareable config for Canonical style guide.

-   Standard - Shareable config for JavaScript Standard Style.
-   XO - Shareable config for XO.
-   Antfu Eslint Config - Anthony's ESLint config preset.

### Other Configs

-   Adjunct - A reasonable collection of plugins to use alongside your main ESLint configuration.
-   Ash-Nazg - One config to rule them all!
-   Cecilia - ESLint configuration for awesome projects.
-   clean-typescript - Enforce classic JavaScript featuress in TypeScript codebase by banning excessive keywords.
-   Hardcore - The most strict (but practical) ESLint config out there.
-   Problems - Shareable config that only catches actual problems, and doesn't enforce stylistic preferences.
-   Supermind - Shareable config for Supermind style.
-   Sheriff - Comprehensive and highly opinionated Eslint configuration. Typescript oriented.

Preconfigured Configs with ESLint Set up
----------------------------------------

-   Node.js Standard Style - Node.js core config.
-   eslint-config-prettier - Prettier config for ESlint maintained by Prettier team.
-   Standard - JavaScript Standard Style.
-   Superlint - JavaScript Supermind Style.
-   XO - JavaScript happiness style linter ❤️.

Plugins
-------

### Code Quality

-   depend - Helps detect dependency tree bloat and redundant polyfills.
-   GitHub - Misc. rules from GitHub.
-   SonarJS - Rules detecting bugs and suspicious patterns.
-   Unicorn - Various awesome ESLint rules.
-   @mysticatea/eslint-plugin - Misc. rules.
-   @brettz9/eslint-plugin - Misc. rules. of `@mysticatea` without the personal config.
-   De Morgan - Transforms logical expressions in code to make them easier to understand.
-   eslint-plugin-code-complete - A custom ESLint plugin that enforces principles of clean, maintainable software design — inspired by Code Complete.

### Compatibility

-   Compat - Lint browser compatibility of APIs used (caniuse as an ESLint plugin).
-   ecmascript-compat - Disable ECMAScript language features not supported by your browserslist targets.
-   es-x - Disable specific ECMAScript language versions or individual features. Properly maintained fork of no longer maintained `eslint-plugin-es`.
-   es5 - ESLint plugin for ES5 users (forbid ES2015+ usage).
-   ie11 - Detect unsupported ES6 features in IE11.

### CSS in JS

-   CSS-modules - Lint undefined or unused rules for css modules.
-   Emotion - ESLint rules for emotion.
-   Styled Components
    -   Better Styled Components - Auto fixable ESlint's rules for styled components.
    -   styled-components-a11y - A11y for Styled Components.
-   vanilla-extract - An ESLint plugin for enforcing CSS property ordering in vanilla-extract CSS styles.

### Deprecation

-   deprecate - Mark functions or modules as deprecated and get lint messages when they are used.
-   disable - Disable specified plugins using file path patterns and inline comments.

### Embedded

-   HTML - Linting for JavaScript inside of HTML `<script>` tags.
-   Markdown - Linting for JavaScript inside of Markdown.

### Frameworks

-   Angular - Linting rules for Angular (v2+).
-   AngularJS - Linting rules to adhere to the John Papa's AngularJS Styleguide.
-   Astro - Plugin for Astro components.
-   Backbone - Linting rules for Backbone.
-   Ember - Linting rules for Ember.
-   Hapi - Linting rules for hapi.
-   Meteor - Meteor specific linting rules for ESLint.
-   React
    -   JSX a11y - Accessibility rules on JSX elements.
    -   React - Linting rules for React and JSX.
    -   React Hooks - Linting rules for React Hooks.
    -   React Native - React Native specific linting rules.
    -   React-Redux - React-Redux specific linting rules.
    -   React Refresh - Improve HMR experience when using Vite.
-   Solid - Linting rules for Solid and JSX.
-   Svelte - Linting rules for Svelte v3 Components.
-   Vue
    -   VueJS - Plugin for VueJS.
    -   VueJS Scoped CSS - Plugin for Scoped CSS in VueJS.

### Languages and Environments

-   Babel - Adds replacements for built-in rules to include Babel features.
-   eslint-plugin-eslint-plugin - An ESLint plugin for linting ESLint plugins.
-   Flow
    -   Flow - Flow type linting rules.
    -   Flow Errors - Run Flow as an ESLint plugin.
-   HTML - ESLint plugin for HTML.
-   JSON
    -   JSON - Lint your JSON files.
    -   JSON, package.json - Lint, format, and auto-fix your JSON files. Sort your `package.json`.
    -   JSON with Comments - ESLint plugin for JSON, JSONC and JSON5.
    -   JSON Schema - Validates data defined in JavaScript, JSON, YAML and TOML using JSON Schema Validator.
-   MDX - ESLint Parser/Plugin for MDX.
-   N - Additional ESLint's rules for Node.js. Properly maintained fork of no longer maintained `eslint-plugin-node`.
-   SQL - SQL linting rules for ESLint.
-   TOML - ESLint plugin for TOML.
-   TypeScript - Linting rules for TypeScript.
-   YAML - ESLint plugin for YAML.

### Libraries

-   GraphQL
    -   dotansimha/graphql-eslint - Validates, prettifies and checks your GraphQL operations and GraphQL schema for best-practices.
    -   apollostack/eslint-plugin-graphql - Check your GraphQL query strings against a schema.
-   TypeGraphQL - Linting rules for TypeGraphQL, targeted at finding common mistakes.
-   jQuery - Linting rules for jQuery, including versioned configs for deprecated features.
-   JSDoc - Linting rules for JSDoc comments (including the JavaScript within `@example`).
-   Lodash
    -   Lodash - Lodash specific linting rules.
    -   Lodash/fp - Lodash/fp specific linting rules.
    -   Lodash template - Plugin for Lodash template/Underscore template.
    -   Microtemplates (Used in Lodash and Underscore.js)
-   Mongodb - Mongodb native Node.js driver linting rules.
-   Ramda - Ramda specific linting rules.
-   RequireJS - Linting rules for RequireJS.
-   Tailwind CSS - Linting rules for Tailwind CSS classnames.

### Misc

-   Diff - Run ESLint on your changed lines only. Also supports CI!
-   Misc - Miscellaneous rules including rules for creating custom checks and wrapping (modifying) third-party rules.
-   Notice - An eslint rule that checks the top of files and fixes them too!
-   Only-Error - Convert all rules to errors.
-   Only-Warn - Convert all rules to warnings.
-   PutOut - an ESLint plugin integrates putout linter into ESLint.
-   TypeLint - Introduces types, based on existing schemas (Swagger, Redux) and linting access to object properties, preventing `undefined` errors.
-   Woke - Helps catch insensitive words, promoting an inclusive codebase.

### Practices and Specific ES Features

-   array-func - Avoid redundancy when using es2015 array methods and functions.
-   arrow functions - ESLint rules to ensure proper arrow function definitions.
-   boundaries - Ensures that your architecture boundaries are respected by the elements in your project checking file structure and dependencies.
-   @eslint-community/eslint-plugin-eslint-comments - Best practices about ESLint directive comments (`/*eslint-disable*/`, etc.). Properly maintained fork of no longer maintained `eslint-plugin-eslint-comments`.
-   eslint-plugin-error-cause - A plugin to preserve original error context when re-throwing exceptions.
-   eslint-plugin-hexagonal-architecture - A plugin that helps you to enforce hexagonal architecture best practices.
-   eslint-plugin-write-good-comments - Enforce good writing style in comments.
-   eslint-plugin-exception-handling - Lints unhandled functions that might throw errors.
-   fp - ESLint rules for functional programming.
-   functional - ESLint rules to disable mutation and promote fp in JavaScript and TypeScript.
-   Immutable - Disable all mutation in JavaScript.
-   import - Linting of ES2015+ import/export syntax, and prevent issues with misspelling of file paths and import names.
-   import-x - Linting of ES2015+ import/export syntax, and prevent issues with misspelling of file paths and import names. Lightweight fork of `eslint-plugin-import`, but which breaks backwards compatibility.
-   Math - ESLint plugin related to Math object and Number.
-   new-with-error - Require errors to be thrown using `new`.

-   no-argument-spread - Lints against expressions like `Math.max(...args)` that can lead to a stack overflow for large arrays.
-   no-comments - Prevents leaking comments into production if bundler is not used and stops developers from commenting out old lines of code.
-   no-constructor-bind - Encourages use of class properties by reporting use of `this` with `bind` or setting state in constructors.
-   no-inferred-method-name - Custom rule for ESLint that checks for inferred method names within object literals.
-   no-loops - It's 2019 and you still use loops?
-   no-restricted-syntax - Show queried syntax's content in messages.
-   no-use-extend-native - Prevent using extended native objects.
-   Promise - Best practices when working with promises.
-   pure - Enforce pure functions (without side effects).
-   ReDoS - ESLint plugin for finding possible ReDoS vulnerabilities.
-   ReDoSDetector - ESLint plugin for finding possible ReDoS vulnerabilities.
-   RegExp - ESLint plugin for finding regexp mistakes and style guide violations.
-   sort-keys-fix - Adds fixer for ESLint `sort-keys` rule.
-   this - Write pure functions, don't allow `this`.
-   toplevel - An eslint plugin for disallow side effect at module toplevel.

### Performance

-   DOM
-   Optimize Regex - Optimize regex literals.
-   Perf-Standard plugin and Config

### Security

-   no-secrets - An eslint plugin that detects potential secrets/credentials.
-   no-unsanitized - Checks for `innerHTML`, `outerHTML`, etc.
-   pii - Checks and enforces PII Compliance of the code. i.e. no email address, birth date, IP address or phone number in comments or string literals.
-   Security - ESLint rules for Node Security.
-   xss - Tries to detect XSS issues in codebase before they end up in production.

### Style

-   ESLint Stylistic - Formatting and stylistic ESLint core rules moved to this project and are maintained by the community.
-   const case - Enforce capitalization of constant primitive literals.
-   editorconfig - Derive rules from `.editorconfig`.
-   filenames - Ensure consistent filenames for your JavaScript files. No longer maintained and does not work with ESlint 9 at all.
-   Simple import sort - Easy autofixable import sorting.
-   perfectionist sorting - Sort objects, imports, TypeScript types, enums, JSX props, etc.
-   split-and-sort-imports - Sorts imports and splits 'multiple' imports into single line imports.
-   Switch case - Switch-case-specific linting rules for ESLint.
-   padding - Allows/disallows padding between statements.
-   paths - Use paths from tsconfig/jsconfig and auto fix relative paths to aliases.
-   @gitbutler/no-relative-imports - Use paths from tsconfig and auto fix relative paths to aliases. Observes tsconfig inheritance.

### Testing Tools

-   AVA - Linting rules for AVA.
-   Chai
    
    -   expect practices
    -   with unused expressions
    -   permitted keywords
    -   with chai-as-promised plugin
    
    -   globals
-   Cucumber - Linting rules for Cucumber.
-   Cypress - Linting rules for Cypress.
-   Jasmine - Linting rules for Jasmine.
-   Jest
    -   Enforcing practices - Linting rules for Jest.
    -   Enforcing consistent formatting - Formatting rules for Jest.
    -   Jest-async - Async linting rule for Jest.
    -   Jest-DOM - Linting rules for Jest-DOM.
-   Mocha
    -   Enforcing practices - Linting rules for Mocha.
    -   Enforcing manageability
-   Playwright - Linting rules for Playwright.
-   QUnit - Linting rules for QUnit.
-   TestCafe-Community - TestCafe linting rules with env globals (fork from TestCafe globals).
-   Testing Library - Linting rules for Testing Library.

Parsers
-------

-   babel-eslint-parser - Allows you to lint ALL valid Babel code with the fantastic ESLint.
-   TypeScript - A TypeScript parser that produces output compatible with ESLint.
-   BrightScript - BrightScript plugin for Roku development. Includes Parser and Rules.
-   GraphQL - Parser for the GraphQL AST. Includes parser, plugin, processor (for non-graphql files) and rules.

Formatters
----------

-   html - A enhanced ESLint formatter.
-   badger - Make SVG-based badges summarizing ESLint results (e.g., for use on a README).
-   git-log - ESLint Formatter featuring Git Author, Date, and Hash.
-   github - See ESLint errors and warnings directly in pull requests.
-   gitlab - Output ESLint results in the GitLab code quality results.
-   mo - Good-lookin' ESLint formatter and also for delightful reading experience.
-   SARIF - Generate a results in a SARIF format so it can be imported into tools like GitHub Advanced Security.
-   summary-chart - Format ESLint output into a bar chart.

Globals
-------

-   confusing-browser-globals - A curated list of browser globals that commonly cause confusion and are not recommended to use without an explicit window. qualifier.
-   ES and browser globals (originally from ESLint)
-   chai globals
-   TestCafe globals - `fixture` & `test` globals for TestCafe.

Tools
-----

-   es-file-traverse - Obtain a list of only those files which are in use based on imports and/or requires from an entry file or files; list passable to ESLint. Intended esp. for linting 3rd party dependencies.
-   eslint-find-rules - Find built-in ESLint rules you don't have in your custom config.
-   eslint-index - CLI for finding and managing rules in ESLint config files.
-   eslint-interactive - The CLI tool to fix huge number of ESLint errors.
-   eslint-multiplexer - Multiplex eslint results and merge results for common files.
-   eslint-nibble - Ease into ESLint, by fixing one rule at a time.
-   eslint-plugin-rule-adoption - An eslint plugin for incremental rule adoption, when `--fix` and codemods don't cut it.
-   eslint-rule-documentation - Find the url for the documentation of an ESLint rule.
-   eslint-watch - Run ESLint with watch mode.
-   codacy-eslint - Docker used at Codacy to run ESLint.
-   esprint - Run ESLint across multiple threads.
-   generator-eslint - Generate ESLint plugin and rules with Yeoman.
-   editor-info - Detect whether one is within an editor/IDE and which type, allowing one to tweak ESLint configuration accordingly.
-   eslint-dashboard - Interactive ESLint workflow that lives in your terminal.
-   eslint-remote-tester - CLI tool for testing given ESlint rules against multiple repositories at once.

Developing for ESLint
---------------------

-   eslint-doc-generator - Generate documentation for your ESLint plugin including a rules table for your readme and header for your rule docs.
-   eslint-docgen - Automatically generate ESLint plugin documentation from rule metadata and test cases.

Tutorials
---------

-   Creating an ESLint Plugin - Article walking through the creation of an ESLint rule and plugin.
-   Lint Like It's 2015 - Article walking through the benefits of using ESLint.
-   Writing a rule to spot undeclared props hiding in plain sight - Article about creating rules that require scope analysis.
-   Dear Old ESLint - Quick intro article on ESLint.

Installation and Setup
----------------------

-   Lintier - CLI to quickly scaffold an ESLint & Prettier setup in a TypeScript project.
