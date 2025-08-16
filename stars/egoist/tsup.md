---
project: tsup
stars: 10692
description: The simplest and fastest way to bundle your TypeScript libraries.
url: https://github.com/egoist/tsup
---

Warning

This project is not actively maintained anymore. Please consider using tsdown instead. Read more in the migration guide.

tsup
====

Bundle your TypeScript library with no config, powered by esbuild.

👀 What can it bundle?
----------------------

Anything that's supported by Node.js natively, namely `.js`, `.json`, `.mjs`. And TypeScript `.ts`, `.tsx`. CSS support is experimental.

⚙️ Install
----------

Install it locally in your project folder:

npm i tsup -D
# Or Yarn
yarn add tsup --dev
# Or pnpm
pnpm add tsup -D

You can also install it globally but it's not recommended.

📖 Usage
--------

### Bundle files

tsup \[...files\]

Files are written into `./dist`.

You can bundle multiple files in one go:

tsup src/index.ts src/cli.ts

This will output `dist/index.js` and `dist/cli.js`.

📚 Documentation
----------------

For complete usages, please dive into the docs.

For all configuration options, please see the API docs.

💬 Discussions
--------------

Head over to the discussions to share your ideas.

Sponsors
--------

Project Stats
-------------

License
-------

MIT © EGOIST
