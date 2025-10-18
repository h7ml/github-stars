---
project: crawlee
stars: 19961
description: Crawlee—A web scraping and browser automation library for Node.js to build reliable crawlers. In JavaScript and TypeScript. Extract data for AI, LLMs, RAG, or GPTs. Download HTML, PDF, JPG, PNG, and other files from websites. Works with Puppeteer, Playwright, Cheerio, JSDOM, and raw HTTP. Both headful and headless mode. With proxy rotation.
url: https://github.com/apify/crawlee
---

  
A web scraping and browser automation library
================================================

Crawlee covers your crawling and scraping end-to-end and **helps you build reliable scrapers. Fast.**

Your crawlers will appear human-like and fly under the radar of modern bot protections even with the default configuration. Crawlee gives you the tools to crawl the web for links, scrape data, and store it to disk or cloud while staying configurable to suit your project's needs.

Crawlee is available as the `crawlee` NPM package.

> 👉 **View full documentation, guides and examples on the Crawlee project website** 👈

> Do you prefer 🐍 Python instead of JavaScript? 👉 Checkout Crawlee for Python 👈.

Installation
------------

We recommend visiting the Introduction tutorial in Crawlee documentation for more information.

> Crawlee requires **Node.js 16 or higher**.

### With Crawlee CLI

The fastest way to try Crawlee out is to use the **Crawlee CLI** and choose the **Getting started example**. The CLI will install all the necessary dependencies and add boilerplate code for you to play with.

npx crawlee create my-crawler

cd my-crawler
npm start

### Manual installation

If you prefer adding Crawlee **into your own project**, try the example below. Because it uses `PlaywrightCrawler` we also need to install Playwright. It's not bundled with Crawlee to reduce install size.

npm install crawlee playwright

import { PlaywrightCrawler, Dataset } from 'crawlee';

// PlaywrightCrawler crawls the web using a headless
// browser controlled by the Playwright library.
const crawler \= new PlaywrightCrawler({
    // Use the requestHandler to process each of the crawled pages.
    async requestHandler({ request, page, enqueueLinks, log }) {
        const title \= await page.title();
        log.info(\`Title of ${request.loadedUrl} is '${title}'\`);

        // Save results as JSON to ./storage/datasets/default
        await Dataset.pushData({ title, url: request.loadedUrl });

        // Extract links from the current page
        // and add them to the crawling queue.
        await enqueueLinks();
    },
    // Uncomment this option to see the browser window.
    // headless: false,
});

// Add first URL to the queue and start the crawl.
await crawler.run(\['https://crawlee.dev'\]);

By default, Crawlee stores data to `./storage` in the current working directory. You can override this directory via Crawlee configuration. For details, see Configuration guide, Request storage and Result storage.

### Installing pre-release versions

We provide automated beta builds for every merged code change in Crawlee. You can find them in the npm list of releases. If you want to test new features or bug fixes before we release them, feel free to install a beta build like this:

npm install crawlee@3.12.3-beta.13

If you also use the Apify SDK, you need to specify dependency overrides in your `package.json` file so that you don't end up with multiple versions of Crawlee installed:

{
    "overrides": {
       "apify": {
           "@crawlee/core": "3.12.3-beta.13",
           "@crawlee/types": "3.12.3-beta.13",
           "@crawlee/utils": "3.12.3-beta.13"
       }
    }
}

🛠 Features
-----------

-   Single interface for **HTTP and headless browser** crawling
-   Persistent **queue** for URLs to crawl (breadth & depth first)
-   Pluggable **storage** of both tabular data and files
-   Automatic **scaling** with available system resources
-   Integrated **proxy rotation** and session management
-   Lifecycles customizable with **hooks**
-   **CLI** to bootstrap your projects
-   Configurable **routing**, **error handling** and **retries**
-   **Dockerfiles** ready to deploy
-   Written in **TypeScript** with generics

### 👾 HTTP crawling

-   Zero config **HTTP2 support**, even for proxies
-   Automatic generation of **browser-like headers**
-   Replication of browser **TLS fingerprints**
-   Integrated fast **HTML parsers**. Cheerio and JSDOM
-   Yes, you can scrape **JSON APIs** as well

### 💻 Real browser crawling

-   JavaScript **rendering** and **screenshots**
-   **Headless** and **headful** support
-   Zero-config generation of **human-like fingerprints**
-   Automatic **browser management**
-   Use **Playwright** and **Puppeteer** with the same interface
-   **Chrome**, **Firefox**, **Webkit** and many others

Usage on the Apify platform
---------------------------

Crawlee is open-source and runs anywhere, but since it's developed by Apify, it's easy to set up on the Apify platform and run in the cloud. Visit the Apify SDK website to learn more about deploying Crawlee to the Apify platform.

Support
-------

If you find any bug or issue with Crawlee, please submit an issue on GitHub. For questions, you can ask on Stack Overflow, in GitHub Discussions or you can join our Discord server.

Contributing
------------

Your code contributions are welcome, and you'll be praised to eternity! If you have any ideas for improvements, either submit an issue or create a pull request. For contribution guidelines and the code of conduct, see CONTRIBUTING.md.

License
-------

This project is licensed under the Apache License 2.0 - see the LICENSE.md file for details.
