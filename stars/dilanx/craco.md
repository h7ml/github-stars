---
project: craco
stars: 7455
description: Create React App Configuration Override, an easy and comprehensible configuration layer for Create React App.
url: https://github.com/dilanx/craco
---

CRACO
=====

**C**reate **R**eact **A**pp **C**onfiguration **O**verride, an easy and comprehensible configuration layer for create-react-app.

**Find config docs, API docs, plugins, and example configs at craco.js.org!**

  

Get all the benefits of Create React App **and** customization without using 'eject' by adding a single configuration (e.g. `craco.config.js`) file at the root of your application and customize your ESLint, Babel, PostCSS configurations and many more.

1.  Install the latest version of the package from npm as a dev dependency:
    
    ```
    npm i -D @craco/craco
    ```
    
2.  Create a CRACO configuration file in your project's root directory and configure:
    
      my-app
      ├── node\_modules
    + ├── craco.config.js
      └── package.json
    
3.  Update the existing calls to `react-scripts` in the `scripts` section of your `package.json` to use the `craco` CLI:
    
    "scripts": {
    \-  "start": "react-scripts start"
    +  "start": "craco start"
    \-  "build": "react-scripts build"
    +  "build": "craco build"
    \-  "test": "react-scripts test"
    +  "test": "craco test"
    }
    

Visit craco.js.org to learn more.
