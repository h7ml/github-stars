---
project: vite-ts-lib-starter
stars: 16
description: A simple library template starter for Vite with TypeScript, Prettier, Vitest, Bun, Renovate and np.
url: https://github.com/matronator/vite-ts-lib-starter
---

Vite TypeScript Library Starter
===============================

A starter template to use for developing libraries with Vite and TypeScript.

Tech-stack
----------

-   Bun - A package manager for the web (faster alternative to npm and yarn)
-   Vite - A next-generation front-end tooling
-   TypeScript - A typed superset of JavaScript
-   Vitest - A test runner for Vite
-   Prettier - An opinionated code formatter
-   Renovate - Automated dependency updates
-   np - A better `npm publish`

Installation
------------

1.  Clone this repository, or
2.  Click on "Use this template" button, or
3.  Download the repository as a ZIP file, or
4.  Use degit, like this:

```
bunx degit matronator/vite-ts-lib-starter my-new-library
```

After installation
------------------

1.  Change the `package.json` file to match your library's name, description, author, etc.
2.  Change the `outFile` field in the `dts-bundle-generator.config.js` file to match your library's name.
3.  Replace the logo with your own.
4.  Modify `FUNDING.yml` in the `.github` folder with your own values or remove it completely.
5.  Replace the `README.md` file with your own.
6.  Change the name in the `LICENSE.md` file.
7.  Replace the `CHANGELOG.md` file with your own.
8.  Start creating your library in the `src` folder.
9.  Write some tests in the `tests` folder.
10.  When you're ready to publish your library, run `npm run build` to generate the production files.
11.  Publish your library to npm with either `npm publish`, or `npm run release` to use `np` for a better publishing experience.
