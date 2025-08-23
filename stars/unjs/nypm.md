---
project: nypm
stars: 603
description: 🌈 Unified Package Manager for Node.js (npm, pnpm, yarn), Bun and Deno
url: https://github.com/unjs/nypm
---

🌈 nypm
=======

🌈 Unified Package Manager for Node.js (npm, pnpm, yarn), Bun and Deno.

✅ Supports npm, yarn, pnpm, bun and deno out of the box with a unified API.

✅ Provides an **API interface** to interact with package managers.

✅ **Autodetects** project's package manager using `package.json` and known lockfiles.

✅ **corepack** integration for **pnpm** and **yarn**.

`nypm` command
--------------

**Install dependencies:**

npx nypm i

**Add a dependency:**

npx nypm add defu

**Remove a dependency:**

npx nypm remove defu

API Usage
---------

Install package:

# ✨ Auto-detect
npx nypm install nypm

# npm
npm install nypm

# yarn
yarn add nypm

# pnpm
pnpm install nypm

# bun
bun install nypm

# deno
deno install nypm

Import:

// ESM import
import { addDependency } from "nypm";

// or dynamic import
const { addDependency } \= await import("nypm");

### `addDependency(name, options)`

Adds dependency to the project.

### `addDevDependency(name, options)`

Adds dev dependency to the project.

### `detectPackageManager(cwd, options)`

Detect the package manager used in a directory (and up) by checking various sources:

1.  Use `packageManager` field from package.json
2.  Known lock files and other files

### `ensureDependencyInstalled(name, options)`

Ensures dependency is installed.

### `installDependencies(options)`

Installs project dependencies.

### `removeDependency(name, options)`

Removes dependency from the project.

### `dedupeDependencies(options)`

Dedupe project dependencies.

Note

For `bun` and `deno` it will remove the lockfile and reinstall all dependencies.

### `runScript(name, options)`

Runs a script defined in the `package.json` file.

### `installDependenciesCommand(<pm>, { short?, frozenLockFile? })`

Get the command to install dependencies with the package manager.

### `addDependencyCommand(<pm>, <name>, { dev?, global?, workspace?, yarnBerry?, short? })`

Get the command to add a dependency with the package manager.

### `runScriptCommand(<pm>, <name>, { args? })`

Get the command to run a script with the package manager.

### `dlxCommand(<pm>, <name>, { args?, short? })`

Get the command to download and execute a package with the package manager.

💻 Development
--------------

-   Clone this repository
-   Play Nyan Cat in the background (really important!)
-   Enable Corepack using `corepack enable`
-   Install dependencies using `pnpm install`
-   Run interactive tests using `pnpm dev`

Related Projects
----------------

NYPM is inspired from previous attempts and projects for unifying package manager experience.

-   pi0/yarnpm
-   unjs/lmify
-   antfu/ni
-   antfu/install-pkg
-   egoist/dum
-   nodejs/corepack

License
-------

Made with 💛

Published under MIT License.
