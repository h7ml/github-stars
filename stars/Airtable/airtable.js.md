---
project: airtable.js
stars: 2126
description: Airtable javascript client
url: https://github.com/Airtable/airtable.js
---

The official Airtable JavaScript library.

Airtable.js
===========

The Airtable API provides a simple way of accessing your data. Whether it's contacts, sales leads, inventory, applicant information or todo items, the vocabulary of the interactions closely matches your data structure. You will use your table names to address tables, column names to access data stored in those columns. In other words, the Airtable API is your own RESTful API for your base.

Installation
============

Node.js
-------

To install Airtable.js in a node project:

npm install airtable

Airtable.js is compatible with Node 10 and above.

Browser
-------

To use Airtable.js in the browser, use build/airtable.browser.js.

For a demo, run:

cd test/test\_files
python -m http.server

Edit `test/test_files/index.html` - put your `BASE_ID` and `API_KEY` (Be careful! You are putting your API key on a web page! Create a separate account and share only one base with it.)

Then open http://localhost:8000/ in your browser.

Airtable.js is compatible with browsers supported by the Airtable web app with the exception of Safari 10.0. Airtable.js supports Safari 10.1 and higher. See the technical requirements for more details.

Configuration
=============

There are three configurable options available:

-   `apiKey` - your secret API token. Visit /create/tokens to create a personal access token. OAuth access tokens can also be used.
-   `endpointUrl` - the API endpoint to hit. You might want to override it if you are using an API proxy (e.g. runscope.net) to debug your API calls. (`AIRTABLE_ENDPOINT_URL`).
-   `requestTimeout` - the timeout in milliseconds for requests. The default is 5 minutes (`300000`).

You can set the options globally via `Airtable.configure`:

Airtable.configure({ apiKey: 'YOUR\_SECRET\_API\_TOKEN' })

Globally via process env (e.g. in 12factor setup):

export AIRTABLE\_API\_KEY=YOUR\_SECRET\_API\_TOKEN

You can also override the settings per connection:

const airtable \= new Airtable({endpointUrl: 'https://api-airtable-com-8hw7i1oz63iz.runscope.net/'})

Interactive documentation
=========================

Go to https://airtable.com/api to see the interactive API documentation for your Airtable bases. Once you select a base, click the "JavaScript" tab to see code snippets using Airtable.js. It'll have examples for all operations you can perform against your base using this library.

You can also view non-interactive API documentation at https://airtable.com/developers/web/api.

Promises
========

As of v0.5.0 all of the methods that take a `done` callback will return a Promise if you don't pass in a `done` callback.

For example:

table.select().firstPage(result \=> { ... })

is equivalent to

table.select().firstPage().then(result \=> { ... })

Tests
=====

Tests are run via `npm run test`.

We strive for 100% test coverage. Some aspects may not be testable or suitable for test coverage. The tooling supports ignoring specific parts of a file documented here; use that as appropriate.

When you run the tests a coverage report will be generated at `./coverage/lcov-report/index.html` which you can access in the browser for line by line reporting.
