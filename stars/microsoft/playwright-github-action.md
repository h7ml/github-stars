---
project: playwright-github-action
stars: 352
description: Run Playwright tests on GitHub Actions
url: https://github.com/microsoft/playwright-github-action
---

Playwright GitHub Action
========================

Set up GitHub Actions to run cross-browser tests on Chromium, WebKit and Firefox with Playwright.

❌ You don't need this GitHub Action
-----------------------------------

**We recommend using the Playwright CLI instead of this GitHub Action**.

One of the reasons for deprecating the GitHub Actions is that it doesn't know which version of Playwright is installed, which then requires installing many more dependencies to ensure support.

We highly discourage the use of the GitHub Action. See next section for using the CLI.

✅ Use the Playwright CLI
------------------------

Starting with Playwright v1.8.0 it includes a CLI that installs all required browser dependencies.

### To install dependencies with a CLI:

npx playwright install --with-deps # install browsers + dependencies for all browsers
npx playwright install chromium --with-deps # install browsers + dependencies for Chromium only

### Playwright CLI with GitHub Actions CI

Following is an example usage of the Playwright CLI with a GitHub Actions workflow file. It shows a `tests_e2e` job which includes steps in which the Playwright CLI invokes the installation of required dependencies (headless browsers, etc) and then invokes the actual npm run script `npm run test:e2e` for the Playwright test runner:

jobs:
  tests\_e2e:
    name: Run end-to-end tests
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
      - name: Install dependencies
        run: npm ci
      - name: Install playwright browsers
        run: npx playwright install --with-deps
      - name: Run tests
        run: npx playwright test

If something doesn't work, please let us know!

⚠️ GitHub Action Usage (deprecated)

Add `uses: microsoft/playwright-github-action@v1` to the GitHub workflow definition before running your tests.

on:
  push:
    branches:
    - main

jobs:
  e2e-tests:
    runs-on: ubuntu-latest # or macos-latest, windows-latest

    steps:
      - uses: actions/checkout@v2

      - uses: actions/setup-node@v1

      - uses: microsoft/playwright-github-action@v1

      - name: Install dependencies and run tests
        run: npm install && npm test

### Upload artifacts

This GitHub Action can be combined with the Upload Artifact action to upload test artifacts (like screenshots or logs).

steps:
- uses: microsoft/playwright-github-action@v1

- name: Install dependencies and run tests
  run: npm install && npm test

- uses: actions/upload-artifact@v2
  if: ${{ always() }}
  with:
    name: test-artifacts
    path: path/to/artifacts

### Run in headful mode

This GitHub Action can also execute tests in headful mode. To do this, use `xvfb-run` on a Linux agent.

# Windows/macOS
npm test

# Linux
xvfb-run --auto-servernum -- npm test

Resources
---------

-   Get started with Playwright
-   Playwright API reference
-   Development docs
