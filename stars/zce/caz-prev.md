---
project: caz-prev
stars: 85
description: A simple yet powerful template-based Scaffolding tools.
url: https://github.com/zce/caz-prev
---

A simple yet powerful template-based Scaffolding tools for my personal productivity.

  

  

Introduction
------------

CAZ (**C**reate **A**pp **Z**en)

It's a a simple template-based Scaffolding tools for my personal productivity, inspired by Yeoman & Vue CLI 2 & etc.

-   pronounced: \[kæz\] 📷 ✌
-   written: CAZ / caz

_For more introduction, please refer to the How it works._

### Features

-   Easy to use
-   Light-weight
-   Still powerful
-   High efficiency
-   Less dependencies
-   Template-based
-   Configurable
-   Extensible
-   TypeScript
-   Use modern API

> I'll give you specific reasons later.

Table of Contents
-----------------

-   Introduction
    -   Features
-   Getting Started
    -   Prerequisites
    -   Installation
    -   Quick Start
-   Recipes
    -   GitHub Repo Templates
    -   Local Templates
    -   Remote ZIP Templates
    -   Offline Mode
    -   List Available Templates
    -   Official Templates
-   Advanced
    -   Create Your Template
    -   Configuration
    -   Create Your Scaffold
-   References
-   Motivation
-   About
    -   How It Works
    -   Built With
-   Roadmap
-   Contributing
-   License

Getting Started
---------------

### Prerequisites

-   Node.js (>= 10.12, 14.15 preferred)
-   npm (>= 6.x) or yarn (>= 1.20)
-   Git (>= 2.0)

### Installation

# install it globally
$ npm install -g caz

# or yarn
$ yarn global add caz

### Quick Start

Create new project from a template.

$ caz <template\> \[project\] \[-f|\--force\] \[-o|\--offline\]

# caz with an official template
$ caz <template\> \[project\]

# caz with a github repo
$ caz <owner\>/<repo\> \[project\]

If you only use it occasionally, I recommend that you use `npx` to run `caz` directly.

$ npx caz <template\> \[project\] \[-f|\--force\] \[-o|\--offline\]

#### Options

-   `-f, --force`: Overwrite if the target exists
-   `-o, --offline`: Try to use an offline template

Recipes
-------

### GitHub Repo Templates

$ caz nm my-project

The above command pulls the template from caz-templates/nm, then prompts for some information according to the configuration of this template, and generate the project at `./my-project`.

$ caz nm#typescript my-project

By running this command, CAZ will pulls the template from typescript branch of caz-templates/nm.

#### Use Custom templates

$ caz zce/nm my-project

The above command pulls the template from zce/nm. This means that you can also pull templates from your public GitHub repository.

**Public repository is necessary.**

### Local Templates

Instead of a GitHub repo, you can also use a template on your local file system.

e.g.

$ caz ~/local/template my-project

The above command use the template from `~/local/template`.

### Remote ZIP Templates

Instead of a GitHub repo, you can also use a template with a zip file uri.

e.g.

$ caz https://cdn.zce.me/boilerplate.zip my-project

The above command will download & extract template from `https://cdn.zce.me/boilerplate.zip`.

### Offline Mode

$ caz nm my-project --offline

By running this command, CAZ will try to find a cached version of `nm` template or download from GitHub if it's not yet cached.

### Prompts Override

CAZ allows you to specify prompt response answers through cli parameters.

$ caz minima my-project --name my-proj

### Debug Mode

$ caz nm my-project --debug

`--debug` parameter will open the debug mode, In debug mode, once an exception occurs, the exception details will be automatically output. This is very helpful in finding errors in the template.

### List Available Templates

Show all available templates

$ caz list \[owner\] \[-j|\--json\] \[-s|\--short\]

#### Arguments

-   `[owner]`: GitHub orgs or user slug, default: `'caz-templates'`

#### Options

-   `-j, --json`: Output with json format
-   `-s, --short`: Output with short format

### Official Templates

Current available templates list:

-   template - for creating caz templates.
-   nm - for creating node modules.
-   react - 🚧 for creating modern react app.
-   vue - for creating modern vue.js app.
-   vite - for creating vue.js app powered by vite.
-   electron - 🚧 for creating electron app.
-   jekyll - 🚧 for creating jekyll site.
-   mp - 🚧 for creating wechat mini-programs.
-   x-pages - for creating x-pages static site.

Maybe more: https://github.com/caz-templates

> You can also run `$ caz list` to see all available official templates in real time.

Advanced
--------

### Create Your Template

$ caz template my-template

The above command will pulls the template from caz-templates/template, and help you create your own CAZ template.

To create and distribute your own template, please refer to the How to create template.

> Maybe fork an official template is also a good decision.

### Configuration

CAZ will read the configuration file in `~/.cazrc`, default config:

; template download registry,
; {owner} & {name} & {branch} will eventually be replaced by the corresponding value.
registry = https://github.com/{owner}/{name}/archive/{branch}.zip
; template offlicial organization name
official = caz-templates
; default template branch name
branch = master

This means that you can customize the configuration by modifying the configuration file.

For example, in your `~/.cazrc`:

registry = https://gitlab.com/{owner}/{name}/archive/{branch}.zip
official = faker
branch = dev

Then run the following command:

$ caz nm my-project

The above command will download & extract template from `https://gitlab.com/faker/nm/archive/dev.zip`.

### Create Your Scaffold

# install it locally
$ npm install caz

# or yarn
$ yarn add caz

with ESM and async/await:

import caz from 'caz'

;(async () \=> {
  try {
    const template \= 'nm'
    // project path (relative cwd or full path)
    const project \= 'my-project'
    const options \= { force: false, offline: false }
    // scaffolding by caz...
    await caz(template, project, options)
    // success created my-project by nm template
  } catch (e) {
    // error handling
    console.error(e)
  }
})()

or with CommonJS and Promise:

const { default: caz } \= require('caz')

const template \= 'nm'
// project path (relative cwd or full path)
const project \= 'my-project'
const options \= { force: false, offline: false }
// scaffolding by caz...
caz(template, project, options)
  .then(() \=> {
    // success created my-project by nm template
  })
  .catch(e \=> {
    // error handling
    console.error(e)
  })

This means that you can develop your own scaffolding module based on it.

To create and distribute your own scaffolding tools, please refer to the How to create scaffolding tools based on CAZ.

References
----------

### caz(template, project?, options?)

Create new project from a template

#### template

-   Type: `string`
-   Details: template name

#### project

-   Type: `string`
-   Details: project name
-   Default: `'.'`

#### options

-   Type: `object`
-   Details: options & prompts override
-   Default: `{}`

##### force

Type: `boolean` Details: overwrite if the target exists Default: `false`

##### offline

Type: `boolean` Details: try to use an offline template Default: `false`

##### \[key: string\]

Type: `any` Details: cli options to override prompts

Motivation
----------

👉 🛠 ⚙

Joking: I want to make wheels ;P

The real reason is that I think I need a scaffolding tool that is more suitable for my personal productivity.

Nothing else.

About
-----

### How It Works

> P.S. The picture is from the Internet, but I have forgotten the specific source, sorry to the author.

#### Main Workflow

The core code is based on the middleware mechanism provided by zce/mwa.

The following middleware will be executed sequentially.

1.  confirm - Confirm destination by prompts.
2.  resolve - Resolve template from remote or local.
3.  load - Load template config by require.
4.  inquire - Inquire template prompts by prompts.
5.  setup - Apply template setup hook.
6.  prepare - Prepare all template files.
7.  rename - Rename file if necessary.
8.  render - Render file if template.
9.  emit - Emit files to destination.
10.  install - Execute `npm | yarn | pnpm install` command.
11.  init - Execute `git init && git add && git commit` command.
12.  complete - Apply template complete hook.

### Built With

-   adm-zip - A Javascript implementation of zip for nodejs. Allows user to create or extract zip files both in memory or to/from disk
-   cac - Simple yet powerful framework for building command-line apps.
-   env-paths - Get paths for storing things like data, config, cache, etc
-   fast-glob - It's a very fast and efficient glob library for Node.js
-   ini - An ini encoder/decoder for node
-   lodash - Lodash modular utilities.
-   node-fetch - A light-weight module that brings Fetch API to node.js
-   ora - Elegant terminal spinner
-   prompts - Lightweight, beautiful and user-friendly prompts
-   semver - The semantic version parser used by npm.
-   validate-npm-package-name - Give me a string and I'll tell you if it's a valid npm package name

Roadmap
-------

The following are the features I want to achieve or are under development:

-   config command
-   cache command
-   all lifecycle hooks
-   console output (colorful & verbose)
-   more and more official templates

See the open issues for a list of proposed features (and known issues).

Contributing
------------

1.  **Fork** it on GitHub!
2.  **Clone** the fork to your own machine.
3.  **Checkout** your feature branch: `git checkout -b my-awesome-feature`
4.  **Commit** your changes to your own branch: `git commit -am 'Add some feature'`
5.  **Push** your work back up to your fork: `git push -u origin my-awesome-feature`
6.  Submit a **Pull Request** so that we can review your changes.

> **NOTE**: Be sure to merge the latest from "upstream" before making a pull request!

License
-------

Distributed under the MIT License. See LICENSE for more information. © 汪磊
