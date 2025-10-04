---
project: random-useragent
stars: 259
description: Get a random user agent (with an optional filter to select from a specific set of user agents).
url: https://github.com/skratchdot/random-useragent
---

random-useragent
================

Description
-----------

Get a random user agent (with an optional filter to select from a specific set of user agents).

Getting Started
---------------

Install the module with: `npm install random-useragent`

const randomUseragent \= require('random-useragent');
randomUseragent.getRandom(); // gets a random user agent string

-   Live example on NPM Runkit

Documentation
-------------

#### .getRandom(filter)

Get a random user agent string (optionally using a filter).

Example Result:

'Mozilla/5.0 (Windows NT 6.2; rv:20.0) Gecko/20121202 Firefox/20.0';

#### .getRandomData(filter)

Get a random user agent's parsed data (optionally using a filter).

Example Result:

{
	"folder": "/Browsers - Windows/Legacy Browsers",
	"description": "Firefox 20.0 (Win 8 32)",
	"userAgent": "Mozilla/5.0 (Windows NT 6.2; rv:20.0) Gecko/20121202 Firefox/20.0",
	"appCodename": "",
	"appName": "",
	"appVersion": "",
	"platform": "",
	"vendor": "",
	"vendorSub": "",
	"browserName": "Firefox",
	"browserMajor": "20",
	"browserVersion": "20.0",
	"deviceModel": "",
	"deviceType": "",
	"deviceVendor": "",
	"engineName": "Gecko",
	"engineVersion": "20.0",
	"osName": "Windows",
	"osVersion": "8",
	"cpuArchitecture": ""
}

#### .getAll(filter)

Get an array of all the user agent strings (optionally using a filter).

#### .getAllData(filter)

Get an array of all the parsed user agent data (optionally using a filter).

Examples
--------

Get a random user agent string:

randomUseragent.getRandom();

Get a random Firefox user agent string:

randomUseragent.getRandom(function (ua) {
  return ua.browserName \=== 'Firefox';
});

Get a random user agent with a version >= 20:

randomUseragent.getRandom(function (ua) {
  return parseFloat(ua.browserVersion) \>= 20;
});

Source Of User Agents
---------------------

The collection of user agents is pulled from the large, regularly updated xml file provided by the author of User Agent Switcher, which is located here:

-   Forum Post
-   Direct Link

Links
-----

-   Source Code
-   Changelog
-   Live example on Tonic

License
-------

Copyright (c) 2014 skratchdot  
Licensed under the MIT license.
