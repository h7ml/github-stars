---
project: fre
stars: 3749
description: :ghost: Tiny Concurrent UI library with Fiber.
url: https://github.com/frejs/fre
---

Fre
===

👻 Tiny Concurrent UI library with Fiber.

-   **Concurrent Mode** — This is an amazing idea, which implements the coroutine scheduler in JavaScript, it also called **Time slicing**.
    
-   **Keyed reconcilation algorithm** — Fre has a minimal diff algorithm, It supported keyed, pre-process, offscreen rendering and SSR hydration.
    
-   **Do more with less** — Fre get the tiny size, but it has most features, virtual DOM, hooks API, Suspense, Fragments, Fre.memo and so on.
    

### Contributors

### Usage

yarn add fre

import { render, useState } from 'fre'

function App() {
  const \[count, setCount\] \= useState(0)
  return <\>
      <h1\>{count}</h1\>
      <button onClick\={() \=> setCount(count + 1)}\>+</button\>
    </\>
}

render(<App/>, document.body)

### Features

-   Suspense
    
-   memo
    
-   ErrorBoundary
    

### Hooks API

-   useState
    
-   useEffect
    
-   useReducer
    
-   useLayout
    
-   useCallback
    
-   useMemo
    
-   useRef
    
-   useContext
    

#### useState

`useState` is a base API, It will receive initial state and return an Array

You can use it many times, new state is available when component is rerender

function App() {
  const \[up, setUp\] \= useState(0)
  const \[down, setDown\] \= useState(() \=> 0)
  return (
    <\>
      <h1\>{up}</h1\>
      <button onClick\={() \=> setUp(up + 1)}\>+</button\>
      <h1\>{down}</h1\>
      <button onClick\={() \=> setDown(down \- 1)}\>\-</button\>
    </\>
  )
}

#### useReducer

`useReducer` and `useState` are almost the same，but `useReducer` needs a global reducer

function reducer(state, action) {
  switch (action.type) {
    case 'up':
      return { count: state.count + 1 }
    case 'down':
      return { count: state.count \- 1 }
  }
}

function App() {
  const \[state, dispatch\] \= useReducer(reducer, { count: 1 })
  return (
    <\>
      {state.count}
      <button onClick\={() \=> dispatch({ type: 'up' })}\>+</button\>
      <button onClick\={() \=> dispatch({ type: 'down' })}\>\-</button\>
    </\>
  )
}

#### useEffect

It is the execution and cleanup of effects, which is represented by the second parameter

```
useEffect(f)       //  effect (and clean-up) every time
useEffect(f, [])   //  effect (and clean-up) only once in a component's life
useEffect(f, [x])  //  effect (and clean-up) when property x changes in a component's life
```

function App({ flag }) {
  const \[count, setCount\] \= useState(0)
  useEffect(() \=> {
    document.title \= 'count is ' + count
  }, \[flag\])
  return (
    <\>
      <h1\>{count}</h1\>
      <button onClick\={() \=> setCount(count + 1)}\>+</button\>
    </\>
  )
}

If it returns a function, the function can do cleanups:

useEffect(() \=> {
  document.title \= 'count is ' + count
  return () \=> {
    store.unsubscribe()
  }
}, \[\])

#### useLayout

More like useEffect, but useLayout is sync and blocking UI.

useLayout(() \=> {
  document.title \= 'count is ' + count
}, \[flag\])

#### useMemo

`useMemo` has the same rules as `useEffect`, but `useMemo` will return a cached value.

const memo \= (c) \=> (props) \=> useMemo(() \=> c, \[Object.values(props)\])

#### useCallback

`useCallback` is based `useMemo`, it will return a cached function.

const cb \= useCallback(() \=> {
  console.log('cb was cached.')
}, \[\])

#### useRef

`useRef` will return a function or an object.

function App() {
  useEffect(() \=> {
    console.log(t) // { current:<div>t</div> }
  })
  const t \= useRef(null)
  return <div ref\={t}\>t</div\>
}

If it uses a function, it can return a cleanup and executes when removed.

function App() {
  const t \= useRef((dom) \=> {
    if (dom) {
      doSomething()
    } else {
      cleanUp()
    }
  })
  return flag && <span ref\={t}\>I will removed</span\>
}

#### useContext

import { createContext, useContext } from 'react';

const ThemeContext \= createContext(null);

function App() {
  return (
    <ThemeContext value\="dark"\>
      <Button />
    </ThemeContext\>
  )
}

function Button({ children }) {
  const theme \= useContext(ThemeContext);
  const className \= 'button-' + theme;
  return (
    <button class\={className}\>
      {children}
    </button\>
  );
}

### Suspense

const Hello \= lazy('./hello.js')

export function App() {
  return (
    <div\>
      <Suspense fallback\={<div\>loading...</div\>}\>
        <Hello />
        <div\>world!</div\>
      </Suspense\>
    </div\>
  )
}

### ErrorBoundary

function A(){
  throw new Error('render error test')
}

export function App() {
  return (
    <div\>
      <ErrorBoundary fallback\={<div\>occur an error</div\>}\>
        <A />
      </ErrorBoundary\>
    </div\>
  )
}

### Fragments

// fragment
function App() {
  return <\>{something}</\>
}
// render array
function App() {
  return \[a, b, c\]
}

### jsx

For vite example

export default {
  esbuild: {
    jsxFactory: 'h',
    jsxFragment: 'Fragment',
    jsxInject: \`import { h, Fragment } from 'fre'\`,
    target: 'es2020',
    format: 'esm'
  }
}

#### License

MIT @yisar
