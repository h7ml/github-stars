---
project: anticaptcha-npm
stars: 11
description: Anti-Captcha NPM library
url: https://github.com/anti-captcha/anticaptcha-npm
---

Official Anti-Captcha.com npm module
------------------------------------

### Contents

-   Intro
-   Installation
-   Request API key balance
-   Earn with us
-   Image Captcha
-   Recaptcha V2
-   Recaptcha V3
-   Hcaptcha
-   Turnstile
-   Antigate tasks
-   Funcaptcha
-   Geetest v3
-   Geetest v4
-   Image to coordinates
-   Amazon WAF

Official anti-captcha.com npm package for solving images with text, Recaptcha v2/v3 Enterprise/non-Enterpise, Funcaptcha, GeeTest, HCaptcha.

Anti-captcha is an oldest and cheapest web service dedicated to solving captchas by human workers from around the world. By solving captchas with us you help people in poorest regions of the world to earn money, which not only cover their basic needs, but also gives them ability to financially help their families, study and avoid jobs where they're simply not happy.

To use the service you need to register and topup your balance. Prices start from $0.0005 per image captcha and $0.002 for Recaptcha. That's $0.5 per 1000 for images and $2 for 1000 Recaptchas.

For more technical information and articles visit our documentation page.

### Module installation:

npm install @antiadmin/anticaptchaofficial

### Import and check your balance in sync mode:

(async() \=> {
    
    const ac \= require("@antiadmin/anticaptchaofficial");
    ac.setAPIKey('YOUR\_API\_KEY');
    try {
        const balance \= await ac.getBalance();
        console.log(\`my balance is $${balance}\`);
        if (balance <= 0) {
            throw "negative balance"
        }
        console.log("solving a captcha..")
        // const token = await ac.solveRecaptchaV2Proxyless('http://DOMAIN.COM', 'WEBSITE\_KEY');
        // const fs = require('fs');
        // const text = await ac.solveImage(fs.readFileSync('captcha.png', { encoding: 'base64' }), true)
    } catch (e) {
        console.log("got error: ", e.toString());
    }
    
})();

Or do the same with promises:

const ac \= require("@antiadmin/anticaptchaofficial");
ac.setAPIKey('YOUR\_API\_KEY');
ac.getBalance()
     .then(balance \=> {
         console.log('my balance is $' + balance)
         if (balance <= 0) {
             return false;
         }
         console.log("solving a captcha..")
         // ac.solveRecaptchaV2Proxyless('http://DOMAIN.COM', 'WEBSITE\_KEY')
         //     .then(token => {
         //         console.log('Got g-response:', token)
         //         // do something
         //     })
         //     .catch(error => {
         //         console.log('test received error ' + error)
         //         return false;
         //     });
     })
     .catch(error \=> console.log('received error '+error))

Disable verbose output to console:

ac.shutUp();

  
Request subscription credits balance:

const remainingCredits \= await ac.getCreditsBalance();

  

### Earn with Anti-Captcha

Specify softId to earn **10% commission** from all captcha spendings with your app. Get your softId in Developers Center.

ac.setSoftId(SOFT\_ID\_NUMBER);

### Solve image captcha:

const fs \= require('fs');
const captcha \= fs.readFileSync('captcha.png', { encoding: 'base64' });

// Additional flags, see https://anti-captcha.com/apidoc/task-types/ImageToTextTask for description:
// ac.settings.phrase = true;                  // 2 words
// ac.settings.case = true;                    // case sensitivity
// ac.settings.numeric = 1;                    // only numbers
// ac.settings.comment = "only green letters"; // text comment for workers
// ac.settings.math = true;                    // math operation like 50+2
// ac.settings.minLength = 1;                  // minimum amount of characters
// ac.settings.maxLength = 10;                 // maximum number of characters
// ac.settings.languagePool = 'en';            // language pool
const text \= await ac.solveImage(captcha, true);

Report last solved image captcha as incorrect (must read this before using):

await ac.reportIncorrectImageCaptcha();

* * *

### Recaptcha V2 without proxy:

ac.settings.recaptchaDataSValue \= 'set me for google.com domains';
const gresponse \= ac.solveRecaptchaV2Proxyless('http://DOMAIN.COM', 'WEBSITE\_KEY');
console.log('g-response: '+gresponse);
console.log('google cookies:');
console.log(ac.getCookies());

Learn what to do with g-response in this article.

Report last solved Recaptcha v2/v3 as incorrect (must read this before using):

await ac.reportIncorrectRecaptcha();

Report Recaptcha v3 as correctly solved (more info here before using):

await ac.reportCorrectRecaptcha();

### Recaptcha V2 with proxy:

const gresponse \= await ac.solveRecaptchaV2ProxyOn('http://DOMAIN.COM',
    'WEBSITE\_KEY',
    'http', //http, socks4, socks5
    'PROXY\_IP',
    'PROXY\_PORT',
    'PROXY\_LOGIN',
    'PROXY\_PASSWORD',
    'Mozilla/5.0 (Macintosh; Intel Mac OS X 10\_11\_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/52.0.2743.116',
    'some=cookies');

Solve Recaptcha V2-invisible (note the 3rd parameter "true"):

const gresponse \= await ac.solveRecaptchaV2Proxyless('http://DOMAIN.COM', 'WEBSITE\_KEY', true)

* * *

### Recaptcha V3:

const gresponse \= await ac.solveRecaptchaV3('http://DOMAIN.COM',
    'WEBSITE\_KEY',
    0.3, //minimum score required: 0.3, 0.7 or 0.9
    'PAGE\_ACTION\_CAN\_BE\_EMPTY');

Solve Recaptcha V2 Enterprise without proxy:

const gresponse \= await ac.solveRecaptchaV2EnterpriseProxyless(
    'http://DOMAIN.COM', 
    'WEBSITE\_KEY', 
    {   //enterprise payload:
        "s" : "SOME\_TOKEN",
        "custom\_parameter" : "string\_number\_boolean" 
    });

* * *

### HCaptcha without proxy:

const token \= await ac.solveHCaptchaProxyless('http://DOMAIN.COM', 'WEBSITE\_KEY', 'FULL USER AGENT HERE');

// use this userAgent for posting the form with token!
const userAgent \= ac.getHcaptchaUserAgent();

//some Hcaptchas also produce "respkey" value, this is how to get it:
const respKey \= ac.getHcaptchaRespKey();

Report last solved Hcaptcha as incorrect:

await ac.reportIncorrectHcaptcha();

* * *

### Turnstile without proxy:

const token \= await ac.solveTurnstileProxyless('http://DOMAIN.COM', 'WEBSITE\_KEY', 'optional\_action', 'optional\_cData\_token');

* * *

### Turnstile with proxy:

const token \= await ac.solveTurnstileProxyOn('http://DOMAIN.COM',
    'WEBSITE\_KEY',
    'http', //http, socks4, socks5
    'PROXY\_IP',
    'PROXY\_PORT',
    'PROXY\_LOGIN',
    'PROXY\_PASSWORD',
    'optional\_action',
    'optional\_cData\_token');

* * *

### AntiGate Tasks:

const solution \= await ac.solveAntiGateTask(
    'http://antigate.com/logintest.php', 
    'Sign-in and wait for control text', 
    { 
        "login\_input\_css": "#login",
        "login\_input\_value": "the login",
        "password\_input\_css": "#password",
        "password\_input\_value": "the password",
        "control\_text": "You have been logged successfully" 
    });
console.log('cookies: ', solution.cookies);
console.log('localStorage: ', solution.localStorage);
console.log('url: ', solution.url);

same with a proxy:

const solution \= await ac.solveAntiGateTask(
    'http://antigate.com/logintest.php', 
    'Sign-in and wait for control text', 
    { 
        "login\_input\_css": "#login",
        "login\_input\_value": "the login",
        "password\_input\_css": "#password",
        "password\_input\_value": "the password",
        "control\_text": "You have been logged successfully" 
    },
    'PROXY\_IP',
    'PROXY\_PORT',
    'PROXY\_LOGIN',
    'PROXY\_PASSWORD');

Send a task with a delayed variable and push it after a few seconds:

const taskId \= await ac.sendAntiGateTask('http://antigate.com/logintest2fa.php',
    'Sign-in with 2FA and wait for control text',
    {
        "login\_input\_css": "#login",
        "login\_input\_value": "the login",
        "password\_input\_css": "#password",
        "password\_input\_value": "the password",
        "2fa\_input\_css": "#2facode",
        "2fa\_input\_value": "\_WAIT\_FOR\_IT\_",
        "control\_text": "You have been logged successfully"
    });
await ac.delay(5000); //simulate a delay in 2FA retrieval
await ac.pushAntiGateVariable('2fa\_input\_value', '349001');
const solution \= await ac.waitForResult(taskId);

console.log('solution:');
console.log(solution);

### Funcaptcha / Arkoselabs without proxy:

//optional data blob:
ac.settings.funcaptchaDataBlob \= 'blob value here is any, or leave it empty';
const token \= await ac.solveFunCaptchaProxyless(
    'https://www.thewebsite.com/path',
    'site-key');

### Funcaptcha / Arkoselabs via proxy:

//optional data blob:
ac.settings.funcaptchaDataBlob \= 'blob value here is any, or leave it empty';
const token \= await ac.solveFunCaptchaProxyOn(
    'https://www.thewebsite.com/path',
    'site-key', 
    'http',
    '1.2.3.4',
    3128,
    'proxy-login',
    'proxy-password',
    'Mozilla/5.0 (Macintosh; Intel Mac OS X 10\_11\_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/52.0.2743.116',
    '');

* * *

### Geetest version 3 without proxy

See tutorial how to find these parameters.

const token \= await ac.solveGeeTestProxyless(
    'https://www.thewebsite.com/path',
    'gt key 32 bytes',
    'challenge value 32 bytes',
    'optional.api-domain.com');

### Geetest version 4 without proxy

See tutorial how to find these parameters.

const token \= await ac.solveGeeTestV4Proxyless(
    'https://www.thewebsite.com/path',
    'captchaId key 32 bytes',
    'optional.api-domain.com',
    {
        'riskType': 'slide' //example
    });

* * *

### Image to coordinates

const fs \= require('fs');
const captcha \= fs.readFileSync('captcha.png', { encoding: 'base64' });
const coordinates \= await ac.solveImageToCoordinates(captcha, "Select all objects in specified order", "points");

Report last solved image captcha as incorrect:

await ac.reportIncorrectImageCaptcha();

* * *

### Prosopo captcha

const token \= await ac.solveProsopoProxyless('http://DOMAIN.COM', 'WEBSITE\_KEY');

* * *

Solve Prosopo captcha with proxy:

const token \= await ac.solveProsopoProxyOn('http://DOMAIN.COM',
    'WEBSITE\_KEY',
    'http', //http, socks4, socks5
    'PROXY\_IP',
    'PROXY\_PORT',
    'PROXY\_LOGIN',
    'PROXY\_PASSWORD');

* * *

### Friendly Captcha without proxy:

const token \= await ac.solveFriendlyCaptchaProxyless('http://DOMAIN.COM', 'WEBSITE\_KEY');

* * *

Solve Friendly Captcha with proxy:

const token \= await ac.solveFriendlyCaptchaProxyOn('http://DOMAIN.COM',
    'WEBSITE\_KEY',
    'http', //http, socks4, socks5
    'PROXY\_IP',
    'PROXY\_PORT',
    'PROXY\_LOGIN',
    'PROXY\_PASSWORD');

* * *

### Amazon WAF:

Two options here:

1.  When captcha is at the bot filtering page and you need aws-was-token cookie:

#### without proxy:

const token \= await ac.solveAmazonProxyless('http://DOMAIN.COM', 
    'key\_value\_from\_window.gokuProps\_object',
    'iv\_value\_from\_window.gokuProps\_object',
    'context\_value\_from\_window.gokuProps\_object',
    'https://e9b10f157f38.9a96e8b4.us-gov-west-1.captcha.awswaf.com/e9b10f157f38/76cbcde1c834/2a564e323e7b/captcha.js', //optional
    'https://e9b10f157f38.9a96e8b4.us-gov-west-1.token.awswaf.com/e9b10f157f38/76cbcde1c834/2a564e323e7b/challenge.js'  //optional
); 

#### with proxy:

const token \= await ac.solveAmazonProxyOn('http://DOMAIN.COM',
    'key\_value\_from\_window.gokuProps\_object',
    'http', //http, socks4, socks5
    'PROXY\_IP',
    'PROXY\_PORT',
    'PROXY\_LOGIN',
    'PROXY\_PASSWORD',
    'iv\_value\_from\_window.gokuProps\_object',
    'context\_value\_from\_window.gokuProps\_object',
    'https://e9b10f157f38.9a96e8b4.us-gov-west-1.captcha.awswaf.com/e9b10f157f38/76cbcde1c834/2a564e323e7b/captcha.js', //optional
    'https://e9b10f157f38.9a96e8b4.us-gov-west-1.token.awswaf.com/e9b10f157f38/76cbcde1c834/2a564e323e7b/challenge.js'  //optional
);

1.  When captcha is a standalone widget which is triggered by user's action:

#### without proxy:

const token \= await ac.solveAmazonWidgetProxyless('http://DOMAIN.COM', 
    'widget\_api\_key',     // get key from AwsWafCaptcha.renderCaptcha function
    'https://164cb210e333.edge.captcha-sdk.awswaf.com/164cb210e333/jsapi.js' // full path to jsapi.js integration script
); 

#### with proxy:

const token \= await ac.solveAmazonWidgetProxyOn('http://DOMAIN.COM',
    'widget\_api\_key',
    'https://164cb210e333.edge.captcha-sdk.awswaf.com/164cb210e333/jsapi.js', // full path to jsapi.js integration script
    'http', //http, socks4, socks5
    'PROXY\_IP',
    'PROXY\_PORT',
    'PROXY\_LOGIN',
    'PROXY\_PASSWORD'
);

For more details visit Anti-Captcha Amazon WAF documentation.

* * *

Other available task types with similar method calls, see source code:

await ac.solveRecaptchaV2EnterpriseProxyOn( ... ); //Recaptcha V2 Enterprise with proxy
await ac.solveRecaptchaV3Enterprise( ... ); //Recaptcha V3 Enterprise
await ac.solveHCaptchaProxyOn( ... ); //hCaptcha with proxy
await ac.solveGeeTestProxyOn( ... ); //Solve Geetest with proxy
await ac.solveGeeTestV4ProxyOn( ... ); //Bypass Geetest V4 with proxy
