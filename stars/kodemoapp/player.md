---
project: player
stars: 678
description: A React component for reading Kodemo documents.
url: https://github.com/kodemoapp/player
---

Kodemo
======

Kodemo is a new format for more engaging and interactive technical documentation. It's great for tutorials and walkthroughs.

-   🔗 Learn more at kodemo.com
-   👉 Try a live demo
-   👀 Follow @kodemoapp

Kodemo Player
-------------

This repo contains the @kodemo/player package which is responsible for rendering and navigating Kodemo documents. The player is a React component and it needs to be provided with a valid Kodemo document.

### Installation

To install and integrate @kodemo/player please follow the docs at https://kodemo.com/docs/player.

TLDR?

1.  Install @kodemo/player using your package manager of choice:

npm i @kodemo/player # yarn add @kodemo/player

1.  Import and render the `KodemoPlayer` component:

import React from 'react'
import ReactDOM from 'react-dom/client'
import { KodemoPlayer } from '@kodemo/player';

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode\>
    <KodemoPlayer json\={{
      story: '<h1>Example Document</h1>',
      subjects: {
        f992151a: {
          type: 'code',
          name: 'file.js',
          language: "javascript",
          versions: {
            e60944c4: { value: 'const a = 123;', },
          }
        }
      }
    }}\></KodemoPlayer\>
  </React.StrictMode\>
)

### Development Setup

If you want to make changes to the @kodemo/player source here's how:

1.  Clone this repository
2.  Run `yarn install`
3.  Run `yarn dev` to start the development server
4.  Open the URL from the dev server output and 💥

#### Other scripts

# run tests
yarn test

# build a new release
yarn build

### Adding New Subject Types

Each subject in Kodemo is its own React component. You can easily add your own subject types by following these steps:

1.  Create your subject component in the subjects directory. I recommend using AbstractSubject as a starting point.
2.  Export your subject from subjects/index.ts.
3.  Add your subject to enum/SubjectType.ts.

### Terminology

If you're planning to work with the Kodemo source here are a few key concepts and names that are good to know about.

-   The `story` is the main body text of the documentation.
-   `Subjects` are the individual pieces of content that the documentation covers. A subject can be an image, code, etc.
-   Subjects can have multiple `versions`. Each version represents a variant of the same subject. For example, multiple versions are used to animate lines being added or removed from code.
-   The `timeline` is the bar with vertical line segments that indicate which subject that will become active when scrolling.
-   `Effects` are keywords within the story that are linked to a specific subject version. They form the relationship between the story and subjects.

* * *

MIT licensed | Copyright © 2022-2023 Hakim El Hattab, https://hakim.se
