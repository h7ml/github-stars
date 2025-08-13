---
project: ajax-proxy
stars: 105
description: :bulb: Browser extension for Chromium kernel. For modifying your Ajax responses
url: https://github.com/g0ngjie/ajax-proxy
---

  

Ajax Proxy
==========

  

#### A browser plugin based on Chromium kernel · Tools for Developers · For the modification of web-side response

**

English | 中文

**

When to use
-----------

-   When actual data fails to meet expected results, mocking data is needed.
-   In development or production stages, verification of exceptional scenarios or edge cases is necessary.
-   The frequent changes in interface data hinder the development process.
-   When a certain interface returns a 404 error.

Installation
------------

Microsoft Edge

Google Chrome

Examples
--------

Video: https://www.youtube.com/watch?v=F\_\_7LXBqnvQ&list=PLniy0-3-8-V1ZhsmG6\_\_HdOJBAschGWSt

FAQ
---

1.  Data interception does not work
    -   You can switch between `interceptor` and `redirector` to solve the Ajax referencing problem
    -   You can select the `Network` section in Developer Tools and disable caching by checking ☑️
2.  Function-based response explanation

Monorepo
--------

Package

Description

@proxy/compatibility

Old Data Compatibility Library

@proxy/lib

Manipulating the Ajax Core Logic Library

@proxy/shared-utils

Public Class Libraries

@proxy/shell-chrome

Browser Extension Library

@proxy/vue-panels

Application Operator Panel

Use of source code
------------------

1.  Download the corresponding version of Source code and unzip it
2.  Open `Developer mode` in your browser
3.  Then just load the unpacked folder

Testing
-------

You can test it directly in Swagger

⭐ Stargazers
------------

Thanks for your support!

License
-------

Ajax Proxy is MIT licensed.
