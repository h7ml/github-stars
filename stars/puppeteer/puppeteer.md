---
project: puppeteer
stars: 92507
description: JavaScript API for Chrome and Firefox
url: https://github.com/puppeteer/puppeteer
---

Puppeteer
=========

> Puppeteer is a JavaScript library which provides a high-level API to control Chrome or Firefox over the DevTools Protocol or WebDriver BiDi. Puppeteer runs in the headless (no visible UI) by default

Get started | API | FAQ | Contributing | Troubleshooting
--------------------------------------------------------

Installation
------------

npm i puppeteer # Downloads compatible Chrome during installation.
npm i puppeteer-core # Alternatively, install as a library, without downloading Chrome.

Example
-------

import puppeteer from 'puppeteer';
// Or import puppeteer from 'puppeteer-core';

// Launch the browser and open a new blank page.
const browser \= await puppeteer.launch();
const page \= await browser.newPage();

// Navigate the page to a URL.
await page.goto('https://developer.chrome.com/');

// Set screen size.
await page.setViewport({width: 1080, height: 1024});

// Open the search menu using the keyboard.
await page.keyboard.press('/');

// Type into search box using accessible input name.
await page.locator('::-p-aria(Search)').fill('automate beyond recorder');

// Wait and click on first result.
await page.locator('.devsite-result-item-link').click();

// Locate the full title with a unique string.
const textSelector \= await page
  .locator('::-p-text(Customize and automate)')
  .waitHandle();
const fullTitle \= await textSelector?.evaluate(el \=> el.textContent);

// Print the full title.
console.log('The title of this blog post is "%s".', fullTitle);

await browser.close();
