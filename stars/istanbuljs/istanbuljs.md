---
project: istanbuljs
stars: 1074
description: monorepo containing the various nuts and bolts that facilitate istanbul.js test instrumentation
url: https://github.com/istanbuljs/istanbuljs
---

IstanbulJS
==========

_Having problems? want to contribute? join our community slack_.

> Everyone's favorite JS code coverage tool.

About this Repo
---------------

This monorepo contains the _nuts and bolts_ utility libraries that facilitate IstanbulJS test coverage; Why a monorepo?

-   it allows us to more easily test API changes across coupled modules, e.g., changes to `istanbul-lib-coverage` potentially have an effect on `istanbul-lib-instrument`.
-   it gives us a centralized repo for discussions about bugs and upcoming features.

Where Should I Start
--------------------

_You're probably actually looking for one of the following repos:_

-   nyc: the IstanbulJS 2.0 command line interface, providing painless coverage support for most popular testing frameworks.
-   babel-plugin-istanbul: a babel plugin for instrumenting your ES2015+ code with Istanbul compatible coverage tracking.
-   istanbul: the legacy 1.0 IstanbulJS interface (you should now consider instead using nyc or babel-plugin-istanbul).

### Contributing

Contributing to the packages contained in this repo is easy:

1.  after checking out, run `npm install` (this will run the lerna build).
2.  to run all tests, simply run `npm test` in the root directory.
3.  to run tests for a single package `cd package/:name` and run `npm test` within the package's folder.
