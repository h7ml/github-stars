---
project: react-three-fiber
stars: 29699
description: 🇨🇭 A React renderer for Three.js
url: https://github.com/pmndrs/react-three-fiber
---

@react-three/fiber
==================

react-three-fiber is a React renderer for threejs.

Build your scene declaratively with re-usable, self-contained components that react to state, are readily interactive and can participate in React's ecosystem.

npm install three @types/three @react-three/fiber

Warning

Three-fiber is a React renderer, it must pair with a major version of React, just like react-dom, react-native, etc. @react-three/fiber@8 pairs with react@18, @react-three/fiber@9 pairs with react@19.

* * *

#### Does it have limitations?

None. Everything that works in Threejs will work here without exception.

#### Is it slower than plain Threejs?

No. There is no overhead. Components render outside of React. It outperforms Threejs in scale due to React's scheduling abilities.

#### Can it keep up with frequent feature updates to Threejs?

Yes. It merely expresses Threejs in JSX, `<mesh />` dynamically turns into `new THREE.Mesh()`. If a new Threejs version adds, removes or changes features, it will be available to you instantly without depending on updates to this library.

### What does it look like?

Let's make a re-usable component that has its own state, reacts to user-input and participates in the render-loop. (live demo).

import { createRoot } from 'react-dom/client'
import React, { useRef, useState } from 'react'
import { Canvas, useFrame } from '@react-three/fiber'

function Box(props) {
  // This reference gives us direct access to the THREE.Mesh object
  const ref \= useRef()
  // Hold state for hovered and clicked events
  const \[hovered, hover\] \= useState(false)
  const \[clicked, click\] \= useState(false)
  // Subscribe this component to the render-loop, rotate the mesh every frame
  useFrame((state, delta) \=> (ref.current.rotation.x += delta))
  // Return the view, these are regular Threejs elements expressed in JSX
  return (
    <mesh
      {...props}
      ref\={ref}
      scale\={clicked ? 1.5 : 1}
      onClick\={(event) \=> click(!clicked)}
      onPointerOver\={(event) \=> hover(true)}
      onPointerOut\={(event) \=> hover(false)}\>
      <boxGeometry args\={\[1, 1, 1\]} />
      <meshStandardMaterial color\={hovered ? 'hotpink' : 'orange'} />
    </mesh\>
  )
}

createRoot(document.getElementById('root')).render(
  <Canvas\>
    <ambientLight intensity\={Math.PI / 2} />
    <spotLight position\={\[10, 10, 10\]} angle\={0.15} penumbra\={1} decay\={0} intensity\={Math.PI} />
    <pointLight position\={\[\-10, \-10, \-10\]} decay\={0} intensity\={Math.PI} />
    <Box position\={\[\-1.2, 0, 0\]} />
    <Box position\={\[1.2, 0, 0\]} />
  </Canvas\>,
)

Show TypeScript example

npm install @types/three

import \* as THREE from 'three'
import { createRoot } from 'react-dom/client'
import React, { useRef, useState } from 'react'
import { Canvas, useFrame, ThreeElements } from '@react-three/fiber'

function Box(props: ThreeElements\['mesh'\]) {
  const ref \= useRef<THREE.Mesh\>(null!)
  const \[hovered, hover\] \= useState(false)
  const \[clicked, click\] \= useState(false)
  useFrame((state, delta) \=> (ref.current.rotation.x += delta))
  return (
    <mesh
      {...props}
      ref\={ref}
      scale\={clicked ? 1.5 : 1}
      onClick\={(event) \=> click(!clicked)}
      onPointerOver\={(event) \=> hover(true)}
      onPointerOut\={(event) \=> hover(false)}\>
      <boxGeometry args\={\[1, 1, 1\]} />
      <meshStandardMaterial color\={hovered ? 'hotpink' : 'orange'} />
    </mesh\>
  )
}

createRoot(document.getElementById('root') as HTMLElement).render(
  <Canvas\>
    <ambientLight intensity\={Math.PI / 2} />
    <spotLight position\={\[10, 10, 10\]} angle\={0.15} penumbra\={1} decay\={0} intensity\={Math.PI} />
    <pointLight position\={\[\-10, \-10, \-10\]} decay\={0} intensity\={Math.PI} />
    <Box position\={\[\-1.2, 0, 0\]} />
    <Box position\={\[1.2, 0, 0\]} />
  </Canvas\>,
)

Live demo: https://codesandbox.io/s/icy-tree-brnsm?file=/src/App.tsx

Show React Native example

This example relies on react 18 and uses `expo-cli`, but you can create a bare project with their template or with the `react-native` CLI.

# Install expo-cli, this will create our app
npm install expo-cli -g
# Create app and cd into it
expo init my-app
cd my-app
# Install dependencies
npm install three @react-three/fiber@beta react@rc
# Start
expo start

Some configuration may be required to tell the Metro bundler about your assets if you use `useLoader` or Drei abstractions like `useGLTF` and `useTexture`:

// metro.config.js
module.exports \= {
  resolver: {
    sourceExts: \['js', 'jsx', 'json', 'ts', 'tsx', 'cjs'\],
    assetExts: \['glb', 'png', 'jpg'\],
  },
}

import React, { useRef, useState } from 'react'
import { Canvas, useFrame } from '@react-three/fiber/native'
function Box(props) {
  const mesh \= useRef(null)
  const \[hovered, setHover\] \= useState(false)
  const \[active, setActive\] \= useState(false)
  useFrame((state, delta) \=> (mesh.current.rotation.x += delta))
  return (
    <mesh
      {...props}
      ref\={mesh}
      scale\={active ? 1.5 : 1}
      onClick\={(event) \=> setActive(!active)}
      onPointerOver\={(event) \=> setHover(true)}
      onPointerOut\={(event) \=> setHover(false)}\>
      <boxGeometry args\={\[1, 1, 1\]} />
      <meshStandardMaterial color\={hovered ? 'hotpink' : 'orange'} />
    </mesh\>
  )
}
export default function App() {
  return (
    <Canvas\>
      <ambientLight intensity\={Math.PI / 2} />
      <spotLight position\={\[10, 10, 10\]} angle\={0.15} penumbra\={1} decay\={0} intensity\={Math.PI} />
      <pointLight position\={\[\-10, \-10, \-10\]} decay\={0} intensity\={Math.PI} />
      <Box position\={\[\-1.2, 0, 0\]} />
      <Box position\={\[1.2, 0, 0\]} />
    </Canvas\>
  )
}

* * *

Documentation, tutorials, examples
==================================

Visit docs.pmnd.rs

First steps
===========

You need to be versed in both React and Threejs before rushing into this. If you are unsure about React consult the official React docs, especially the section about hooks. As for Threejs, make sure you at least glance over the following links:

1.  Make sure you have a basic grasp of Threejs. Keep that site open.
2.  When you know what a scene is, a camera, mesh, geometry, material, fork the demo above.
3.  Look up the JSX elements that you see (mesh, ambientLight, etc), _all_ threejs exports are native to three-fiber.
4.  Try changing some values, scroll through our API to see what the various settings and hooks do.

Some helpful material:

-   Threejs-docs and examples
-   Discover Threejs, especially the Tips and Tricks chapter for best practices
-   Bruno Simons Threejs Journey, arguably the best learning resource, now includes a full R3F chapter

Ecosystem
=========

There is a vibrant and extensive eco system around three-fiber, full of libraries, helpers and abstractions.

-   `@react-three/drei` – useful helpers, this is an eco system in itself
-   `@react-three/gltfjsx` – turns GLTFs into JSX components
-   `@react-three/postprocessing` – post-processing effects
-   `@react-three/uikit` – WebGL rendered UI components for three-fiber
-   `@react-three/test-renderer` – for unit tests in node
-   `@react-three/offscreen` – offscreen/worker canvas for react-three-fiber
-   `@react-three/flex` – flexbox for react-three-fiber
-   `@react-three/xr` – VR/AR controllers and events
-   `@react-three/csg` – constructive solid geometry
-   `@react-three/rapier` – 3D physics using Rapier
-   `@react-three/cannon` – 3D physics using Cannon
-   `@react-three/p2` – 2D physics using P2
-   `@react-three/a11y` – real a11y for your scene
-   `@react-three/gpu-pathtracer` – realistic path tracing
-   `create-r3f-app next` – nextjs starter
-   `lamina` – layer based shader materials
-   `zustand` – flux based state management
-   `jotai` – atoms based state management
-   `valtio` – proxy based state management
-   `react-spring` – a spring-physics-based animation library
-   `framer-motion-3d` – framer motion, a popular animation library
-   `use-gesture` – mouse/touch gestures
-   `leva` – create GUI controls in seconds
-   `maath` – a kitchen sink for math helpers
-   `miniplex` – ECS (entity management system)
-   `composer-suite` – composing shaders, particles, effects and game mechanics
-   `triplex` – visual editor for react-three-fiber
-   `koestlich` – UI component library for react-three-fiber

Usage Trend of the @react-three Family

Who is using Three-fiber
========================

A small selection of companies and projects relying on three-fiber.

-   `vercel` (design agency)
-   `basement` (design agency)
-   `studio freight` (design agency)
-   `14 islands` (design agency)
-   `ueno` (design agency) — video
-   `flux.ai` (PCB builder)
-   `colorful.app` (modeller)
-   `bezi` (modeller)
-   `readyplayer.me` (avatar configurator)
-   `zillow` (real estate)
-   `lumalabs.ai/genie` (AI models)
-   `skybox.blockadelabs` (AI envmaps)
-   `3dconfig` (floor planer)
-   `buerli.io` (CAD)
-   `getencube` (CAD)
-   `glowbuzzer` (CAD) — video
-   `triplex` (editor) — video
-   `theatrejs` (editor) — video

How to contribute
=================

If you like this project, please consider helping out. All contributions are welcome as well as donations to Opencollective, or in crypto `BTC: 36fuguTPxGCNnYZSRdgdh6Ea94brCAjMbH`, `ETH: 0x6E3f79Ea1d0dcedeb33D3fC6c34d2B1f156F2682`.

#### Backers

Thank you to all our backers! 🙏

#### Contributors

This project exists thanks to all the people who contribute.
