---
project: EdgeGPT
stars: 7997
description: Reverse engineered API of Microsoft's Bing Chat AI
url: https://github.com/acheong08/EdgeGPT
---

> This project has been archived. Due to personal circumstances, I lack the time to maintain this repository.
> ===========================================================================================================

Edge GPT
========

_The reverse engineering the chat feature of the new version of Bing_

English - 简体中文 - 繁體中文 - Español - 日本語

Setup
=====

Install package
---------------

python3 -m pip install EdgeGPT --upgrade

Requirements
------------

-   python 3.8+
-   A Microsoft Account with access to https://bing.com/chat (Optional, depending on your region)
-   Required in a supported country or region with New Bing (Chinese mainland VPN required)
-   Selenium (for automatic cookie setup)

Authentication
--------------

!!! POSSIBLY NOT REQUIRED ANYMORE !!!

**In some regions**, Microsoft has made the chat feature **available** to everyone, so you might be able to **skip this step**. You can check this with a browser (with user-agent set to reflect Edge), by **trying to start a chat without logging in**.

It was also found that it might **depend on your IP address**. For example, if you try to access the chat features from an IP that is known to **belong to a datacenter range** (vServers, root servers, VPN, common proxies, ...), **you might be required to log in** while being able to access the features just fine from your home IP address.

If you receive the following error, you can try **providing a cookie** and see if it works then:

`Exception: Authentication failed. You have not been accepted into the beta.`

### Collect cookies

1.  Get a browser that looks like Microsoft Edge.

-   a) (Easy) Install the latest version of Microsoft Edge
-   b) (Advanced) Alternatively, you can use any browser and set the user-agent to look like you're using Edge (e.g., `Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/111.0.0.0 Safari/537.36 Edg/111.0.1661.51`). You can do this easily with an extension like "User-Agent Switcher and Manager" for Chrome and Firefox.

1.  Open bing.com/chat
2.  If you see a chat feature, you are good to continue...
3.  Install the cookie editor extension for Chrome or Firefox
4.  Go to bing.com
5.  Open the extension
6.  Click "Export" on the bottom right, then "Export as JSON" (This saves your cookies to clipboard)
7.  Paste your cookies into a file `bing_cookies_*.json`.
    -   NOTE: The **cookies file name MUST follow the regex pattern `bing_cookies_*.json`**, so that they could be recognized by internal cookie processing mechanisms

### Use cookies in code:

cookies \= json.loads(open("./path/to/cookies.json", encoding\="utf-8").read())  \# might omit cookies option
bot \= await Chatbot.create(cookies\=cookies)

How to use Chatbot
==================

Run from Command Line
---------------------

```
 $ python3 -m EdgeGPT.EdgeGPT -h

        EdgeGPT - A demo of reverse engineering the Bing GPT chatbot
        Repo: github.com/acheong08/EdgeGPT
        By: Antonio Cheong

        !help for help

        Type !exit to exit

usage: EdgeGPT.py [-h] [--enter-once] [--search-result] [--no-stream] [--rich] [--proxy PROXY] [--wss-link WSS_LINK]
                  [--style {creative,balanced,precise}] [--prompt PROMPT] [--cookie-file COOKIE_FILE]
                  [--history-file HISTORY_FILE] [--locale LOCALE]

options:
  -h, --help            show this help message and exit
  --enter-once
  --search-result
  --no-stream
  --rich
  --proxy PROXY         Proxy URL (e.g. socks5://127.0.0.1:1080)
  --wss-link WSS_LINK   WSS URL(e.g. wss://sydney.bing.com/sydney/ChatHub)
  --style {creative,balanced,precise}
  --prompt PROMPT       prompt to start with
  --cookie-file COOKIE_FILE
                        path to cookie file
  --history-file HISTORY_FILE
                        path to history file
  --locale LOCALE       your locale (e.g. en-US, zh-CN, en-IE, en-GB)
```

(China/US/UK/Norway has enhanced support for locale)

Run in Python
-------------

### 1\. The `Chatbot` class and `asyncio` for more granular control

Use Async for the best experience, for example:

import asyncio, json
from EdgeGPT.EdgeGPT import Chatbot, ConversationStyle

async def main():
    bot \= await Chatbot.create() \# Passing cookies is "optional", as explained above
    response \= await bot.ask(prompt\="Hello world", conversation\_style\=ConversationStyle.creative, simplify\_response\=True)
    print(json.dumps(response, indent\=2)) \# Returns
    """
{
    "text": str,
    "author": str,
    "sources": list\[dict\],
    "sources\_text": str,
    "suggestions": list\[str\],
    "messages\_left": int
}
    """
    await bot.close()

if \_\_name\_\_ \== "\_\_main\_\_":
    asyncio.run(main())

### 2) The `Query` and `Cookie` helper classes

Create a simple Bing Chat AI query (using the 'precise' conversation style by default) and see just the main text output rather than the whole API response:

Remeber to store your cookies in a specific format: `bing_cookies_*.json`.

from EdgeGPT.EdgeUtils import Query, Cookie

q \= Query("What are you? Give your answer as Python code")
print(q)

The default directory for storing Cookie files is `HOME/bing_cookies` but you can change it with:

Cookie.dir\_path \= Path(r"...")

Or change the conversation style or cookie file to be used:

q \= Query(
  "What are you? Give your answer as Python code",
  style\="creative",  \# or: 'balanced', 'precise'
  cookie\_file\="./bing\_cookies\_alternative.json"
)

\#  Use \`help(Query)\` to see other supported parameters.

Quickly extract the text output, code snippets, list of sources/references, or suggested follow-on questions from a response using the following attributes:

q.output  \# Also: print(q)
q.sources
q.sources\_dict
q.suggestions
q.code
q.code\_blocks
q.code\_block\_formatsgiven)

Get the orginal prompt and the conversation style you specified:

q.prompt
q.ignore\_cookies
q.style
q.simplify\_response
q.locale
repr(q)

Access previous Queries made since importing `Query`:

Query.index  \# A list of Query objects; updated dynamically
Query.image\_dir\_path

And finally, the `Cookie` class supports multiple cookie files, so if you create additional cookie files with the naming convention `bing_cookies_*.json`, your queries will automatically try using the next file (alphabetically) if you've exceeded your daily quota of requests (currently set at 200).

Here are the main attributes which you can access:

Cookie.current\_file\_index
Cookie.current\_file\_path
Cookie.current\_data
Cookie.dir\_path
Cookie.search\_pattern
Cookie.files
Cookie.image\_token
Cookie.import\_next
Cookie.rotate\_cookies
Cookie.ignore\_files
Cookie.supplied\_files
Cookie.request\_count

* * *

Run with Docker
---------------

This assumes you have a file cookies.json in your current working directory

docker run --rm -it -v $(pwd)/cookies.json:/cookies.json:ro -e COOKIE\_FILE='/cookies.json' ghcr.io/acheong08/edgegpt

You can add any extra flags as following

docker run --rm -it -v $(pwd)/cookies.json:/cookies.json:ro -e COOKIE\_FILE='/cookies.json' ghcr.io/acheong08/edgegpt --rich --style creative

How to use Image generator
==========================

Run from Command Line
---------------------

$ python3 -m ImageGen.ImageGen -h
usage: ImageGen.py \[-h\] \[-U U\] \[--cookie-file COOKIE\_FILE\] --prompt PROMPT \[--output-dir OUTPUT\_DIR\] \[--quiet\] \[--asyncio\]

optional arguments:
  -h, --help            show this help message and exit
  -U U                  Auth cookie from browser
  --cookie-file COOKIE\_FILE
                        File containing auth cookie
  --prompt PROMPT       Prompt to generate images for
  --output-dir OUTPUT\_DIR
                        Output directory
  --quiet               Disable pipeline messages
  --asyncio             Run ImageGen using asyncio

Run in Python
-------------

### 1) The `ImageQuery` helper class

Generate images based on a simple prompt and download to the current working directory:

from EdgeGPT.EdgeUtils import ImageQuery

q\=ImageQuery("Meerkats at a garden party in Devon")

Change the download directory for all future images in this session:

```
Query.image_dirpath = Path("./to_another_folder")
```

### 2) The `ImageGen` class and `asyncio` for more granular control

from EdgeGPT.ImageGen import ImageGen
import argparse
import json

async def async\_image\_gen(args) \-> None:
    async with ImageGenAsync(args.U, args.quiet) as image\_generator:
        images \= await image\_generator.get\_images(args.prompt)
        await image\_generator.save\_images(images, output\_dir\=args.output\_dir)

if \_\_name\_\_ \== "\_\_main\_\_":
    parser \= argparse.ArgumentParser()
    parser.add\_argument("-U", help\="Auth cookie from browser", type\=str)
    parser.add\_argument("--cookie-file", help\="File containing auth cookie", type\=str)
    parser.add\_argument(
        "--prompt",
        help\="Prompt to generate images for",
        type\=str,
        required\=True,
    )
    parser.add\_argument(
        "--output-dir",
        help\="Output directory",
        type\=str,
        default\="./output",
    )
    parser.add\_argument(
        "--quiet", help\="Disable pipeline messages", action\="store\_true"
    )
    parser.add\_argument(
        "--asyncio", help\="Run ImageGen using asyncio", action\="store\_true"
    )
    args \= parser.parse\_args()
    \# Load auth cookie
    with open(args.cookie\_file, encoding\="utf-8") as file:
        cookie\_json \= json.load(file)
        for cookie in cookie\_json:
            if cookie.get("name") \== "\_U":
                args.U \= cookie.get("value")
                break

    if args.U is None:
        raise Exception("Could not find auth cookie")

    if not args.asyncio:
        \# Create image generator
        image\_generator \= ImageGen(args.U, args.quiet)
        image\_generator.save\_images(
            image\_generator.get\_images(args.prompt),
            output\_dir\=args.output\_dir,
        )
    else:
        asyncio.run(async\_image\_gen(args))

Star History
============

Contributors
============

This project exists thanks to all the people who contribute.
