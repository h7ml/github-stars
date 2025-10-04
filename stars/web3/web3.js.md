---
project: web3.js
stars: 19895
description: Collection of comprehensive TypeScript libraries for Interaction with the Ethereum JSON RPC API and utility functions.
url: https://github.com/web3/web3.js
---

Web3.js
=======

### Web3.js libraries are being sunset on March 4th, 2025. For migration guides and more details please refer to Chainsafe blog

Web3.js is a TypeScript implementation of the Ethereum JSON RPC API and related tooling maintained by ChainSafe Systems.

Installation
------------

You can install the package either using NPM or using Yarn

> If you wanna checkout latest bugfix or feature, use `npm install web3@dev`

### Using NPM

npm install web3

### Using Yarn

yarn add web3

Getting Started
---------------

-   ✍️ If you have questions submit an issue or join us on Discord

Prerequisites
-------------

-   ⚙️ NodeJS (LTS/Fermium)
-   🧰 Yarn/Lerna

Migration Guide
---------------

-   Migration Guide from Web3.js 1.x to 4.x Breaking changes are listed in migration guide and its first step for migrating from Web3.js 1.x to 4.x. If there is any question or discussion feel free to ask in Discord, and in case of any bug or new feature request open issue or create a pull request for contributions.

Useful links
------------

-   Web3 tree shaking support guide
-   React App Example

Architecture Overview
---------------------

Package

Version

License

Docs

Description

web3

🚨 Entire Web3.js offering (includes all packages)

web3-core

Core functions for web3.js packages

web3-errors

Errors Objects

web3-eth

Modules to interact with the Ethereum blockchain and smart contracts

web3-eth-abi

Functions for encoding and decoding EVM in/output

web3-eth-accounts

Functions for managing Ethereum accounts and signing

web3-eth-contract

The contract package contained in web3-eth

web3-eth-ens

Functions for interacting with the Ethereum Name Service

web3-eth-iban

Functionality for converting Ethereum addressed to IBAN addressed and vice versa

web3-eth-personal

Module to interact with the Ethereum blockchain accounts stored in the node

web3-net

Functions to interact with an Ethereum node's network properties

web3-providers-http

Web3.js provider for the HTTP protocol

web3-providers-ipc

Web3.js provider for IPC

web3-providers-ws

Web3.js provider for the Websocket protocol

web3-rpc-methods

RPC Methods

web3-types

Shared useable types

web3-utils

Useful utility functions for Dapp developers

web3-validator

Utilities for validating objects

Package.json Scripts
--------------------

Script

Description

clean

Uses `rimraf` to remove `dist/`

build

Uses `tsc` to build all packages

lint

Uses `eslint` to lint all packages

lint:fix

Uses `eslint` to check and fix any warnings

format

Uses `prettier` to format the code

test

Uses `jest` to run unit tests in each package

test:integration

Uses `jest` to run tests under `/test/integration` in each package

test:unit

Uses `jest` to run tests under `/test/unit` in each package

test:manual:long-connection-ws

Runs manual tests for keeping a long WebSocket connection

test:manual

Runs manual tests under `test/manual` in the web3 package
