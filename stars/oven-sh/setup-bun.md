---
project: setup-bun
stars: 520
description: Set up your GitHub Actions workflow with a specific version of Bun
url: https://github.com/oven-sh/setup-bun
---

setup-bun
=========

Download, install, and setup Bun in GitHub Actions.

Usage
-----

\- uses: oven-sh/setup-bun@v2
  with:
    bun-version: latest

Using version file
------------------

\- uses: oven-sh/setup-bun@v2
  with:
    bun-version-file: ".bun-version"

### Using a custom NPM registry

\- uses: oven-sh/setup-bun@v2
  with:
    registry-url: "https://npm.pkg.github.com/"
    scope: "@foo"

If you need to authenticate with a private registry, you can set the `BUN_AUTH_TOKEN` environment variable.

\- name: Install Dependencies
  env:
    BUN\_AUTH\_TOKEN: ${{ secrets.NPM\_TOKEN }}
  run: bun install --frozen-lockfile

### Override download url

If you need to override the download URL, you can use the `bun-download-url` input.

\- uses: oven-sh/setup-bun@v2
  with:
    bun-download-url: "https://github.com/oven-sh/bun/releases/latest/download/bun-linux-x64.zip"

### Node.js not needed

In most cases, you shouldn't need to use the setup-node GitHub Action.

Inputs
------

Name

Description

Default

Examples

`bun-version`

The version of Bun to download and install.

`latest`

`canary`, `1.0.0`, `1.0.x`

`bun-version-file`

The version of Bun to download and install from file.

`undefined`

`package.json`, `.bun-version`, `.tool-versions`

`bun-download-url`

URL to download .zip file for Bun release

`registry-url`

Registry URL where some private package is stored.

`undefined`

`"https://npm.pkg.github.com/"`

`scope`

Scope for private packages.

`undefined`

`"@foo"`, `"@orgname"`

Outputs
-------

Name

Description

Example

`bun-version`

The output from `bun --version`.

`1.0.0`

`bun-revision`

The output from `bun --revision`.

`1.0.0+822a00c4`

`bun-path`

The path to the Bun executable.

`/path/to/bun`

`bun-download-url`

The URL from which Bun was downloaded.

`https://bun.sh/download/latest/linux/x64?avx2=true&profile=false`

`cache-hit`

If the Bun executable was read from cache.

`true`
