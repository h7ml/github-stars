---
project: masto.js
stars: 762
description: 🐘 Universal Mastodon API client for JavaScript
url: https://github.com/neet/masto.js
---

Universal Mastodon API client for JavaScript

Q&A | Examples | Read the Docs | Releases

Features
--------

-   🌎 **Universal:** Works in Node.js, browsers, and Deno
-   📦 **Lightweight:** Less runtime codes, 6kB+ minified and gzipped
-   📚 **TypeScript:** Written in TypeScript, and provides type definitions
-   🧪 **Tested:** 100% test coverage using a real Mastodon server
-   🤓 **Maintained:** Actively maintained by a Fediverse lover since 2018

Migration Guides
----------------

-   Migrate from v6 to v7
-   Migrate from v5 to v6
-   Migrate from v4 to v5

Who's using Masto.js?
---------------------

-   Elk - A nimble Mastodon web client
-   Phanpy - A minimalistic opinionated Mastodon web client
-   ...and a lot more!

Quick Start
-----------

In this quick start, we'll look at how to create a simple Mastodon bot that publishes a post using _Masto.js_.

First, you must install _Node.js_ and _npm_ in your environment. Follow the npm official guide for the setup, and proceed to the next step. Alternatively, you can use _yarn_, _pnpm_, or other package managers to install Masto.js.

The minimal required version of dependencies is as follows:

-   **Node.js**: `>= 20.x`
-   **npm**: `>= 9.x`
-   **TypeScript** (optional peer dependency): `>= 5.0.0`

If you successfully installed _Node.js_ and _npm_, create your first _Masto.js_ project with the following command. Assume you're using a POSIX-compatible operating system.

Create a directory and initialise your project.

npm init --yes
npm pkg set type=module

Make sure a `package.json` file is created in your project directory. Then install Masto.js using _npm_

```
npm install masto
```

Now you successfully initialised your project for developing a Mastodon bot. Next, you need to create an application to obtain an _access token_ required to access your account.

Go to your settings page, open **Development**, and click the **New Application** button to obtain your personal access token.

You need to fill out _Application name_, but rest of the fields can be left as defaults. What you need to select for _Scopes_ is depending on your bot's ability, but you can access most of the functionality by granting `read` and `write`. See OAuth Scopes documentation for further information.

Once you have created an application, save **Your access token** securely. This string is required to access your account through Masto.js.

Then you're almost there! Create a file named `index.js` inside your project directory and add the following code. This is an example which will post a status from your account.

import { createRestAPIClient } from "masto";

const masto \= createRestAPIClient({
  url: process.env.URL,
  accessToken: process.env.TOKEN,
});

const status \= await masto.v1.statuses.create({
  status: "Hello from #mastojs!",
});

console.log(status.url);

Finally, run the program with the following command. Replace `{URL}` with your instance's URL such as `https://mastodon.social`, and `{TOKEN}` to your access token that you obtained in the previous section.

```
URL={URL} TOKEN={TOKEN} node ./index.js
```

You can learn about other available features in the documentation. You may also want to refer examples to see more examples. Of course, you can ask questions in the Discussions if you have any.

Enjoy your Mastodon development with Masto.js!

Contribution
------------

See CONTRIBUTING.md

License
-------

Masto.js is distributed under the MIT license
