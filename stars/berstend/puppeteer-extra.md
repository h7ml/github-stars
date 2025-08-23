---
project: puppeteer-extra
stars: 7000
description: 💯  Teach puppeteer new tricks through plugins.
url: https://github.com/berstend/puppeteer-extra
---

puppeteer-extra
===============

This is the monorepo for `puppeteer-extra`, a modular plugin framework for `puppeteer`. :-)

🌟 **For the main documentation, please head over to the `puppeteer-extra` package.**

We've also recently introduced support for Playwright, if you're interested in that head over to `playwright-extra`.

Monorepo
--------

**Contributing**

### Contributing

PRs and new plugins are welcome! The plugin API for `puppeteer-extra` is clean and fun to use. Have a look the `PuppeteerExtraPlugin` base class documentation to get going and check out the existing plugins (minimal example is the anonymize-ua plugin) for reference.

We use a monorepo powered by Lerna (and yarn workspaces), ava for testing, the standard style for linting and JSDoc heavily to auto-generate markdown documentation based on code. :-)

**Lerna**

### Lerna

This monorepo is powered by Lerna and yarn workspaces.

#### Initial setup

# Install deps
yarn

# Bootstrap the packages in the current Lerna repo.
# Installs all of their dependencies and links any cross-dependencies.
yarn bootstrap

# Build all TypeScript sources
yarn build

#### Development flow

# Install debug in all packages
yarn lerna add debug

# Install fs-extra to puppeteer-extra-plugin-user-data-dir
yarn lerna add fs-extra --scope=puppeteer-extra-plugin-user-data-dir

# Remove dependency
# https://github.com/lerna/lerna/issues/833
yarn lerna exec --concurrency 1 'yarn remove fs-extra; echo 0'

# Run test in all packages
yarn test

# Update JSDoc based documentation in markdown files
yarn docs

# Upgrade project wide deps like puppeteer
# (We keep the devDependency version blurry)
rm -rf node\_modules
rm -rf yarn.lock
yarn
yarn lerna bootstrap

# Update deps within packages (interactive)
yarn lernaupdate

# If in doubt :-(
yarn lerna exec "rm -f yarn.lock; rm -rf node\_modules; echo 0"
rm -f yarn.lock &&  rm -rf node\_modules && yarn cache clean

# Run tests of specific package
cd packages/puppeteer-extra-plugin-stealth
yarn test

# Run tests of specific stealth evasion
cd packages/puppeteer-extra-plugin-stealth
yarn ava -v ./evasions/user-agent-override/index.test.js

# Test a local monorepo package in an outside folder as it would've been installed from the registry
# Change PACKAGE\_DIR to the path of this monorepo and PACKAGE to the package you wish to install
PACKAGE=puppeteer-extra PACKAGE\_DIR=/Users/foo/puppeteer-extra/packages && yarn remove $(echo $PACKAGE); true && rm -f $(pwd)/$(echo $PACKAGE)\-latest.tgz && yarn --cwd $(echo $PACKAGE\_DIR)/$(echo $PACKAGE) pack --filename $(pwd)/$(echo $PACKAGE)\-latest.tgz && YARN\_CACHE\_FOLDER=/tmp/yarn yarn add file:$(pwd)/$(echo $PACKAGE)\-latest.tgz && rm -rf /tmp/yarn

#### Publishing

# make sure you're signed into npm before publishing
# yarn publishing is broken so lerna uses npm
npm whoami

# ensure everything is up2date and peachy
yarn
yarn bootstrap
yarn lerna link
yarn build
yarn test

# Phew, let's publish these packages!
# - Will publish all changed packages
# - Will ask for new pkg version per package
# - Will updated inter-package dependency versions automatically
yarn lerna publish

# Fix new dependency version symlinks
yarn bootstrap && yarn lerna link
