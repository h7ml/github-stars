---
project: puppeteer-extra-plugin-portal
stars: 53
description: A puppeteer-extra plugin to remotely view and interact with puppeteer sessions. Essentially opening a "portal" to the page.
url: https://github.com/claabs/puppeteer-extra-plugin-portal
---

puppeteer-extra-plugin-portal
=============================

A puppeteer-extra plugin to remotely view and interact with puppeteer sessions. Essentially opening a "portal" to the page.

Demo
----

Here is a demo of the code below:

portal-demo.mp4

Install
-------

yarn add puppeteer-extra-plugin-portal
# - or -
npm install puppeteer-extra-plugin-portal

If this is your first puppeteer-extra plugin here's everything you need:

yarn add puppeteer puppeteer-extra puppeteer-extra-plugin-portal
# - or -
npm install puppeteer puppeteer-extra puppeteer-extra-plugin-portal

Usage your own express server (middleware)
------------------------------------------

// puppeteer-extra is a drop-in replacement for puppeteer,
// it augments the installed puppeteer with plugin functionality
import puppeteer from 'puppeteer-extra';

import express from 'express';

// add portal plugin
import PortalPlugin from 'puppeteer-extra-plugin-portal';
puppeteer.use(
  PortalPlugin({
    webPortalConfig: {
        // When used as middleware, you'll need to provide the baseUrl if it's anything but \`http://localhost:3000\`
        baseUrl: 'http://localhost:3001',
      },
  })
)

const app \= express();
app.use(portalPlugin.createExpressMiddleware());
const server \= app.listen(3001);
server.headersTimeout \= 0; // Required for Node 18+ due to slow loris attack change
server.requestTimeout \= 0;

// puppeteer usage as normal
puppeteer.launch({ headless: true }).then(async browser \=> {
  const page \= await browser.newPage();
  await page.goto('https://www.google.com/recaptcha/api2/demo');

  // Open a portal to get a link to it. 
  const portalUrl \= await page.openPortal();
  console.log('Portal URL:', portalUrl);

  // Wait a long time for the success condition to be met
  const successDiv \= await page.waitForSelector('.recaptcha-success', {
      timeout: 86400 \* 1000, // 24 hours
    });
  
  await page.closePortal(); // You can manually close a portal with
  // OR
  await page.close(); // Closing the page will automatically close its portal.
  // OR
  await browser.close(); // Closing the browser will automatically close the portals opened on it.
})

// You'll need to close the server on your own
app.close()

Usage with plugin-managed server
--------------------------------

// puppeteer-extra is a drop-in replacement for puppeteer,
// it augments the installed puppeteer with plugin functionality
import puppeteer from 'puppeteer-extra';

// add portal plugin
import PortalPlugin from 'puppeteer-extra-plugin-portal';
puppeteer.use(
  PortalPlugin({
    // This is a typical configuration when hosting behind a secured reverse proxy
    webPortalConfig: {
        listenOpts: {
          port: 3000,
        },
        baseUrl: 'https://portal.example.com',
      },
  })
)

// puppeteer usage as normal
puppeteer.launch({ headless: true }).then(async browser \=> {
  const page \= await browser.newPage();
  await page.goto('https://www.google.com/recaptcha/api2/demo');

  // Open a portal to get a link to it. 
  const portalUrl \= await page.openPortal();
  console.log('Portal URL:', portalUrl);

  // Wait a long time for the success condition to be met
  const successDiv \= await page.waitForSelector('.recaptcha-success', {
      timeout: 86400 \* 1000, // 24 hours
    });
  
  await page.closePortal(); // You can manually close a portal with
  // OR
  await page.close(); // Closing the page will automatically close its portal.
  // OR
  await browser.close(); // Closing the browser will automatically close the portals opened on it.
  // When all portals are closed, the web server will automatically shut down
})
