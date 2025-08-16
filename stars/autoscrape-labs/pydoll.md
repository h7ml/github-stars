---
project: pydoll
stars: 5075
description: Pydoll is a library for automating chromium-based browsers without a WebDriver, offering realistic interactions. 
url: https://github.com/autoscrape-labs/pydoll
---

  

Pydoll: Automate the Web, Naturally
===================================

📖 Documentation • 🚀 Getting Started • ⚡ Advanced Features • 🤝 Contributing • 💖 Support My Work

Imagine the following scenario: you need to automate tasks in your browser. Maybe it's testing a web application, collecting data from a site, or even automating repetitive processes. Normally this involves using external drivers, complex configurations, and many compatibility issues.

**Pydoll was born to solve these problems.**

Built from scratch with a different philosophy, Pydoll connects directly to the Chrome DevTools Protocol (CDP), eliminating the need for external drivers. This clean implementation along with realistic ways of clicking, navigating and interacting with elements makes it practically indistinguishable from a real user.

We believe that powerful automation shouldn't require you to become an expert in configuration or constantly fight with bot protection systems. With Pydoll, you can focus on what really matters: your automation logic, not the underlying complexity or protection systems.

#### Be a good human. Give it a star ⭐

No stars, no bugs fixed. Just kidding (maybe)

🌟 What makes Pydoll special?
-----------------------------

-   **Zero Webdrivers**: Say goodbye to webdriver compatibility issues
-   **Human-like Interaction Engine**: Capable of passing behavioral CAPTCHAs like reCAPTCHA v3 or Turnstile, depending on IP reputation and interaction patterns
-   **Asynchronous Performance**: For high-speed automation and multiple simultaneous tasks
-   **Humanized Interactions**: Mimic real user behavior
-   **Simplicity**: With Pydoll, you install and you're ready to automate.

What's New
----------

### Browser-context HTTP requests - game changer for hybrid automation!

Ever wished you could make HTTP requests that automatically inherit all your browser's session state? **Now you can!**  
The `tab.request` property gives you a beautiful `requests`\-like interface that executes HTTP calls directly in the browser's JavaScript context. This means every request automatically gets cookies, authentication headers, CORS policies, and session state, just as if the browser made the request itself.

**Perfect for Hybrid Automation:**

\# Navigate to a site and login normally with PyDoll
await tab.go\_to('https://example.com/login')
await (await tab.find(id\='username')).type\_text('user@example.com')
await (await tab.find(id\='password')).type\_text('password')
await (await tab.find(id\='login-btn')).click()

\# Now make API calls that inherit the logged-in session!
response \= await tab.request.get('https://example.com/api/user/profile')
user\_data \= response.json()

\# POST data while staying authenticated
response \= await tab.request.post(
    'https://example.com/api/settings', 
    json\={'theme': 'dark', 'notifications': True}
)

\# Access response content in different formats
raw\_data \= response.content
text\_data \= response.text
json\_data \= response.json()

\# Check cookies that were set
for cookie in response.cookies:
    print(f"Cookie: {cookie\['name'\]} = {cookie\['value'\]}")

\# Add custom headers to your requests
headers \= \[
    {'name': 'X-Custom-Header', 'value': 'my-value'},
    {'name': 'X-API-Version', 'value': '2.0'}
\]

await tab.request.get('https://api.example.com/data', headers\=headers)

**Why this is great:**

-   **No more session juggling** - Requests inherit browser cookies automatically
-   **CORS just works** - Requests respect browser security policies
-   **Perfect for modern SPAs** - Seamlessly mix UI automation with API calls
-   **Authentication made easy** - Login once via UI, then hammer APIs
-   **Hybrid workflows** - Use the best tool for each step (UI or API)

This opens up incredible possibilities for automation scenarios where you need both browser interaction AND API efficiency!

### New expect\_download() context manager — robust file downloads made easy!

Tired of fighting with flaky download flows, missing files, or racy event listeners? Meet `tab.expect_download()`, a delightful, reliable way to handle file downloads.

-   Automatically sets the browser’s download behavior
-   Works with your own directory or a temporary folder (auto-cleaned!)
-   Waits for completion with a timeout (so your tests don’t hang)
-   Gives you a handy handle to read bytes/base64 or check `file_path`

Tiny example that just works:

import asyncio
from pathlib import Path
from pydoll.browser import Chrome

async def download\_report():
    async with Chrome() as browser:
        tab \= await browser.start()
        await tab.go\_to('https://example.com/reports')

        target\_dir \= Path('/tmp/my-downloads')
        async with tab.expect\_download(keep\_file\_at\=target\_dir, timeout\=10) as download:
            \# Trigger the download in the page (button/link/etc.)
            await (await tab.find(text\='Download latest report')).click()
            \# Wait until finished and read the content
            data \= await download.read\_bytes()
            print(f"Downloaded {len(data)} bytes to: {download.file\_path}")

asyncio.run(download\_report())

Want zero-hassle cleanup? Omit `keep_file_at` and we’ll create a temp folder and remove it automatically after the context exits. Perfect for tests.

### Total browser control with custom preferences! (thanks to @LucasAlvws)

Want to completely customize how Chrome behaves? **Now you can control EVERYTHING!**  
The new `browser_preferences` system gives you access to hundreds of internal Chrome settings that were previously impossible to change programmatically. We're talking about deep browser customization that goes way beyond command-line flags!

**The possibilities are endless:**

options \= ChromiumOptions()

\# Create the perfect automation environment
options.browser\_preferences \= {
    'download': {
        'default\_directory': '/tmp/downloads',
        'prompt\_for\_download': False,
        'directory\_upgrade': True,
        'extensions\_to\_open': ''  \# Don't auto-open any downloads
    },
    'profile': {
        'default\_content\_setting\_values': {
            'notifications': 2,        \# Block all notifications
            'geolocation': 2,         \# Block location requests
            'media\_stream\_camera': 2, \# Block camera access
            'media\_stream\_mic': 2,    \# Block microphone access
            'popups': 1               \# Allow popups (useful for automation)
        },
        'password\_manager\_enabled': False,  \# Disable password prompts
        'exit\_type': 'Normal'              \# Always exit cleanly
    },
    'intl': {
        'accept\_languages': 'en-US,en',
        'charset\_default': 'UTF-8'
    },
    'browser': {
        'check\_default\_browser': False,    \# Don't ask about default browser
        'show\_update\_promotion\_infobar': False
    }
}

\# Or use the convenient helper methods
options.set\_default\_download\_directory('/tmp/downloads')
options.set\_accept\_languages('en-US,en,pt-BR')  
options.prompt\_for\_download \= False

**Real-world power examples:**

-   **Silent downloads** - No prompts, no dialogs, just automated downloads
-   **Block ALL distractions** - Notifications, popups, camera requests, you name it
-   **Perfect for CI/CD** - Disable update checks, default browser prompts, crash reporting
-   **Multi-region testing** - Change languages, timezones, and locale settings instantly
-   **Security hardening** - Lock down permissions and disable unnecessary features
-   **Advanced fingerprinting control** - Modify browser install dates, engagement history, and behavioral patterns

**Fingerprint customization for stealth automation:**

import time

\# Simulate a browser that's been around for months
fake\_engagement\_time \= int(time.time()) \- (7 \* 24 \* 60 \* 60)  \# 7 days ago

options.browser\_preferences \= {
    'settings': {
        'touchpad': {
            'natural\_scroll': True,
        }
    },
    'profile': {
        'last\_engagement\_time': fake\_engagement\_time,
        'exit\_type': 'Normal',
        'exited\_cleanly': True
    },
    'newtab\_page\_location\_override': 'https://www.google.com',
    'session': {
        'restore\_on\_startup': 1,  \# Restore last session
        'startup\_urls': \['https://www.google.com'\]
    }
}

This level of control was previously only available to Chrome extension developers - now it's in your automation toolkit!

Check the documentation for more details.

### New `get_parent_element()` method

Retrieve the parent of any WebElement, making it easier to navigate the DOM structure:

element \= await tab.find(id\='button')
parent \= await element.get\_parent\_element()

### New start\_timeout option (thanks to @j0j1j2)

Added to ChromiumOptions to control how long the browser can take to start. Useful on slower machines or CI environments.

options \= ChromiumOptions()
options.start\_timeout \= 20  \# wait 20 seconds

📦 Installation
---------------

pip install pydoll-python

And that's it! Just install and start automating.

🚀 Getting Started
------------------

### Your first automation

Let's start with a real example: an automation that performs a Google search and clicks on the first result. With this example, we can see how the library works and how you can start automating your tasks.

import asyncio

from pydoll.browser import Chrome
from pydoll.constants import Key

async def google\_search(query: str):
    async with Chrome() as browser:
        tab \= await browser.start()
        await tab.go\_to('https://www.google.com')
        search\_box \= await tab.find(tag\_name\='textarea', name\='q')
        await search\_box.insert\_text(query)
        await search\_box.press\_keyboard\_key(Key.ENTER)
        await (await tab.find(
            tag\_name\='h3',
            text\='autoscrape-labs/pydoll',
            timeout\=10,
        )).click()
        await tab.find(id\='repository-container-header', timeout\=10)

asyncio.run(google\_search('pydoll python'))

Without configurations, just a simple script, we can do a complete Google search! Okay, now let's see how we can extract data from a page, using the same previous example. Let's consider in the code below that we're already on the Pydoll page. We want to extract the following information:

-   Project description
-   Number of stars
-   Number of forks
-   Number of issues
-   Number of pull requests

Let's get started! To get the project description, we'll use xpath queries. You can check the documentation on how to build your own queries.

description \= await (await tab.query(
    '//h2\[contains(text(), "About")\]/following-sibling::p',
    timeout\=10,
)).text

And that's it! Let's understand what this query does:

1.  `//h2[contains(text(), "About")]` - Selects the first `<h2>` that contains "About"
2.  `/following-sibling::p` - Selects the first `<p>` that comes after the `<h2>`

Now let's get the rest of the data:

number\_of\_stars \= await (await tab.find(
    id\='repo-stars-counter-star'
)).text

number\_of\_forks \= await (await tab.find(
    id\='repo-network-counter'
)).text
number\_of\_issues \= await (await tab.find(
    id\='issues-repo-tab-count',
)).text
number\_of\_pull\_requests \= await (await tab.find(
    id\='pull-requests-repo-tab-count',
)).text

data \= {
    'description': description,
    'number\_of\_stars': number\_of\_stars,
    'number\_of\_forks': number\_of\_forks,
    'number\_of\_issues': number\_of\_issues,
    'number\_of\_pull\_requests': number\_of\_pull\_requests,
}
print(data)

In the image below we can see the execution speed and the result of the automation. For demonstration purposes, the browser is not displayed.

In just 5 seconds, we managed to extract all the necessary data! This is the speed you can expect from automation with Pydoll.

### A more complex example

Let's now move to a case that you've probably encountered many times: a captcha like Cloudflare's. Pydoll has a method to try to handle this, although, as mentioned earlier, effectiveness depends on various factors. In the code below, we have a complete example of how to handle a Cloudflare captcha.

import asyncio

from pydoll.browser import Chrome
from pydoll.constants import By

async def cloudflare\_example():
    async with Chrome() as browser:
        tab \= await browser.start()
        async with tab.expect\_and\_bypass\_cloudflare\_captcha():
            await tab.go\_to('https://2captcha.com/demo/cloudflare-turnstile')
        print('Captcha handled, continuing...')
        await asyncio.sleep(5)  \# just to see the result :)

asyncio.run(cloudflare\_example())

Below we have the result of the execution:

With just a few lines of code, we managed to handle one of the most difficult captchas to deal with. This is just one of the many functionalities that Pydoll offers. But it doesn't stop there!

### Custom Configurations

Sometimes we need more control over the browser. Pydoll offers a flexible way to do this. Let's see the example below:

from pydoll.browser import Chrome
from pydoll.browser.options import ChromiumOptions as Options

async def custom\_automation():
    \# Configure browser options
    options \= Options()
    options.add\_argument('--proxy-server=username:password@ip:port')
    options.add\_argument('--window-size=1920,1080')
    options.binary\_location \= '/path/to/your/browser'
    options.start\_timeout \= 20

    async with Chrome(options\=options) as browser:
        tab \= await browser.start()
        \# Your automation code here
        await tab.go\_to('https://example.com')
        \# The browser is now using your custom settings

asyncio.run(custom\_automation())

In this example, we're configuring the browser to use a proxy and a 1920x1080 window, in addition to a custom path for the Chrome binary, in case your installation location is different from the common defaults.

⚡ Advanced Features
-------------------

Pydoll offers a series of advanced features to please even the most demanding users.

### Advanced Element Search

We have several ways to find elements on the page. No matter how you prefer, we have a way that makes sense for you:

import asyncio
from pydoll.browser import Chrome

async def element\_finding\_examples():
    async with Chrome() as browser:
        tab \= await browser.start()
        await tab.go\_to('https://example.com')

        \# Find by attributes (most intuitive)
        submit\_btn \= await tab.find(
            tag\_name\='button',
            class\_name\='btn-primary',
            text\='Submit'
        )
        \# Find by ID
        username\_field \= await tab.find(id\='username')
        \# Find multiple elements
        all\_links \= await tab.find(tag\_name\='a', find\_all\=True)
        \# CSS selectors and XPath
        nav\_menu \= await tab.query('nav.main-menu')
        specific\_item \= await tab.query('//div\[@data-testid="item-123"\]')
        \# With timeout and error handling
        delayed\_element \= await tab.find(
            class\_name\='dynamic-content',
            timeout\=10,
            raise\_exc\=False  \# Returns None if not found
        )
        \# Advanced: Custom attributes
        custom\_element \= await tab.find(
            data\_testid\='submit-button',
            aria\_label\='Submit form'
        )

asyncio.run(element\_finding\_examples())

The `find` method is more user-friendly. We can search by common attributes like id, tag\_name, class\_name, etc., up to custom attributes (e.g. `data-testid`).

If that's not enough, we can use the `query` method to search for elements using CSS selectors, XPath queries, etc. Pydoll automatically takes care of identifying what type of query we're using.

### Concurrent Automation

One of the great advantages of Pydoll is the ability to process multiple tasks simultaneously thanks to its asynchronous implementation. We can automate multiple tabs at the same time! Let's see an example:

import asyncio
from pydoll.browser import Chrome

async def scrape\_page(url, tab):
    await tab.go\_to(url)
    title \= await tab.execute\_script('return document.title')
    links \= await tab.find(tag\_name\='a', find\_all\=True)
    return {
        'url': url,
        'title': title,
        'link\_count': len(links)
    }

async def concurrent\_scraping():
    browser \= Chrome()
    tab\_google \= await browser.start()
    tab\_duckduckgo \= await browser.new\_tab()
    tasks \= \[
        scrape\_page('https://google.com/', tab\_google),
        scrape\_page('https://duckduckgo.com/', tab\_duckduckgo)
    \]
    results \= await asyncio.gather(\*tasks)
    print(results)
    await browser.stop()

asyncio.run(concurrent\_scraping())

Below we see the incredible execution speed:

We managed to extract data from two pages at the same time! Tell me if that's not incredible?

And there's much, much more! Event system for reactive automations, request interception and modification, and so on. Take a look at the documentation, you won't regret it!

🔧 Quick Troubleshooting
------------------------

**Browser not found?**

from pydoll.browser import Chrome
from pydoll.browser.options import ChromiumOptions

options \= ChromiumOptions()
options.binary\_location \= '/path/to/your/chrome'
browser \= Chrome(options\=options)

**Browser starts after a FailedToStartBrowser error?**

from pydoll.browser import Chrome
from pydoll.browser.options import ChromiumOptions

options \= ChromiumOptions()
options.start\_timeout \= 20  \# default is 10 seconds

browser \= Chrome(options\=options)

**Need a proxy?**

options.add\_argument('--proxy-server=your-proxy:port')

**Running in Docker?**

options.add\_argument('--no-sandbox')
options.add\_argument('--disable-dev-shm-usage')

📚 Documentation
----------------

For complete documentation, detailed examples and deep dives into all Pydoll functionalities, visit our official documentation.

The documentation includes:

-   **Getting Started Guide** - Step-by-step tutorials
-   **API Reference** - Complete method documentation
-   **Advanced Techniques** - Network interception, event handling, performance optimization

> The chinese version of this README is here.

🤝 Contributing
---------------

We would love your help to make Pydoll even better! Check out our contribution guidelines to get started. Whether it's fixing bugs, adding features or improving documentation - all contributions are welcome!

Please make sure to:

-   Write tests for new features or bug fixes
-   Follow code style and conventions
-   Use conventional commits for pull requests
-   Run lint checks and tests before submitting

💖 Support My Work
------------------

If you find Pydoll useful, consider supporting me on GitHub.  
You'll get access to exclusive benefits like priority support, custom features and much more!

Can't sponsor right now? No problem, you can still help a lot by:

-   Starring the repository
-   Sharing on social media
-   Writing posts or tutorials
-   Giving feedback or reporting issues

Every bit of support makes a difference/

💬 Spread the word
------------------

If Pydoll saved you time, mental health, or a keyboard from being smashed, give it a ⭐, share it, or tell your weird dev friends.

📄 License
----------

Pydoll is licensed under the MIT License.

**Pydoll** — Making browser automation magical!
