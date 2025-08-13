---
project: rest.js
stars: 623
description: GitHub REST API client for JavaScript
url: https://github.com/octokit/rest.js
---

rest.js
=======

> GitHub REST API client for JavaScript

Usage
-----

Browsers

Load `@octokit/rest` directly from esm.sh

<script type\="module"\>
  import { Octokit } from "https://esm.sh/@octokit/rest";
</script\>

Node

Install with `npm install @octokit/rest`

import { Octokit } from "@octokit/rest";

Important

As we use conditional exports, you will need to adapt your `tsconfig.json` by setting `"moduleResolution": "node16", "module": "node16"`.

See the TypeScript docs on package.json "exports".  
See this helpful guide on transitioning to ESM from @sindresorhus

const octokit \= new Octokit();

// Compare: https://docs.github.com/en/rest/reference/repos/#list-organization-repositories
octokit.rest.repos
  .listForOrg({
    org: "octokit",
    type: "public",
  })
  .then(({ data }) \=> {
    // handle data
  });

See https://octokit.github.io/rest.js for full documentation.

Important

As we use conditional exports, you will need to adapt your `tsconfig.json` by setting `"moduleResolution": "node16", "module": "node16"`.

See the TypeScript docs on package.json "exports".  
See this helpful guide on transitioning to ESM from @sindresorhus

Contributing
------------

We would love you to contribute to `@octokit/rest`, pull requests are very welcome! Please see CONTRIBUTING.md for more information.

Credits
-------

`@octokit/rest` was originally created as `node-github` in 2012 by Mike de Boer from Cloud9 IDE, Inc. The original commit is from 2010 which predates the npm registry.

It was adopted and renamed by GitHub in 2017. Learn more about its origin on GitHub's blog: From 48k lines of code to 10—the story of GitHub’s JavaScript SDK

LICENSE
-------

MIT
