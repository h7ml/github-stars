---
project: taze
stars: 3813
description: 🥦 A modern cli tool that keeps your deps fresh
url: https://github.com/antfu-collective/taze
---

🥦 Taze
=======

(/ta:zei/, _fresh_ in Persian)

A modern cli tool that keeps your deps fresh

npx **taze**

or recursively for **monorepos**

npx taze **\-r**

Features
--------

-   Built-in support for monorepos
-   No installation required — `npx taze`
-   Safe by default — updates in the version range you are allowed

Usage
-----

By default, `taze` will only bump versions in the ranges you specified in `package.json` _(which is safe and the default behavior of `npm install`)_

To ignore the ranges, explicitly set the maximum allowed version change.

For example `taze major` will check all changes and bump to the latest stable changes including majors (breaking changes), or `taze minor` that bump to latest minor changes within the same major version.

  

Check for **major** updates  

Check up to **minor** updates  

Check up to **patch** updates  

### Monorepo

`taze` has the built-in first-class monorepo support. Simply adding `-r` will scan the subdirectories that contain `package.json` and update them together. It will handle local private packages automatically.

Configures
----------

See `taze --help` for more details

### Filters

You can filter out packages you want to check for upgrades by `--include` or `--exclude`; they accept string and regex, separated by commas (,).

taze --include lodash,webpack
taze --include /react/ --exclude react-dom # regex is also supported

### Locked Versions

Locked (fixed version without `^` or `~`) packages are skipped by default, use `taze --include-locked` or `taze -l` to show them.

### Peer Dependencies

Bumping version in `peerDependencies` is not enabled by default. Pass `--peer` option to include them in the update process.

taze --peer

### Config file

With `taze.config.js` file, you can configure the same options the command has.

import { defineConfig } from 'taze'

export default defineConfig({
  // ignore packages from bumping
  exclude: \[
    'webpack'
  \],
  // fetch latest package info from registry without cache
  force: true,
  // write to package.json
  write: true,
  // run \`npm install\` or \`yarn install\` right after bumping
  install: true,
  // ignore paths for looking for package.json in monorepo
  ignorePaths: \[
    '\*\*/node\_modules/\*\*',
    '\*\*/test/\*\*',
  \],
  // ignore package.json that in other workspaces (with their own .git,pnpm-workspace.yaml,etc.)
  ignoreOtherWorkspaces: true,
  // override with different bumping mode for each package
  packageMode: {
    'typescript': 'major',
    'unocss': 'ignore',
    // regex starts and ends with '/'
    '/vue/': 'latest'
  },
  // disable checking for "overrides" package.json field
  depFields: {
    overrides: false
  }
})

Alternatives
------------

`taze` is inspired by the following tools.

-   npm-check-updates
-   npm-check

They work well but have different focuses and feature sets, try them out as well :)

Thanks
------

Great thanks to @sinoon who helped a lot with idea brainstorming and feedback discussion.

License
-------

MIT License © 2020 Anthony Fu
