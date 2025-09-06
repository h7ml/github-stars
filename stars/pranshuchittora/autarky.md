---
project: autarky
stars: 365
description: Liberating disk space from 📁 node_modules | Built with React
url: https://github.com/pranshuchittora/autarky
---

  

Installation
------------

# npm
npm i -g autarky

#yarn
yarn global add autarky

Usage
-----

$\> autarky

Why autarky
-----------

In today's world storage is comparatively costlier than compute. Majority of devs uses MacBooks and sadly MacBooks have pretty low storage (for base models). Hence filling up storage is quite often and we spend a lot of time picking stuff to be deleted.

### Motivation

It's 2019 and I got ran out of storage in my laptop after a thorough analysis I found out that the majority of the storage is occupied by `node_modules`. As each project have a separate node\_modules (duplication despite the same version).

I also have a few projects which I touch once in a blue moon, hence they end up eating a lot of space. On the other hand, picking & removing `node_modules` manually is a tedious process. So I thought why not automate it.

### How it works

Autarky works by traversing all the child directories recursively relative to the current working directory (the place where you are executing autarky).

1.  Enter the time in months. Node modules older than the given time will be shown.
2.  Select the `node_modules` which you want to delete.
3.  Confirm deletion.
4.  Done! (No need to pay for more storage.)

* * *

Internals
---------

Autarky is built with the latest open source technologies.

1.  UI - The user interface is written in React. Using the Ink's reconciler for rendering the react components.
2.  State Management - The challenge of sharing data b/w UI and the process is achieved using Redux.
3.  Heavy Computation - Large data crunching is done on child processes.

### Building Blocks

-   React
-   Redux
-   Ink
-   moment
-   rimraf
-   chalk

* * *

Read CONTRIBUTING Guide

License MIT

Author: Pranshu Chittora

Github Twitter LinkedIn
