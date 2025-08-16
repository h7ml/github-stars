---
project: fuels-ts
stars: 43625
description: Fuel Network Typescript SDK
url: https://github.com/FuelLabs/fuels-ts
---

fuels-ts
========

Typescript SDK for Fuel.

Install (docs)
==============

npm install fuels --save

Connect (docs)
==============

Network

URL

Mainnet

`https://mainnet.fuel.network/v1/graphql`

Testnet

`https://testnet.fuel.network/v1/graphql`

Localhost

Running a local Fuel node

import { Provider } from 'fuels';

const NETWORK\_URL \= 'https://mainnet.fuel.network/v1/graphql';

const provider \= new Provider(NETWORK\_URL);

const chainId \= await provider.getChainId();
const gasConfig \= await provider.getGasConfig();
const baseAssetId \= await provider.getBaseAssetId();

console.log({ chainId, gasConfig, baseAssetId });

Create a new dApp (docs)
========================

$ npm create fuels

◇ What is the name of your project? #
│ my-fuel-project
└

⚡️ Success! Created a fullstack Fuel dapp at: my-fuel-project.

Enjoy the `fuels` CLI (docs)
============================

$ npm install fuels --save
$ npm fuels --help

Commands:
  init \[options\]      Create a sample \`fuel.config.ts\` file
  build \[options\]     Build Sway programs and generate Typescript for them
  deploy \[options\]    Deploy contracts to the Fuel network
  dev \[options\]       Start a Fuel node with hot-reload capabilities
  node \[options\]      Start a Fuel node using project configs
  typegen \[options\]   Generate Typescript from Sway ABI JSON files
  versions \[options\]  Check for version incompatibilities
  help \[command\]      Display help for command

In-depth docs:

-   `fuels init` — Creates a new `fuels.config.ts` file
-   `fuels build` — Build `forc` workspace and generate Typescript types for everything
-   `fuels deploy` — Deploy workspace contracts and save their IDs to JSON file
-   `fuels dev` — Start a Fuel node with hot-reload capabilities

Official Docs
=============

-   Install The Fuel Toolchain — https://docs.fuel.network/guides/installation/

* * *

-   Typescript SDK — https://docs.fuel.network/docs/fuels-ts
-   Fuel Wallet SDK — https://docs.fuel.network/docs/wallet
-   Rust SDK — https://docs.fuel.network/docs/fuels-rs
-   GraphQL Playground — https://docs.fuel.network/docs/graphql

* * *

-   Forc — https://docs.fuel.network/docs/forc
-   Sway — https://docs.fuel.network/docs/sway
-   Fuel Core — https://github.com/FuelLabs/fuel-core
-   Fuel VM — https://docs.fuel.network/docs/specs/fuel-vm
-   Fuel Specs — https://docs.fuel.network/docs/specs

Apps & Ecosystem
================

-   Fuel Bridge — https://app.fuel.network/bridge
-   Block Explorer — https://app.fuel.network
-   Ecosystem Apps — https://app.fuel.network/ecosystem

Get in Touch
============

-   `Forum` — https://forum.fuel.network
-   `Discord` — https://discord.gg/xfpK4Pe

Contribute
==========

-   ./CONTRIBUTING.md

License
=======

The primary license for this repo is `Apache 2.0`, see `LICENSE`.
