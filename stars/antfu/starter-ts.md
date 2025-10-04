---
project: starter-ts
stars: 842
description: Starter template for TypeScript library
url: https://github.com/antfu/starter-ts
---

pkg-placeholder
===============

_description_

Note for Developers
-------------------

This starter recommands using npm Trusted Publisher, where the release is done on CI to ensure the security of the packages.

To do so, you need to run `pnpm publish` manually for the very first time to create the package on npm, and then go to `https://www.npmjs.com/package/<your-package-name>/access` to set the connection to your GitHub repo.

Then for the future releases, you can run `pnpm run release` to do the release and the GitHub Actions will take care of the release process.

Sponsors
--------

License
-------

MIT License © Anthony Fu
