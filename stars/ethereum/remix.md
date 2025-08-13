---
project: remix
stars: 1179
description: This has been moved to https://github.com/ethereum/remix-project
url: https://github.com/ethereum/remix
---

**The project has been moved to https://github.com/ethereum/remix-project**

**Remix** is a suite of tools that helps smart contract development, compilation, testing & deployment. These tools also works as a core of native plugins of Remix IDE.

**Remix IDE** is an IDE for Solidity dApp developers, powered by Remix. The Remix IDE repository is available **here**, and an online version is available at https://remix.ethereum.org.

For more, check out the Remix IDE documentation.

Remix Modules
-------------

Remix is built out of several different modules. Here is the brief description.

-   `remix-analyzer`: Perform static analysis on Solidity smart contracts to check security vulnerabilities and bad development practices
-   `remix-astwalker`: Parse solidity AST (Abstract Syntax Tree)
-   `remix-debug`: Debug Ethereum transactions. It provides several controls that allow stepping over the trace and seeing the current state of a selected step.
-   `remix-solidity`: Load a Solidity compiler from provided URL and compile the contract using loaded compiler and return the compilation details
-   `remix-lib`: Common place for libraries being used across multiple modules
-   `remix-tests`: Unit test Solidity smart contracts. It works as a plugin & as CLI both
-   `remix-url-resolver`: Provide helpers for resolving the content from external URL ( including github, swarm, ipfs etc.).
-   `remixd`: Allow accessing local filesystem from Remix IDE by running a daemon

Each module generally has their own npm package and test suite, as well as basic documentation in their respective `README`s. Usage of modules as plugin is well documented **here**.

Contributing
------------

Everyone is very welcome to contribute on the codebase of Remix. Please reach us in Gitter in case of any query/feedback/suggestion.

For more information on the contributing procedure, see CONTRIBUTING.md.
