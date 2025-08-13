---
project: bitflow
stars: 44
description: Bitflow a library for creating and conducting dynamic flow-based assessments.
url: https://github.com/openpatch/bitflow
---

Bitflow
=======

Bitflow is a library for building flow-based assessment systems. Feel free to check out the examples to get started.

-   **Website:** https://bitflow.openpatch.org
-   **Documentation:** https://bitflow.openpatch.org/docs
-   **Website/Docs Repository:** https://github.com/openpatch/bitflow
-   **Community:** https://matrix.to/#/#openpatch:matrix.org

Development
-----------

Before you start you need to install the Biflow dependencies and set up the monorepo via `pnpm install`.

If you want to contribute or develop custom features the easiest way is to start the documentation and the dev mode:

```
pnpm dev
pnpm website:dev
```

You can use plop templates for creating new packages:

```
pnpm plop
```

Testing
-------

Testing is done with jest. You can find the tests in each package in the `tests` folder. In order to run the tests for all packages do:

```
pnpm test
```

For running tests on an individual package run:

```
pnpm --filter @bitflow/core test
```

Documentation
-------------

If you want to work on the documentation, run the development server.

```
pnpm dev
pnpm website:dev
```

Maintainer
----------

Mike Barkmin • Twitter • GitHub

Support
-------

We are happy to hear from you, if you need custom support or features for your application.

* * *

Bitflow is maintained by OpenPatch, an organization for educational assessments. If you need help or want to develop Bitflow tools or educational assessments get in touch.

Thanks!
-------

Special thanks to the University of Duisburg-Essen and the Chair of Computer Science Education for supporting the development of this library.

Another huge shoutout to webkid for developing and maintaining React Flow. This library is the core of Bitflow.

We also like to thank Vercel for hosting our documentation.
