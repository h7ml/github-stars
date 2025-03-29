---
project: deskreen
stars: 18308
description: Deskreen turns any device with a web browser into a secondary screen for your computer. ⭐️ Star to support our work!
url: https://github.com/pavlobu/deskreen
---

Deskreen
========

### Website: https://deskreen.com

* * *

DESKREEN CREATOR IS A UKRAINIAN. 🇺🇦 UKRAINE 🇺🇦 NEEDS YOUR HELP ❗️❗️❗️
=========================================================================

♥️ CLICK HERE TO DONATE TO UKRAINE! ♥️
--------------------------------------

If you don't live in a cave and aware of what is going on in the world 🌍 , Russian 🇷🇺 government had started global armed invasion on the territory of Ukraine on the 24th of February 2022. **_This is for real, this is a WAR. Russian army is killing Ukrainian soldiers, Ukrainian civil citizens and Ukrainian children RIGHT NOW because Russian government gave them an order to do so._** You can search online for thousands of videos of what is going on in Ukraine.

Ukrainians fight brave for their land and will never give up. But you must understand that our country is fighting here not for our land only, but for the safety of the whole world. ❗️❗️❗️ **_If Ukraine fails in this war with Russian army and Russian government, the security of all countries in the world 🌍 will be under the threat! Russian government and it's vicious allies and governments from other countries will be moving their armies to YOUR land, sooner or later_** ❗️❗️❗

You must understand that now Ukraine has more people here willing to fight than weapons, military supplies and other inventory for them.

**If you CAN and WANT to support Ukraine 🇺🇦 and Ukrainian army, here is a tweet with instructions from OFFICIAL ✅ account of Ukraine 🇺🇦**

♥️ CLICK HERE TO GO TO A TWEET TO DONATE TO UKRAINE! ♥️
-------------------------------------------------------

GLORY TO 🇺🇦 UKRAINE 🇺🇦, GLORY TO UKRAINIAN HEROES! 🇺🇦🇺🇦🇺🇦
===================================================================

* * *

### ▶️ Deskreen Youtube channel (video tutorials, demos, use cases for Deskreen day to day usage)

Deskreen turns any device with a web browser into a secondary screen for your computer
--------------------------------------------------------------------------------------

Deskreen is an `electron.js` based application that uses `WebRTC` to make a live stream of your desktop to a web browser on any device. It is built on top of Electron React Boilerplate For better security mechanism, end-to-end encryption is implemented, which is inspired by darkwire.io. The difference is that it is rewritten in `Typescript` and transformed to use `node-forge` instead of `window.crypto.subtle`. Why this was made? Because a client served with `http` without SSL, which makes `window.crypto.subtle` unavailable.

  

Deskreen FAQ
------------

  

Get Started for translators
---------------------------

Want to add a new language support for Deskreen? Or you found a typo in existing translations of Deskreen App or website? Here are step by step guides:

-   How to add a new language to Deskreen App and Website
-   How to fix a typo in Deskreen App or Website

  

Deskreen Github Discussion Threads
----------------------------------

Read and Respect our Contributor Covenant Code of Conduct When Writing in our Discussion Threads.

### Announcements Channel in Discussions

Some progress and updates on Deskreen can be found here.

* * *

-   Q&A General - for general questions about Deskreen.

* * *

-   Bugs General - for general bug reports if you don't know dev environment details. Please include Deskreen version! If you saw a bug and know your dev environment, and how to reproduce it, please consider opening a new Issue labeled as Bug and provide full details.

* * *

-   General Discussion - for general discussion. For example how did you find out about Deskreen? Or send cheers and thanks to anyone in Deskreen's community members. 🎉

* * *

-   Use Cases for Deskreen - let our community know how you use Deskreen in this thread.

* * *

-   Enhancements and New Features for Deskreen - share your ideas of what improvements can be done to Deskreen. Issues created with enhancement tag should be related to some concrete example of change in UI, Security patch, Performance improvement with some concrete notes on how you think the problem should be approached. Otherwise for general improvements with short paragraphs post your thoughts here.

* * *

-   Virtual Display Drivers Knowledge Base | Getting Rid From Virtual Display Plugs - share your knowledge or useful links on how to create a virtual display for any operating system. Links to source code are highly appreciated.

* * *

-   Cast Audio with Video when screen sharing using WebRTC in Electron | Drivers to pipe audio output as an audio input source that can be read by ElectronJS WebRTC and streamed to client along with video - this feature has been requested multiple times, but it has a long way to go. Share your knowledge or useful links on how to get built in system audio output and put it to WebRTC stream so that client viewing device will be able to play it along with the video stream.

* * *

  
  

NOTE: We are looking for a solution to get rid from Dummy Display Plugs while using Deskreen as a second screen. Your code support is highly valuable and welcome in Deskreen!
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Display Dummy Plugs are good temporary solution, but it is not that good for everyone. If you are a seasoned Windows or Linux or MacOS hacker with a knowledge of low level tweaks and tricks, you can help us to make Deskreen better! On a long run Deskreen seeks for getting rid of Display Dummy Plugs, because most people don't like using them. Sometimes they can't use them because all available display ports are already taken. **So we need to have native drivers for Win / Mac / Linux that will help to enable virtual display without Dummy Display Plugs.** There are already working commercial solutions out there with their own drivers which they don't disclose, but this task is doable with a help of entire community. The goal of Deskreen is to enable community power and knowledge to overcome these technical challenges and make it a go-to second screen solution that everyone will benefit from!

We plan on making virtual display driver support for each of three main operating systems and place all OS related codes in **`./drivers`** subdirectory of this project. You can find brief requirements for driver API in **`./drivers/README.md`**.

Share your valuable knowledge on how to create virtual desktop **without a Dummy Display Plug in this discussion thread.**

Thank you in advance!

Installing with binaries
------------------------

### Windows

-   Get the .msi or .exe file from Releases

### Mac

-   Get the .dmg file from Releases
    
-   Or get from Homebrew: `brew install --cask deskreen`
    

### Linux

-   Debian and Ubuntu based distributions (deb)
    
-   Enterprise Linux based distributions (rpm)
    
-   Arch Linux AUR Package
    
-   AppImage for other distributions
    

Get Started for Developers
--------------------------

### Run `yarn test-all` locally to make sure you don't have any errors, before submitting your PR

### Prerequisites

You will need to have `node` `npm` and `yarn` installed globally on your machine.

1.  git clone this repo
2.  `cd app/client; yarn install --frozen-lockfile ; cd ../../ ; yarn install --frozen-lockfile`
3.  `yarn dev` -- run in dev mode with live updates

### Useful yarn commands

`yarn start` -- run in production mode to test, without packaging `yarn package` -- to package an app and make executables available in `release` folder

#### for more yarn commands look at `package.json`

### How to run tests

`yarn test` -- run all unit tests `yarn build-ux && yarn test-ux` -- run User Experience tests (no tests for `app/client` yet)

### TODO: add e2e tests with host + client app interaction

#### run tests of host app

`yarn test-watch-not-silent` -- run tests in watch mode with console logs only for host app, excluding `app/client` `yarn test -- -u` -- update snapshots

#### run tests for `app/client`

`yarn test` -- run client tests in watch mode `test:nowatch` -- run client tests a single time `yarn test -- -u` -- update snapshots

### Generate test coverage results

`yarn coverage` -- when run from project root, generates a coverage report for `host` and `app/client`

### How to regenerate snapshots if you have tests failing when running `yarn test`?

in root `./` folder of project run this:

```
yarn jest --updateSnapshot
```

in Deskreen Viewer `./app/client` folder of project run this:

```
cd app/client
SKIP_PREFLIGHT_CHECK=true yarn test:nowatch -- -u
```

### Run `yarn test-all` locally to make sure you don't have any errors, before submitting your PR

Instruction for running a local Sonar Qube, community edition
-------------------------------------------------------------

### Prerequisites

You need to install Sonar Qube community edition for your machine. And sonar-scanner. Then add sonar scanner to your PATH.

You need to run sonar-scanner separately on root directory and on `app/client` directory.

Luckily for you sonar scanner is automatically triggered after `husky` checks. So you only need to install and configure SonarCube locally and create two separate projects in SonarCube panel. First project for host app, and second project for client viewer app. TODO: add how to get started with local SonarCube for Deskreen in details.

Documentation
-------------

### High level architecture design

### WebRTC Screen Sharing Session Initiation Step by Step

### Benchmarks:

Benchmarks can be found here

Note on versioning:
-------------------

-   All versions git tags should start with `v` ex. `v1.0.0`
-   Before making a new release with `git push <version-tagname>` set version to `<version-tagname>` ! without `v` in the beginning! (ex. `1.0.0` -- not start with `v`) in these three files:
    -   `package.json` -- in `version` key ex. `1.0.0`
    -   `app/package.json` -- in `version` key ex. `1.0.0`
    -   `app/package-lock.json` -- in `version` key ex. `1.0.0`
    -   `app/client/package.json` -- in `version` key ex. `1.0.0`

Found typo on https://deskreen.com ?
------------------------------------

You can submit your pull request with fix on Deskreen website locales repo

Maintainer
----------

-   Pavlo (Paul) Buidenkov

License
-------

AGPL-3.0 License © Pavlo (Paul) Buidenkov

Copyright
---------

Deskreen Logo PNG Image -- © Nadiia Plaunova

Apache 2.0 © blueprintjs

MIT © Electron React Boilerplate

simple-peer MIT. Copyright (c) Feross Aboukhadijeh

GNU General Public License (GPL) Version 2 node-forge

ISC Copyright (c) 2019, Mapbox pixelmatch

Thanks
------

🙏 Special thanks to Electron React Boilerplate community for providing a good kickstart template boilerplate code for electron project, that really helped a lot to get started with development of Deskreen.

🙏 Thanks to Github workflows for enabling a robust CI pipeline for the needs of 'forging' 🛠️ Deskreen.

🙏 Many thanks to all 🌍 open source community members and maintainers of libraries used in this project.

Donate
------

Click to donate on Deskreen's Patreon page

Click to donate on Deskreen's Opencollective page
