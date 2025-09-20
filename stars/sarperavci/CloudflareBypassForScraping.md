---
project: CloudflareBypassForScraping
stars: 1628
description: A cloudflare verification bypass script for webscraping
url: https://github.com/sarperavci/CloudflareBypassForScraping
---

Cloudflare Turnstile Page & Captcha Bypass for Scraping
=======================================================

**We love scraping, don't we?** But sometimes, we face Cloudflare protection. This script is designed to bypass the Cloudflare protection on websites, allowing you to interact with them programmatically.

Sponsors
--------

### Scrapeless

If you're looking for a long-term and stable solution to bypass Cloudflare, CAPTCHA challenges, and sophisticated bot detection systems, we highly recommend Scrapeless Scraping Browser.

**Scrapeless Scraping Browser** offers low-level dynamic browser environment spoofing and automated CAPTCHA bypassing, significantly improving the stability, success rate, and anti-blocking capability of your project. It is especially well-suited for mid-to-large-scale scraping systems or commercial automation applications.

**Key Advantages of Scrapeless Scraping Browser:**

-   Built-in CAPTCHA solving: Automatically bypasses Cloudflare Turnstile, reCAPTCHA, AWS WAF, DataDome, and other challenge systems.
-   Undetectable browser environment: Not based on the traditional WebDriver — avoids automation detection.
-   Massive concurrency support: Run 50–10,000+ browser instances simultaneously with no server constraints.
-   Real-time debugging: Live View and session recording for efficient troubleshooting.
-   Native integration: Compatible with Puppeteer, Playwright, Python, and Node.js — easy to integrate into your current workflows.
-   70M+ residential IPs: Global proxy network with automatic rotation and smart geolocation routing.

Scrapeless is an all-in-one, highly scalable data scraping platform built for enterprises and developers. In addition to the Scraping Browser, Scrapeless also offers a Scraping API, Deep Serp API, and Proxy services. 👉 Learn more: Scrapeless Scraping Browser | Documentation

How does this script work?
==========================

If you use Selenium, you may have noticed that it is not possible to bypass Cloudflare protection with it. Even you click the "I'm not a robot" button, you will still be stuck in the "Checking your browser before accessing" page. This is because Cloudflare protection is able to detect the automation tools and block them, which puts the webdriver infinitely in the "Checking your browser before accessing" page.

As you realize, the script uses the DrissionPage, which is a controller for the browser itself. This way, the browser is not detected as a webdriver and the Cloudflare protection is bypassed.

Installation
------------

You can install the required packages by running the following command:

pip install -r requirements.txt

Demo
----

Usage
-----

Create a new instance of the `CloudflareBypass` class and call the `bypass` method when you need to bypass the Cloudflare protection.

from CloudflareBypasser import CloudflareBypasser
from DrissionPage import ChromiumPage

driver \= ChromiumPage()
driver.get('https://nopecha.com/demo/cloudflare')

cf\_bypasser \= CloudflareBypasser(driver)
cf\_bypasser.bypass()

You can run the test script to see how it works:

python test.py

Introducing Server Mode
=======================

Recently, @frederik-uni has introduced a new feature called "Server Mode". This feature allows you to bypass the Cloudflare protection remotely, either you can get the cookies or the HTML content of the website.

Installation
------------

You can install the required packages by running the following command:

pip install -r server\_requirements.txt

Usage
-----

Start the server by running the following command:

python server.py

Two endpoints are available:

-   `/cookies?url=<URL>&retries=<>&proxy=<>`: This endpoint returns the cookies of the website (including the Cloudflare cookies).
-   `/html?url=<URL>&retries=<>&proxy=<>`: This endpoint returns the HTML content of the website.

Send a GET request to the desired endpoint with the URL of the website you want to bypass the Cloudflare protection.

sarp@IdeaPad:~/$ curl http://localhost:8000/cookies?url=https://nopecha.com/demo/cloudflare
{"cookies":{"cf\_clearance":"SJHuYhHrTZpXDUe8iMuzEUpJxocmOW8ougQVS0.aK5g-1723665177-1.0.1.1-5\_NOoP19LQZw4TQ4BLwJmtrXBoX8JbKF5ZqsAOxRNOnW2rmDUwv4hQ7BztnsOfB9DQ06xR5hR\_hsg3n8xteUCw"},"user\_agent":"Mozilla/5.0 (X11; Linux x86\_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/125.0.0.0 Safari/537.36"}

Docker
------

You can also run the server in a Docker container. Thanks to @gandrunx for Dockerizing the server.

First, build the Docker image:

docker build -t cloudflare-bypass .

Then, run the Docker container:

docker run -p 8000:8000 cloudflare-bypass

Alternatively, you can skip `docker build` step, and run the container using pre-build image:

docker run -p 8000:8000 ghcr.io/sarperavci/cloudflarebypassforscraping:latest

Example Projects
----------------

Here are some example projects that utilize the CloudflareBypasser Server:

-   Calibre Web Automated Book Downloader - A tool to download books from calibre web.
-   Kick Unofficial API - A tool to interact with the Kick.com, download videos, send messages, etc.

Star History
------------
