---
project: covalent
stars: 2229
description: Teradata UI Platform built on Angular Material
url: https://github.com/Teradata/covalent
---

Covalent Design System
----------------------

Covalent is Teradata's design system used to create Teradata branded experiences. This space is intended to be used to support developers creating coded experiences for Teradata products. Currently we are only supporting angular and a library of web components.

**Vision: To build an atomic, reusable component platform for Teradata to consume, while collaborating in an open source model.**

Setup
-----

-   Ensure you have Node 18.12.0+
-   Install Node packages `npm ci`
-   Run local build `npm run start`

* * *

-   Getting Started
-   Web Components
-   Contributing Guidelines
-   Developer Guide
-   Upgrading
-   Releasing
-   Changelog
-   StackBlitz Template
-   Plunker Template

* * *

Angular Support
---------------

Certain covalent version are meant for certain angular versions, and here is the matrix:

Covalent

Angular

2.X

8.X

3.X

9.X / 10.X / 11.x

4.X

12.X / 13.X

5.X

14.X

6.X

15.X

7.X

16.X

8.X

17.X

Browser Support
---------------

Covalent is built on a CSS Flexbox layout and all layouts and components heavily rely up that support, so the current browsers are supported in order or recommendation:

#### Current version - 1 for the following:

Chrome

Firefox

Safari

Edge

Mobile Chrome

Mobile Safari

**Supported**

✓

✓

✓

✓

~

~

~ Indicates limited testing & lower priority

Running Chromatic
-----------------

`npx chromatic --project-token=${CHROMATIC_PROJECT_TOKEN}`
