---
project: xyflow
stars: 33534
description: React Flow | Svelte Flow - Powerful open source libraries for building node-based UIs with React (https://reactflow.dev) or Svelte (https://svelteflow.dev). Ready out-of-the-box and infinitely customizable.
url: https://github.com/xyflow/xyflow
---

Powerful open source libraries for building node-based UIs with React or Svelte. Ready out-of-the-box and infinitely customizable.

React Flow · Svelte Flow · React Flow Pro · Discord

* * *

The xyflow mono repo
--------------------

The xyflow repository is the home of four packages:

-   React Flow 12 `@xyflow/react` packages/react
-   React Flow 11 `reactflow` v11 branch
-   Svelte Flow `@xyflow/svelte` packages/svelte
-   Shared helper library `@xyflow/system` packages/system

Commercial usage
----------------

**Are you using React Flow or Svelte Flow for a personal project?** Great! No sponsorship needed, you can support us by reporting any bugs you find, sending us screenshots of your projects, and starring us on Github 🌟

**Are you using React Flow or Svelte Flow at your organization and making money from it?** Awesome! We rely on your support to keep our libraries developed and maintained under an MIT License, just how we like it. For React Flow you can do that on the React Flow Pro website and for both of our libraries you can do it through Github Sponsors.

Getting started
---------------

The best way to get started is to check out the React Flow or Svelte Flow learn section. However if you want to get a sneak peek of how to install and use the libraries you can see it here:

**React Flow** basic usage

### Installation

npm install @xyflow/react

### Basic usage

import { useCallback } from 'react';
import {
ReactFlow,
MiniMap,
Controls,
Background,
useNodesState,
useEdgesState,
addEdge,
} from '@xyflow/react';

import '@xyflow/react/dist/style.css';

const initialNodes \= \[
{ id: '1', position: { x: 0, y: 0 }, data: { label: '1' } },
{ id: '2', position: { x: 0, y: 100 }, data: { label: '2' } },
\];

const initialEdges \= \[{ id: 'e1-2', source: '1', target: '2' }\];

function Flow() {
const \[nodes, setNodes, onNodesChange\] \= useNodesState(initialNodes);
const \[edges, setEdges, onEdgesChange\] \= useEdgesState(initialEdges);

const onConnect \= useCallback((params) \=> setEdges((eds) \=> addEdge(params, eds)), \[setEdges\]);

return (
  <ReactFlow
    nodes\={nodes}
    edges\={edges}
    onNodesChange\={onNodesChange}
    onEdgesChange\={onEdgesChange}
    onConnect\={onConnect}
  \>
    <MiniMap />
    <Controls />
    <Background />
  </ReactFlow\>
);
}

export default Flow;

**Svelte Flow** basic usage

### Installation

npm install @xyflow/svelte

### Basic usage

<script lang\="ts"\>
import { writable } from 'svelte/store';
import {
  SvelteFlow,
  Controls,
  Background,
  BackgroundVariant,
  MiniMap,
} from '@xyflow/svelte';
import '@xyflow/svelte/dist/style.css'
const nodes \= writable(\[
  {
    id: '1',
    type: 'input',
    data: { label: 'Input Node' },
    position: { x: 0, y: 0 }
  },
  {
    id: '2',
    type: 'custom',
    data: { label: 'Node' },
    position: { x: 0, y: 150 }
  }
\]);
const edges \= writable(\[
  {
    id: '1-2',
    type: 'default',
    source: '1',
    target: '2',
    label: 'Edge Text'
  }
\]);
</script\>

<SvelteFlow
{nodes}
{edges}
fitView
on:nodeclick\={(event) \=> console.log('on node click', event)}
>
<Controls />
<Background variant\={BackgroundVariant.Dots} />
<MiniMap />
</SvelteFlow\>

Releases
--------

For releasing packages we are using changesets in combination with the changeset Github action. The rough idea is:

1.  create PRs for new features, updates and fixes (with a changeset if relevant for changelog)
2.  merge into main
3.  changset creates a PR that bumps all packages based on the changesets
4.  merge changeset PR if you want to release to Github and npm

Built by xyflow
---------------

React Flow and Svelte Flow are maintained by the xyflow team. If you need help or want to talk to us about a collaboration, reach out through our contact form or by joining our Discord Server.

License
-------

React Flow and Svelte Flow are MIT licensed.
