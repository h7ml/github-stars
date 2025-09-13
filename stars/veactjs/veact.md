---
project: veact
stars: 210
description: Mutable state enhancer library for React based on @vue/reactivity
url: https://github.com/veactjs/veact
---

  

Veact
=====

       

A mutable state enhancer library for `React`, built on top of `@vue/reactivity`.

#### Why Veact?

If you’re frustrated with the repetitive task of defining `props`, `emits`, `slots` and `attrs` in Vue, sometimes struggling to keep track of types, and you value the simplicity of managing everything with interfaces in React, then Veact is for you. Veact effortlessly merges the low cognitive overhead of Vue’s mutable state with the robust type support and flexibility of React’s JSX. It strikes a perfect balance between the strengths of both frameworks, providing a near-flawless development experience—without the complexity and potential pitfalls of useEffect in React.

Veact embodies what I believe is the **“best of both worlds”**—a powerful, yet intuitive library crafted to simplify and enhance your front-end development experience and efficiency.

#### Who is using this library 🔥

-   **veact-use** Veact hooks.
-   **surmon.admin** A CMS admin client for surmon.me blog.
-   ...

#### API & examples

-   API List
-   Example: Lifecycle
-   Example: Ref
-   Example: ShallowRef
-   Example: Reactive
-   Example: Computed
-   Example: Watch
-   Example: EffectScope
-   Example: Reactivity

Installation
------------

# using npm
npm install veact --save

# using yarn
yarn add veact

# using pnpm
pnpm add veact

Usage
-----

### Lifecycle

import React from 'react'
import { onMounted, onBeforeUnmount, onUpdated } from 'veact'

export const Component: React.FC \= () \=> {
  onMounted(() \=> {
    console.log('component mounted')
  })

  onUpdated(() \=> {
    console.log('component updated')
  })

  onBeforeUnmount(() \=> {
    console.log('component will unmount')
  })

  return <div\>component</div\>
}

### Ref

import React from 'react'
import { useRef } from 'veact'

export const Component: React.FC \= () \=> {
  const count \= useRef(0)
  const increment \= () \=> {
    count.value++
  }

  return (
    <div\>
      <p\>{count.value}</p\>
      <button onClick\={increment}\>increment</button\>
    </div\>
  )
}

### ShallowRef

import React from 'react'
import { useShallowRef } from 'veact'

export const Component: React.FC \= () \=> {
  const numbers \= useShallowRef(\[1, 2, 3\])
  const resetNumbers \= () \=> {
    numbers.value \= \[\]
  }

  return (
    <div\>
      <p\>{numbers.value.length}</p\>
      <button onClick\={resetNumbers}\>resetNumbers</button\>
    </div\>
  )
}

### Reactive

import React from 'react'
import { useReactive } from 'veact'

export const Component: React.FC \= () \=> {
  const data \= useReactive({
    count: 10,
    nested: { count: 1 },
  })

  const incrementCount \= () \=> {
    data.count++
  }

  const incrementNestedCount \= () \=> {
    data.nested.count++
  }

  return (
    <div\>
      <p\>{data.count}</p\>
      <p\>{data.nested.count}</p\>
      <button onClick\={incrementCount}\>incrementCount</button\>
      <button onClick\={incrementNestedCount}\>incrementNestedCount</button\>
    </div\>
  )
}

### Computed

import React from 'react'
import { useReactive, useComputed } from 'veact'

export const Component: React.FC \= () \=> {
  const data \= useReactive({
    year: 3,
    count: 4,
  })

  const total \= useComputed(() \=> {
    return data.count \* data.year
  })

  const incrementCount \= () \=> {
    data.count++
  }

  return (
    <div\>
      <span\>{total.value}</span\>
      <button onClick\={incrementCount}\>incrementCount</button\>
    </div\>
  )
}

### Watch

import React from 'react'
import { useReactive, useWatch } from 'veact'

export const Component: React.FC \= () \=> {
  const data \= useReactive({
    count: 0,
  })

  const incrementCount \= () \=> {
    data.count++
  }

  useWatch(data, (newData) \=> {
    console.log('data changed', newData)
  })

  useWatch(
    () \=> data.count,
    (newCount) \=> {
      console.log('count changed', newCount)
    },
  )

  return (
    <div\>
      <span\>{data.count}</span\>
      <button onClick\={incrementCount}\>incrementCount</button\>
    </div\>
  )
}

### EffectScope

import React from 'react'
import { watch, useRef, useEffectScope, onScopeDispose } from 'veact'

export const Component: React.FC \= () \=> {
  const scope \= useEffectScope()
  const counter \= useRef(0)

  const incrementCounter \= () \=> {
    counter.value++
  }

  scope.run(() \=> {
    const doubled \= computed(() \=> counter.value \* 2)
    watch(doubled, (newValue) \=> console.log(newValue))
    watchEffect(() \=> console.log('doubled: ', doubled.value))
    onScopeDispose(() \=> console.log('effect scope is stopped'))
  })

  return (
    <div\>
      <span\>{counter.value}</span\>
      <button onClick\={incrementCounter}\>incrementCounter</button\>
      <button onClick\={() \=> scope.pause()}\>pause Scope</button\>
      <button onClick\={() \=> scope.resume()}\>resume Scope</button\>
      <button onClick\={() \=> scope.stop()}\>stop Scope</button\>
    </div\>
  )
}

### Reactivity

Converts some of the 'raw Vue' data, which is not already wrapped in a hook, into reactive hook data to ensure proper reactivity within the component.

import React from 'react'
import { ref, useReactivity } from 'veact'

// ref data without hooks
const countRef \= ref(0)

export const Component: React.FC \= () \=> {
  // to reactivity hook
  const count \= useReactivity(() \=> countRef)
  const increment \= () \=> {
    count.value++
  }

  return (
    <div\>
      <span\>{count.value}</span\>
      <button onClick\={increment}\>increment</button\>
    </div\>
  )
}

API
---

All APIs listed here are implemented and provided by Veact. For additional exported types, please refer to `index.ts`.

Veact also re-exports all APIs from `@vue/reactivity`.

Veact API

Corresponding Capability

Description

`onMounted`

React `componentDidMount()`

The function is called right after the component is mounted.

`onUpdated`

React `componentDidUpdate()`

The function is called immediately after the component is re-rendered with updated props or state. (This method is not invoked during the initial render.)

`onBeforeUnmount`

React `componentWillUnmount()`

The function is called right before the component is unmounted.

`useRef`

Vue `ref()`

Takes an inner value and returns a reactive and mutable ref object, which has a single property `.value` that points to the inner value.

`useShallowRef`

Vue `shallowRef()`

Shallow version of `useRef()`.

`useCustomRef`

Vue `customRef()`

Creates a customized ref with explicit control over its dependency tracking and updates triggering.

`useReactive`

Vue `reactive()`

Returns a reactive proxy of the object.

`useShallowReactive`

Vue `shallowReactive()`

Shallow version of `useReactive()`.

`useReadonly`

Vue `readonly()`

Takes an object (reactive or plain) or a ref and returns a readonly proxy to the original.

`useShallowReadonly`

Vue `shallowReadonly()`

Shallow version of `useReadonly()`.

`useComputed`

Vue `computed()`

Takes a getter function and returns a readonly reactive ref object for the returned value from the getter. It can also take an object with get and set functions to create a writable ref object.

`watch`

Vue `watch()`

Watches one or more reactive data sources and invokes a callback function when the sources change. Unlike Vue (3.5.0), it does not support the `option.flush`.

`useWatch`

Vue `watch()`

Same as above, this is the hook implementation of `watch()`.

`watchEffect`

Vue `watchEffect()`

Runs a function immediately while reactively tracking its dependencies and re-runs it whenever the dependencies are changed. Unlike Vue (3.5.0), it does not support the `option.flush`.

`useWatchEffect`

Vue `watchEffect()`

Same as above, this is the hook implementation of `watchEffect()`.

`useEffectScope`

Vue `effectScope()`

Unlike `effectScope` in Vue, `useEffectScope().run()` will only execute once within the component and cannot contain any other hooks.

`useReactivity`

Internal implementation in Veact

Converts some of the 'raw Vue' data, which is not already wrapped in a hook, into reactive hook data to ensure proper reactivity within the component.

Development
-----------

# install dependencies
pnpm install

# dev
pnpm run dev

# lint
pnpm run lint

# test
pnpm run test

# build
pnpm run build

Changelog
---------

Detailed changes for each release are documented in the release notes.

License
-------

Licensed under the MIT License.
