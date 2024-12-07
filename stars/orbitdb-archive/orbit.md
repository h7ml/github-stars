---
project: orbit
stars: 1638
description: A distributed, serverless, peer-to-peer chat application on IPFS
url: https://github.com/orbitdb-archive/orbit
---

Orbit
=====

> A distributed, serverless, peer-to-peer chat application on IPFS.

If you're here, you're probably looking for:

-   **orbit-db** - The decentralized databases project
-   **orbit-web** - The current repository behind Orbit Chat, a p2p chat running on orbitdb.

No work is currently being done in this repository.

#### Try the web app at https://orbit.chat

**NOTE!** _Orbit is still more or less experimental. It means Orbit is currently **not secure**, APIs will change and clients can break over time. If you come across problems, it would help greatly to open issues so that we can fix them as quickly as possible._

Clients
-------

**Browsers**

Orbit chat application for the browsers.

https://github.com/orbitdb/orbit-web

**Desktops**

A desktop version of the Orbit chat application that can be run as a stand-alone app in OSX and Linux. _We're currently working on Windows support._

https://github.com/orbitdb/orbit-electron

**Terminal**

A prototype of a terminal client.

https://github.com/orbitdb/orbit-textui

Core Library
------------

### orbit-core

Orbit is intended to be embeddable in applications. `orbit-core` is a JavaScript implementation which can be used in Node.js, Browser and Electron applications and on websites.

orbit-core

### orbit-db

A serverless, p2p database built on IPFS. Orbit uses `orbit-db` to have a database for each channel in the chat network.

orbit-db

### js-ipfs

A new peer-to-peer hypermedia protocol. Orbit uses IPFS as its data storage and libp2p to handle all the p2p networking.

-   js-ipfs - IPFS JavaScript implementation
-   go-ipfs - IPFS Go implementation
-   https://github.com/ipfs/ipfs - IPFS on Github
-   https://ipfs.io - IPFS Website

Contributing
------------

We would be happy to accept PRs! If you want to work on something, it'd be good to talk beforehand to make sure nobody else is working on it. You can reach us on on Gitter, or in the comments of the issues section. At the moment, progress in this particular repo is on hold. PRs are unlikely to be merged, and the issues are a bit stale.

We also have **regular community calls**, which we announce in the issues in the @orbitdb welcome repository. Join us!

For specific guidelines for contributing to this repository, check out the Contributing guide. For more on contributing to OrbitDB in general, take a look at the @OrbitDB welcome repository. Please note that all interactions in @OrbitDB fall under our Code of Conduct.

License
-------

MIT © 2015-2018 Protocol Labs Inc., 2018-2019 Haja Networks Oy
