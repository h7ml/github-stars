---
project: partytown
stars: 13445
description: Relocate resource intensive third-party scripts off of the main thread and into a web worker. 🎉
url: https://github.com/QwikDev/partytown
---

Partytown 🎉
============

-   Introducing Partytown: Run Third-Party Scripts From a Web Worker
-   How Partytown's Sync Communication Works
-   How we cut 99% of our JavaScript with Qwik + Partytown
-   Partytown is now in Beta

> A fun location for your third-party scripts to hang out

Partytown is a lazy-loaded library to help relocate resource intensive scripts into a web worker, and off of the main thread. Its goal is to help speed up sites by dedicating the main thread to your code, and offloading third-party scripts to a web worker.

> Note: Partytown is still in beta and not guaranteed to work in every scenario. Please see our FAQ and Trade-Off sections for more info.

The philosophy is that the main thread should be dedicated to your code, and any scripts that are not required to be in the critical path should be moved to a web worker. Main thread performance is, without question, more important than web worker thread performance.

-   Getting Started
-   Integrations
-   Configuration
-   Releases
-   FAQs

Community
---------

-   @QwikDev
-   @Builderio
-   Local Development
-   For Plugin Authors / Developers

Related Projects
----------------

-   Qwik: An open-source framework designed for best possible time to interactive, by focusing on resumability of server-side-rendering of HTML, and fine-grained lazy-loading of code.
-   Mitosis: Write components once, run everywhere. Compiles to Vue, React, Solid, Angular, Svelte, and more.
-   Builder: Drag and drop page builder and CMS for React, Vue, Angular, and more.
