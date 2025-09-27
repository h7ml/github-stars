---
project: clientjs
stars: 2201
description: Device information and digital fingerprinting written in pure JavaScript.
url: https://github.com/jackspirou/clientjs
---

**Device information and digital fingerprinting written in _pure_ JavaScript.**

ClientJS is a JavaScript library that makes digital fingerprinting easy, while also exposing all the browser data-points used in generating fingerprints.

If you want to fingerprint browsers, you are **_probably_** also interested in other client-based information, such as screen resolution, operating system, browser type, device type, and much more.

Below are some features that make ClientJS different from other fingerprinting libraries:

-   It's pure native JavaScript
-   It's decently lightweight at ~55 KB (full bundle) or ~28 KB (minimal bundle)
-   All user data points are available by design, not just the 32bit integer fingerprint

Installation
------------

To use ClientJS, simply include `dist/client.base.min.js` or one of the other bundles (see bundles section for more details)

### npm

npm install clientjs

Fingerprinting
--------------

Digital fingerprints are based on device/browser settings. They allow you to make an "educated guess" about the identify of a new or returning visitor. By taking multiple data points, combining them, and representing them as a number, you can be surprisingly accurate at recognizing not only browsers and devices, but also individual users.

This is useful for identifying users or devices without cookies or sessions. It is not a full proof technique, but it has been shown to be statistically significant at accurately identifying devices.

First, you'll need to import the library. You can do it in different ways, depending on your environment:

// in an ES6 environment:
import { ClientJS } from 'clientjs';

// via CommonJS imports:
const { ClientJS } \= require('clientjs');

// in a browser, when using a script tag:
const ClientJS \= window.ClientJS;

After having imported the library, simply create a new `ClientJS` object and call the `getFingerprint()` method which will return the browser/device fingerprint as a 32bit integer hash ID.

// Create a new ClientJS object
const client \= new ClientJS();

// Get the client's fingerprint id
const fingerprint \= client.getFingerprint();

// Print the 32bit hash id to the console
console.log(fingerprint);

The current data-points that used to generate fingerprint 32bit integer hash ID is listed below:

-   user agent
-   screen print
-   color depth
-   current resolution
-   available resolution
-   device XDPI
-   device YDPI
-   plugin list
-   font list
-   local storage
-   session storage
-   timezone
-   language
-   system language
-   cookies
-   canvas print

Bundles
-------

For maximum flexibility, this library is distributed in 4 different pre-bundled variants for the browser:

-   `dist/client.min.js` - full distribution bundle, contains Flash and Java detection mechanisms
-   `dist/client.flash.min.js` - contains Flash detection mechanism but misses Java detection (`getJavaVersion()` will throw an error when called)
-   `dist/client.java.min.js` - contains Java detection mechanism but misses Flash detection (`getFlashVersion()` will throw an error when called)
-   `dist/client.base.min.js` - misses both, Flash and Java detection mechanisms (`getFlashVersion()` and `getJavaVersion()` will throw an error when called)

Available Methods
-----------------

Below is the current list of available methods to find information on a users browser/device.

You can find documentation on each method at clientjs.org.

const client \= new ClientJS();

client.getBrowserData();
client.getFingerprint();
client.getCustomFingerprint(...);

client.getUserAgent();
client.getUserAgentLowerCase();

client.getBrowser();
client.getBrowserVersion();
client.getBrowserMajorVersion();
client.isIE();
client.isChrome();
client.isFirefox();
client.isSafari();
client.isOpera();

client.getEngine();
client.getEngineVersion();

client.getOS();
client.getOSVersion();
client.isWindows();
client.isMac();
client.isLinux();
client.isUbuntu();
client.isSolaris();

client.getDevice();
client.getDeviceType();
client.getDeviceVendor();

client.getCPU();

client.isMobile();
client.isMobileMajor();
client.isMobileAndroid();
client.isMobileOpera();
client.isMobileWindows();
client.isMobileBlackBerry();

client.isMobileIOS();
client.isIphone();
client.isIpad();
client.isIpod();

client.getScreenPrint();
client.getColorDepth();
client.getCurrentResolution();
client.getAvailableResolution();
client.getDeviceXDPI();
client.getDeviceYDPI();

client.getPlugins();
client.isJava();
client.getJavaVersion(); // functional only in java and full builds, throws an error otherwise
client.isFlash();
client.getFlashVersion(); // functional only in flash and full builds, throws an error otherwise
client.isSilverlight();
client.getSilverlightVersion();

client.getMimeTypes();
client.isMimeTypes();

client.isFont();
client.getFonts();

client.isLocalStorage();
client.isSessionStorage();
client.isCookie();

client.getTimeZone();

client.getLanguage();
client.getSystemLanguage();

client.isCanvas();
client.getCanvasPrint();

Shoulders of Giants
-------------------

It is important to note this project owes much to other pieces great works. We had the advantage of observing how others had approached this problem.

Built Upon:

-   https://web.archive.org/web/20200714191004/https://github.com/Valve/fingerprintjs
-   https://web.archive.org/web/20200411083356/https://www.darkwavetech.com/index.php/device-fingerprint-blog
-   http://detectmobilebrowsers.com

Contributing
------------

Collaborate by forking this project and sending a Pull Request this way.

Once cloned, install all dependencies. ClientJS uses Karma as its testing environment.

# Install dependencies
$ npm install

Run Karma and enjoy coding!

$ npm test

Thanks for contributing to ClientJS! Please report any bug here.

Releasing
---------

To make a new release, use the `release-it` tool, this will guide you through the release process:

npx release-it

You can make a dry run of the release process with the following command:

npx release-it --dry-run

LICENSE
-------

Apache License 2.0
