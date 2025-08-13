---
project: console-importer
stars: 919
description: Easily import JS and CSS resources from Chrome console.
url: https://github.com/pd4d10/console-importer
---

Console Importer
================

Installation
------------

Install it from Chrome Web Store:

https://chrome.google.com/webstore/detail/console-importer/hgajpakhafplebkdljleajgbpdmplhie

Usage
-----

Open Chrome devtools console, a function named `$i` could be used to import JavaScript and CSS resources.

$i('jquery')

Import specific version:

$i('jquery@2')

Also, you can import a valid script URL:

$i('https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js')

CSS is supported, too:

$i('https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css')

### Import ES Module

ES module has been widely supported in modern browsers. `$i.esm` method can be useful in this case:

d3 \= await $i.esm('d3')

or specify a version:

d3 \= await $i.esm('d3@7')

The advantage of this approach is that no global variables are added to the window, which allows better control over the scope of side effects. For more details, see https://esm.run.

Trouble shooting
----------------

### Q: `$i` doesn't work as expected

Some websites like Google Inbox already have `$i` used as a global variable. This extension doesn't overwrite it.

You can use `console.$i` on these websites.

### Q: `$i` fail to import resources

On some websites like GitHub, `$i` will fail to import resources. Console errors may be like follows:

# js errors example
Refused to connect to 'https://api.cdnjs.com/libraries?search=jquery' because it violates the following Content Security Policy directive:

# css errors example
Refused to load the stylesheet 'https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css' because it violates the following Content Security Policy directive:

It is because of strict Content Security Policy of these websites. For more information, see Content Security Policy (CSP) wiki

How does it work?
-----------------

-   If it is like a JavaScript lib name, like `jquery`, try to load it from cdnjs
-   If it has version number, like `jquery@2`, try to load it from unpkg
-   If it is a valid URL(CSS or JS), load it directly

For advanced use, there are also two functions `$i.unpkg` and `$i.cdnjs` which could be used to import resources from specific CDN.

License
-------

MIT
