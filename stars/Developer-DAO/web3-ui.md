---
project: web3-ui
stars: 782
description: A React UI library for Web3
url: https://github.com/Developer-DAO/web3-ui
---

web3-ui
=======

_In Development - Refactoring in Progress 🏗️_

A library of UI components specifically crafted for web3 use cases.

Package name

Current version

(Deprecated) `@web3-ui/core`

`@web3-ui/components`

(Deprecated) `@web3-ui/hooks`

Quick start
-----------

### Note: This is for the current public release. This library is being refactored and instructions will change.

1.  Install the package

$ yarn add @web3-ui/core ethers

1.  Setup the Provider

import { Provider, NETWORKS } from '@web3-ui/core';

function MyApp({ Component, pageProps }) {
  return (
    <Provider network\={NETWORKS.mainnet}\>
      <Component {...pageProps} />
    </Provider\>
  );
}

1.  Use the components and hooks

import { ConnectWallet, useWallet } from '@web3-ui/core';

function Home() {
  const { connection } \= useWallet();

  return (
    <div\>
      <ConnectWallet />
      <div\>{connection.ens || connection.userAddress}</div\>
    </div\>
  );
}

Roadmap
-------

Please see the Roadmap for more details

How to Contribute
-----------------

Read the CONTRIBUTING GUIDELINES.

The motive behind this package
------------------------------

-   RFC: web3-ui (a web3-specific UI library)

Contributors ✨
--------------

Thanks goes to these wonderful people (emoji key):

  
**Erik Ritter**  
💻 👀

  
**Camila Rondinini**  
💻 👀

  
**Dhaiwat Pandya**  
💻 👀

  
**Nazeeh Vahora**  
💻 📖

  
**Jose L. Velez**  
📖 💻

  
**with-heart**  
👀 💻

  
**Christian**  
💻

  
**Alex**  
💻

  
**Sam Wellander**  
📖

  
**Todor Tsankov**  
💻

  
**Jovi De Croock**  
💻

  
**Bonhomme**  
💻

  
**hone1er**  
💻

  
**Emanuel López**  
💻

  
**Greg Syme**  
💻

  
**Casuneanu Catalin**  
💻

  
**Jake Warren**  
💻

  
**Carlo Miguel Dy**  
💻 📖

  
**Akshata Mohanty**  
📖

  
**Ibby E**  
💻

  
**Sweta Shaw**  
💻

  
**Snehit Paunikar**  
📖

  
**Nathan Ng**  
💻

  
**manny**  
💻

  
**fangjun**  
📖

  
**Julian Krispel-Samsel**  
📖

  
**Ikko Ashimine**  
📖

  
**Leonardo Berteotti**  
💻

  
**Patrick Aljord**  
💻

  
**Shamoil Arsiwala**  
💻

  
**Ernesto García**  
💻

  
**David**  
💻

  
**Eric Roupe**  
💻

  
**Ricardo Seromenho**  
💻

  
**James Charlesworth**  
💻

  
**Diego Alzate**  
💻

  
**Andrii Shupta**  
💻

  
**meowy**  
💻

  
**Rémi Roycourt**  
💻

  
**Ajinkya Shinde**  
💻

This project follows the all-contributors specification. Contributions of any kind welcome!

Special thanks
--------------

This project would not have been possible without these wonderful projects:

-   ethers
-   scaffold-eth
-   Chakra UI
-   web3modal
-   useDApp
-   wagmi
-   Storybook
-   Preconstruct
