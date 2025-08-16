---
project: react-babylonjs
stars: 871
description: React for Babylon 3D engine
url: https://github.com/brianzinn/react-babylonjs
---

react-babylonjs
===============

> _'react-babylonjs'_ integrates the Babylon.js real time 3D engine with React

`react-babylonjs` lets you build your scene and components using a familiar declarative syntax with the benefits of reusable components and hooks. The Babylon.js API is mostly covered declaratively thanks to code generation and even custom props allow you to declaratively add shadows, physics, 3D models, attach 2D/3D UI to meshes, etc.

**NOTE:** for the time being React 19 works with newest and @latest versions. For older React versions, you will need to use 3.2.2 (ie: `yarn add react-babylonjs@3.2.2`). Hope next version will support both. I tried to stay away from a major bump due to the ephemeral nature of this change. Thanks for your patience.

Fully supports hooks. Full support for TypeScript with auto-completion on elements and compile time checks. Context API and hooks provide easy access to Scene/Engine/Canvas.

_No third party dependencies outside of React + babylon.js_

https://brianzinn.github.io/react-babylonjs/

Examples
--------

~50 sample web pages with viewable source code on: github pages examples.

Example Projects
----------------

-   Create React App (JavaScript) CRA JavaScript implementation. Github pages has live examples of typical and declarative usage some with Redux.
-   Create React App (TypeScript) CRA 3 TypeScript. Examples of physics, shadows, etc.

React Native
------------

No online examples for native, but you can integrate using `EngineCanvasContext.Provider`:

import React, { useState } from 'react';
import { View } from 'react-native';

import { EngineView, useEngine } from '@babylonjs/react-native';
import { Camera } from '@babylonjs/core';
import { EngineCanvasContext, Scene } from 'react-babylonjs';

const EngineScreen: FunctionComponent<ViewProps\> = (props: ViewProps) =\> {

  const engine \= useEngine();
  const \[camera, setCamera\] \= useState<Camera\>();

  return (
    <View style\={props.style}\>
      <EngineCanvasContext.Provider value\={{ engine, canvas: null }}\>
        {engine &&
          <Scene\>
            <arcRotateCamera
              name\="camera1"
              onCreated\={camera \=> setCamera(camera)}
            />
            <hemisphericLight name\="light1" />
            { /\* rest of declarative scene/components here \*/ }
          </Scene\>
        }
      </EngineCanvasContext.Provider\>
      <EngineView camera\={camera} displayFrameRate\={true} />
    </View\>
  );
};

Contributors
------------

-   Huge shout out to Konsumer that helped bring this project to the next level. The ideas and code sandboxes from issue #6 inspired the code generation and HOC + Context API integration.
-   seacloud9 for adding storybook, GSAP demo, dynamic terrain (extension) & PIXI demo.
-   hookex has made the largest contribution 😃 Proper texture handling demo, Node parenting, demo Full Screen GUI demo, Effect Layers glow demo, behaviors demo, useHover & useClick hooks demo and react-spring integration as author of `react-babylon-spring` - https://github.com/hookex/react-babylon-spring.
-   dennemark add support for `CascadedShadowGenerator`, `createPortal` and `Html` (project HTML in scene - ported from `drei`). Also, stories for Snippet Material and "tunnel" zustand integration. Added `RenderOnDemand` to customize render loops.
-   kencyke created a cool multi-canvas + cloud point repo that insipired creation of `<pointsCloudSystem .../>` as host element.
-   flostellbrink fixed the `react-babylon-spring` integration and added GH action for Storybook (github pages)
-   voronp add `isPaused` Engine prop to skip rendering
-   saidmoya12 add camera before/after render hooks
-   Viktor Zhurbin rebuilt single handedly a much improved GH pages website using rspress. Including a complete rewrite of how inline code samples are displayed, so you can view fullscreen, multiple files and toggle between code/preview/split and a much better search and mobile experience. Also, the amazing Playground was added including saved and sharable snippets/forking!
-   Baris Ozcetin add React 19 support

> Thanks also to all the people who have contributed with issues/questions/discussions. All the great ideas and requests are why this project evolved beyond an experiment.

Made with ♥
