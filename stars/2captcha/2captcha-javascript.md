---
project: 2captcha-javascript
stars: 68
description: JavaScript library for easy integration with the API of 2captcha captcha solving service to bypass reCAPTCHA, funcaptcha, geetest and solve any other captchas.
url: https://github.com/2captcha/2captcha-javascript
---

JavaScript module for 2Captcha API (captcha solver)
===================================================

The easiest way to quickly integrate the 2Captcha captcha-solving service into your code and automate the solving of any type of captcha. Examples of API requests for different captcha types are available on the JavaScript captcha solver page.

-   JavaScript module for 2Captcha API (captcha solver)
    -   Installation
    -   Configuration
        -   TwoCaptcha instance options
    -   Solve captcha
        -   Image Captcha
        -   reCAPTCHA v2
        -   reCAPTCHA v3
        -   FunCaptcha
        -   GeeTest
        -   GeeTest V4
        -   Yandex Smart Captcha
        -   Lemin Cropped Captcha
        -   Cloudflare Turnstile
        -   Amazon WAF
        -   Capy
        -   ClickCaptcha
        -   DataDome CAPTCHA
        -   CyberSiARA
        -   MTCaptcha
        -   Friendly Captcha
        -   Bounding Box Method
        -   Grid
        -   Text Captcha
        -   Canvas
        -   Rotate
        -   KeyCaptcha
        -   Cutcaptcha
        -   Tencent
        -   atbCAPTCHA
        -   Audio Captcha
    -   Other methods
        -   goodReport
        -   badReport
        -   balance
    -   Proxies
    -   Examples
    -   Examples using Puppeteer
-   Useful articles
-   Get in touch
-   Join the team 👪
-   License
    -   Graphics and Trademarks

Installation
------------

This package can be installed with NPM:

npm install @2captcha/captcha-solver

or Yarn:

yarn add @2captcha/captcha-solver

Configuration
-------------

TwoCaptcha instance can be created like this:

const TwoCaptcha \= require("@2captcha/captcha-solver")
const solver \= new TwoCaptcha.Solver("<Your 2captcha api key>")

Also, there are a few options that can be configured:

const apiKey \= 'YOUR\_API\_KEY'
const pollingInterval \= 10

const solver \= new TwoCaptcha.Solver(apiKey, pollingInterval)

### TwoCaptcha instance options

Option

Default value

Description

apiKey

\-

Your API key

pollingInterval

5000

Interval in milliseconds between requests to the `res.php` API endpoint. Setting values less than 5 seconds is not recommended

Solve captcha
-------------

When you submit any image-based captcha use can provide additional options to help 2captcha workers to solve it properly.

### Captcha options

Option

Default Value

Description

numeric

0

Defines if the captcha contains numeric or other symbols see more info in the API docs

min\_len

0

minimal answer length

max\_len

0

maximum answer length

phrase

0

defines if the answer contains multiple words or not

regsense

0

defines if the answer is case sensitive

calc

0

defines captcha requires calculation

lang

\-

defines the captcha language; see the list of supported languages

textinstructions

\-

hint or task text shown to workers with the captcha

Below you can find basic examples for every captcha type, check out the code below.

### Image captcha

API method description.

To bypass a normal captcha (distorted text on an image) use the following method. This method can also be used to recognize any text in an image.

const imageBase64 \= fs.readFileSync("./examples/media/imageCaptcha\_6e584.png", "base64")

solver.imageCaptcha({
    body: imageBase64,
    numeric: 4,
    min\_len: 5,
    max\_len: 5
})
.then((res) \=> {
  console.log(res);
})
.catch((err) \=> {
  console.log(err);
})

### reCAPTCHA V2

API method description.

Use the following method to solve reCAPTCHA V2 and obtain a token to bypass the protection.

solver.recaptcha({
  pageurl: 'https://2captcha.com/demo/recaptcha-v2',
  googlekey: '6LfD3PIbAAAAAJs\_eEHvoOl75\_83eXSqpPSRFJ\_u'
})
.then((res) \=> {
  console.log(res);
})
.catch((err) \=> {
  console.log(err);
})

### reCAPTCHA V3

API method description.

This method provides a reCAPTCHA V3 solver and returns a token.

solver.recaptcha({
    pageurl: 'https://2captcha.com/demo/recaptcha-v3',
    googlekey: '6Lcyqq8oAAAAAJE7eVJ3aZp\_hnJcI6LgGdYD8lge',
    version: "v3",
    min\_score: "0.4",
    action: 'demo\_action'
})
.then((res) \=> {
  console.log(res);
})
.catch((err) \=> {
  console.log(err);
})

### FunCaptcha

API method description.

FunCaptcha (Arkoselabs) solving method. Returns a token.

solver.funCaptcha({
  pageurl: "https://funcaptcha.com/tile-game-lite-mode/fc/api/nojs/?pkey=804380F4-6844-FFA1-ED4E-5877CA1F1EA4&lang=en",
  publickey: "804380F4-6844-FFA1-ED4E-5877CA1F1EA4"
})
.then((res) \=> {
  console.log(res);
})
.catch((err) \=> {
  console.log(err);
})

### GeeTest Captcha

API method description.

Method to solve GeeTest puzzle captcha. Returns a set of tokens as JSON.

// Read more about \`challenge\` on the page https://2captcha.com/p/geetest
solver.geetest({ 
  pageurl: 'https://2captcha.com/demo/geetest',
  gt: '81388ea1fc187e0c335c0a8907ff2625',
  challenge: '<you need to get a new challenge value each time>'
})
.then((res) \=> {
  console.log(res);
})
.catch((err) \=> {
  console.log(err);
})

### GeeTest V4 Captcha

API method description.

Use this method to solve GeeTest v4. Returns the response in JSON.

solver.geetestV4({
  pageurl: 'https://2captcha.com/demo/geetest-v4',
  captcha\_id: 'e392e1d7fd421dc63325744d5a2b9c73'
})
.then((res) \=> {
  console.log(res);
})
.catch((err) \=> {
  console.log(err);
})

### Yandex Smart Captcha

Use this method to solve Yandex Smart Captcha and obtain a token to bypass the protection.

solver.yandexSmart({ 
  pageurl: "https://captcha-api.yandex.ru/demo",
  sitekey: "FEXfAbHQsToo97VidNVk3j4dC74nGW1DgdxjtNB9"
 })
.then((res) \=> {
  console.log(res);
})
.catch((err) \=> {
  console.log(err);
})

### Lemin Cropped Captcha

API method description.

Use this method to solve Lemin and obtain a token to bypass the protection.

solver.lemin({
  pageurl:'https://2captcha.com/demo/lemin', 
  captcha\_id: 'CROPPED\_3dfdd5c\_d1872b526b794d83ba3b365eb15a200b',
  div\_id: 'lemin-cropped-captcha',
  api\_server: 'api.leminnow.com'
})
.then((res) \=> {
  console.log(res);
})
.catch((err) \=> {
  console.log(err);
})

### Cloudflare Turnstile

API method description.

Use this method to solve Cloudflare Turnstile. Returns JSON with the token.

Turnstile captcha has two types, one of them is Cloudflare Turnstile Challenge page. For Turnstile Challenge page cases, we have a demo. Try this demo if you need to solve Cloudflare Turnstile Challenge page captcha.

solver.cloudflareTurnstile({
    pageurl: "https://app.nodecraft.com/login",
    sitekey: "0x4AAAAAAAAkg0s3VIOD10y4"    
})
.then((res) \=> {
    console.log(res);
})
.catch((err) \=> {
    console.log(err);
})

### Amazon WAF

API method description.

Use this method to solve Amazon WAF Captcha also known as AWS WAF Captcha is a part of Intelligent threat mitigation for Amazon AWS. Returns JSON with the token.

//INFO: The \`context\` value is dynamic, it is necessary to take the actual value from the page each time.
solver.amazonWaf({
  pageurl: "https://non-existent-example.execute-api.us-east-1.amazonaws.com/latest",
  sitekey: "AQIDAHjcYu/GjX+QlghicBgQ/7bFaQZ+m5FKCMDnO+vTbNg96AHMDLodoefdvyOnsHMRt...",
  context: "9BUgmlm48F92WUoqv97a49ZuEJJ50TCk9MVr3C7WMtQ0X6flVbufM4n8mjFLmbLVAPgaQ...",
  iv: "CgAHbCe2GgAAAAAj",
})
.then((res) \=> {
  console.log(res);
})
.catch((err) \=> {
  console.log(err);
})

### Capy

API method description.

Token-based method to bypass Capy puzzle captcha.

solver.capyPuzzle({
    pageurl: "https://www.capy.me/account/register/",
    captchakey: "PUZZLE\_Cme4hZLjuZRMYC3uh14C52D3uNms5w"
})
.then((res) \=> {
    console.log(res);
})
.catch((err) \=> {
    console.log(err);
})

### DataDome CAPTCHA

API method description.

Use this method to solve DataDome and obtain a token to bypass the protection.

Important

To solve the DataDome captcha, you must use a proxy. It is recommended to use residential proxies.

solver.dataDome({
    pageurl: "https://rendezvousparis.hermes.com/client/register",
    captcha\_url: "https://geo.captcha-delivery.com/captcha/?initialCid=AHrlqAAAAAMAEuQtkf4k1c0ABZhYZA%3D%3D&hash=789361B674144528D0B7EE76B35826&cid=mY4z7GNmh7Nt1lAFwpbNHAOcWPhyPgjHD2K1Pm~Od1iEKYLUnK3t7N2ZGUj8OqDK65cnwJHtHwd~t902vlwpSBA5l4ZHbS1Qszv~jEuEUJNQ\_jMAjar2Kj3kq20MRJYh&t=fe&referer=https%3A%2F%2Frendezvousparis.hermes.com%2Fclient%2Fregister&s=40119&e=67fef144ac1a54dbd7507776367d2f9d5e36ec3add17fa22f3cb881db8385838",
    userAgent: "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/118.0.0.0 Safari/537.36",
    proxy: "login:password@1.2.3.4:8888", // The (Username : Password @ Address : Port) of our chosen proxy
    proxytype: "http" // The 'Type' of proxy, http, https, socks, ect.
})
.then((res) \=> {
console.log(res);
})
.catch((err) \=> {
console.log(err);
})

### CyberSiARA

API method description.

Use this method to solve CyberSiARA and obtain a token to bypass the protection.

solver.cyberSiARA({
    pageurl: "https://www.cybersiara.com/book-a-demo",
    master\_url\_id: "OXR2LVNvCuXykkZbB8KZIfh162sNT8S2",
    userAgent: "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/118.0.0.0 Safari/537.36"
})
.then((res) \=> {
console.log(res);
})
.catch((err) \=> {
console.log(err);
})

### MTCaptcha

API method description.

Use this method to solve MTCaptcha and obtain a token to bypass the protection.

solver.mtCaptcha({
    pageurl: "https://service.mtcaptcha.com/mtcv1/demo/index.html",
    sitekey: "MTPublic-DemoKey9M"
})
.then((res) \=> {
console.log(res);
})
.catch((err) \=> {
console.log(err);
})

### Friendly Captcha

API method description.

Use this method to solve Friendly Captcha and obtain a token to bypass the protection.

Important

To successfully use the received token, the captcha widget must not be loaded on the page. To do this, you need to abort request to `/friendlycaptcha/...module.min.js` on the page. When the captcha widget is already loaded on the page, there is a high probability that the received token will not work.

solver.friendlyCaptcha({
    pageurl: "https://geizhals.de/?liftban=1&from=/455973138?fsean=5901747021356",
    sitekey: "FCMST5VUMCBOCGQ9"
})
.then((res) \=> {
console.log(res);
})
.catch((err) \=> {
console.log(err);
})

### ClickCaptcha

API method description.

The ClickCaptcha method returns the coordinates of points on the captcha image. It can be used if you need to click on particular points in the image.

const imageBase64 \= fs.readFileSync("./tests/media/coordinates.jpg", "base64")

solver.coordinates({
    body: imageBase64,
    textinstructions: 'Select all photos containing the boat'
 })
.then((res) \=> {
    console.log(res);
})
.catch((err) \=> {
    console.log(err);
})

### Bounding Box Method

API method description.

Use Bounding Box Method when you need to select objects on the image. To do this, you need to pass the markup instructions and image for markup. The instructions can be sent as text or as an image encoded in `base64` format.

Important

You must to send instruction `imginstructions` or `textinstructions`.

solver.boundingBox({ 
  image: "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAR4AAACwCAIAAAB...",
  textinstructions: "Circle all the cars in the image.",
})
.then((res) \=> {
    console.log(res);
})
.catch((err) \=> {
    console.log(err);
})

### Grid

API method description.

This method allows to solve any captcha where image can be divided into equal parts like reCAPTCHA V2. A grid is applied above the image. And you receive the numbers clicked boxes.

Important

You must to send instruction `imginstructions` or `textinstructions`.

solver.grid({ 
  body: "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAR4AAACwCAIAAAB...",
  textinstructions: "Select cars in the image"
})
.then((res) \=> {
    console.log(res);
})
.catch((err) \=> {
    console.log(err);
})

### Text Captcha

API method description.

This method can be used to bypass a captcha that requires answering a question provided in clear text.

solver.textCaptcha({
  textcaptcha: "If tomorrow is Saturday, what day is today?",
  lang: 'en'
})
.then((res) \=> {
    console.log(res);
})
.catch((err) \=> {
    console.log(err);
})

### Canvas

API method description.

The canvas method can be used when you need to draw a line around an object on an image. Returns a set of points' coordinates to draw a polygon.

solver.canvas({
    body: 'iVBORw0KGgoAAAANSgAAAcIA...',
    imginstructions: '/9j/4AAQSkZJRgABAQEA...',
    textinstructions: 'Highlight the red CIRCLE'
})
.then((res) \=> {
    console.log(res);
})
.catch((err) \=> {
    console.log(err);
})

### Rotate

API method description.

This method can be used to solve a captcha that asks to rotate an object. It is mostly used to bypass FunCaptcha. Returns the rotation angle.

solver.rotate({
  body: imageBase64,
  textinstructions: "Rotate the object to the correct position"
})
.then((res) \=> {
    console.log(res);
})
.catch((err) \=> {
    console.log(err);
})

### KeyCaptcha

API method description.

Token-based method to solve KeyCaptcha.

solver.keyCaptcha({
    pageurl: "https://2captcha.com/demo/keycaptcha",
    userId: '184015',
    sessionId: '0917788cad24ad3a69813c4fcd556061',
    webServerSign: '02f7f9669f1269595c4c69bcd4a3c52e',
    webServerSign2: 'd888700f6f324ec0f32b44c32c50bde1'
})
.then((res) \=> {
    console.log(res);
})
.catch((err) \=> {
    console.log(err);
})

### Cutcaptcha

API method description.

Use this method to solve Cutcaptcha. Returns the response in JSON.

solver.cutCaptcha({
    pageurl: "https://mysite.com/page/with/cutcaptcha",
    misery\_key: "098e6a849af406142e3150dbf4e6d0538db2b51f", 
    api\_key: "SAs61IAI",
})
.then((res) \=> {
console.log(res);
})
.catch((err) \=> {
console.log(err);
})

### Tencent

API method description.

Use this method to solve Tencent captcha. Returns the response in JSON.

solver.tencent({
    pageurl: "https://mysite.com/page/with/tencent",
    appId: "189956587"  
})
.then((res) \=> {
console.log(res);
})
.catch((err) \=> {
console.log(err);
})

### atbCAPTCHA

API method description.

Use this method to solve atbCAPTCHA challenge. Returns a token to bypass the captcha.

solver.atbCaptcha({
    pageurl: "https://mysite.com/page/with/atbCAPTCHA",
    appId: "af25e409b33d722a95e56a230ff8771c",
    apiServer: "https://cap.aisecurius.com"
})
.then((res) \=> {
console.log(res);
})
.catch((err) \=> {
console.log(err);
})

### Audio Captcha

API method description.

Use the following method to bypass an audio captcha (`mp3` formats only). You must provide the language as `lang = 'en'`. Supported languages are "en", "ru", "de", "el", "pt", "fr".

solver.audio({
  body: "SUQzBAAAAAAAHFRTU0UAAAA...",
  lang: "en"
})
.then((res) \=> {
  console.log(res);
})
.catch((err) \=> {
  console.log(err);
})

Other methods
-------------

### goodReport

API method description.

Use this method to report good captcha answer.

solver.goodReport('7031846604')

### badReport

API method description.

Use this method to report bad captcha answer.

solver.badReport('7031854546')

### balance

API method description.

Use this method to get your account's balance.

solver.balance()
.then((res) \=> {
    console.log(res)
})

Proxies
-------

You can pass your proxy as an additional argument for methods: recaptcha, funcaptcha, geetest, geetest v4, keycaptcha, capy puzzle, lemin, turnstile, amazon waf, DataDome, CyberSiARA, MTCaptcha, Friendly Captcha and etc. The proxy will be forwarded to the API to solve the captcha.

We have our own proxies that we can offer you. Buy residential proxies for avoid restrictions and blocks. Quick start.

Solving reCAPTCHA V2 using proxy:

solver.recaptcha({
    pageurl: 'https://2captcha.com/demo/recaptcha-v2',
    googlekey: '6LfD3PIbAAAAAJs\_eEHvoOl75\_83eXSqpPSRFJ\_u',
    proxy: 'HTTPS',
    proxytype: 'login:password@123.123.123.123:3128'
})

Examples
--------

Examples of solving all supported captcha types are located in the examples directory.

Examples using Puppeteer
------------------------

Also we have a separate repositories you can find examples of solving captcha using Puppeteer. At the moment we have implemented examples of bypassing Cloudflare Challenge page and reCAPTCHA. Links:

-   Cloudflare Bypassing Demo using Puppeteer
-   Solving reCAPTCHA V2 using Puppeteer and clicks
-   Custom Slider Captcha Demo

Useful articles
---------------

-   How to bypass captcha using JavaScript
-   Bypassing Cloudflare Challenge with Puppeteer and 2Captcha
-   How to bypass Geetest v4 CAPTCHA
-   Automatic reCAPTCHA V3 resolution - a tutorial for developers and customers

Get in touch
------------

Join the team 👪
----------------

There are many ways to contribute, of which development is only one! Find your next job. Open positions: AI experts, scrapers, developers, technical support, and much more! 😍

License
-------

The code in this repository is licensed under the MIT License. See the LICENSE file for more details.

### Graphics and Trademarks

The graphics and trademarks included in this repository are not covered by the MIT License. Please contact support for permissions regarding the use of these materials.
