---
project: aws-sdk-js
stars: 7627
description: AWS SDK for JavaScript in the browser and Node.js (In Maintenance Mode, End-of-Life on 09/08/2025). The AWS SDK for JavaScript v3 in the browser and Node.js is available here: https://github.com/aws/aws-sdk-js-v3
url: https://github.com/aws/aws-sdk-js
---

AWS SDK for JavaScript
======================

In Maintenance Mode as of September 8, 2024
-------------------------------------------

The AWS SDK for JavaScript v2 has entered maintenance mode on **September 8, 2024** and will be reaching end-of-support on **September 8, 2025**. During maintenance mode, AWS will limit SDK releases to address critical bug fixes and security issues only. The SDK will not receive API updates for new or existing services, or be updated to support new regions.

We recommend that you migrate to AWS SDK for JavaScript v3. For dates, additional details, and information on how to migrate, please refer to the linked announcement.

The **AWS SDK for JavaScript v3** is the latest and recommended version, which has been GA since December 2020. Here is why and how you should use **AWS SDK for JavaScript v3**. You can try our migration scripts in aws-sdk-js-codemod to migrate your application from v2 to v3.

To get help with your migration, please follow our general guidelines to open an issue and choose guidance. To give feedback on and report issues in the v3 repo, please refer to Giving feedback and contributing.

Watch this README and the AWS Developer Tools Blog for updates and announcements regarding the maintenance plans and timelines.

A maintenance mode message may be emitted by this package on startup. To suppress this message, use an environment variable:

AWS\_SDK\_JS\_SUPPRESS\_MAINTENANCE\_MODE\_MESSAGE=1 node my\_program.js

or a JavaScript setting as follows:

var SDK \= require('aws-sdk');
require('aws-sdk/lib/maintenance\_mode\_message').suppress \= true;

Table of Contents:
------------------

-   Getting Started
-   Getting Help
-   Contributing

Getting Started
---------------

How To Install
--------------

### In the Browser

To use the SDK in the browser, simply add the following script tag to your HTML pages:

```
<script src="https://sdk.amazonaws.com/js/aws-sdk-2.1692.0.min.js"></script>
```

You can also build a custom browser SDK with your specified set of AWS services. This can allow you to reduce the SDK's size, specify different API versions of services, or use AWS services that don't currently support CORS if you are working in an environment that does not enforce CORS. To get started:

http://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/building-sdk-for-browsers.html

The AWS SDK is also compatible with browserify.

For browser-based web, mobile and hybrid apps, you can use AWS Amplify Library which extends the AWS SDK and provides an easier and declarative interface.

### In Node.js

The preferred way to install the AWS SDK for Node.js is to use the npm package manager for Node.js. Simply type the following into a terminal window:

npm install aws-sdk

### In React Native

To use the SDK in a react native project, first install the SDK using npm:

npm install aws-sdk

Then within your application, you can reference the react native compatible version of the SDK with the following:

var AWS \= require('aws-sdk/dist/aws-sdk-react-native');

Alternatively, you can use AWS Amplify Library which extends AWS SDK and provides React Native UI components and CLI support to work with AWS services.

### Using Bower

You can also use Bower to install the SDK by typing the following into a terminal window:

bower install aws-sdk-js

Usage with TypeScript
---------------------

The AWS SDK for JavaScript bundles TypeScript definition files for use in TypeScript projects and to support tools that can read `.d.ts` files. Our goal is to keep these TypeScript definition files updated with each release for any public api.

### Pre-requisites

Before you can begin using these TypeScript definitions with your project, you need to make sure your project meets a few of these requirements:

-   Use latest version of TypeScript. We recommend 4.x+
    
-   Includes the TypeScript definitions for node. You can use npm to install this by typing the following into a terminal window:
    
    npm install --save-dev @types/node
    
-   If you are targeting at es5 or older ECMA standards, your `tsconfig.json` has to include `'es5'` and `'es2015.promise'` under `compilerOptions.lib`. See tsconfig.json for an example.
    

### In the Browser

To use the TypeScript definition files with the global `AWS` object in a front-end project, add the following line to the top of your JavaScript file:

/// <reference types="aws-sdk" />

This will provide support for the global `AWS` object.

### In Node.js

To use the TypeScript definition files within a Node.js project, simply import `aws-sdk` as you normally would.

In a TypeScript file:

// import entire SDK
import AWS from 'aws-sdk';
// import AWS object without services
import AWS from 'aws-sdk/global';
// import individual service
import S3 from 'aws-sdk/clients/s3';

**NOTE:** You need to add `"esModuleInterop": true` to compilerOptions of your `tsconfig.json`. If not possible, use like `import * as AWS from 'aws-sdk'`.

In a JavaScript file:

// import entire SDK
var AWS \= require('aws-sdk');
// import AWS object without services
var AWS \= require('aws-sdk/global');
// import individual service
var S3 \= require('aws-sdk/clients/s3');

### With React

To create React applications with AWS SDK, you can use AWS Amplify Library which provides React components and CLI support to work with AWS services.

### With Angular

Due to the SDK's reliance on node.js typings, you may encounter compilation issues when using the typings provided by the SDK in an Angular project created using the Angular CLI.

To resolve these issues, either add `"types": ["node"]` to the project's `tsconfig.app.json` file, or remove the `"types"` field entirely.

AWS Amplify Library provides Angular components and CLI support to work with AWS services.

### Known Limitations

There are a few known limitations with the bundled TypeScript definitions at this time:

-   Service client typings reflect the latest `apiVersion`, regardless of which `apiVersion` is specified when creating a client.
-   Service-bound parameters use the `any` type.

Getting Help
============

The best way to interact with our team is through GitHub. You can open an issue and choose from one of our templates for bug reports, feature requests or guidance. You may also find help on community resources such as StackOverFlow with the tag #aws-sdk-js. If you have a support plan with AWS Support, you can also create a new support case.

Please make sure to check out our resources too before opening an issue:

-   Our Developer Guide and API reference
-   Our Changelog for recent changes.
-   Our code examples.

Please see SERVICES.md for a list of supported services.

Maintenance and support for SDK major versions
==============================================

For information about maintenance and support for SDK major versions and their underlying dependencies, see the following in the AWS SDKs and Tools Shared Configuration and Credentials Reference Guide:

-   AWS SDKs and Tools Maintenance Policy
-   AWS SDKs and Tools Version Support Matrix

Contributing
============

We welcome community contributions and pull requests. See CONTRIBUTING.md for information on how to set up a development environment and submit code.

License
-------

This SDK is distributed under the Apache License, Version 2.0, see LICENSE.txt and NOTICE.txt for more information.
