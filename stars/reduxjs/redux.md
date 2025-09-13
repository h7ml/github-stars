---
project: redux
stars: 61329
description: A JS library for predictable global state management
url: https://github.com/reduxjs/redux
---

Redux
=====

Redux is a JS library for predictable and maintainable global state management.

It helps you write applications that behave consistently, run in different environments (client, server, and native), and are easy to test. On top of that, it provides a great developer experience, such as live code editing combined with a time traveling debugger.

You can use Redux together with React, or with any other view library. The Redux core is tiny (2kB, including dependencies), and has a rich ecosystem of addons.

**Redux Toolkit** is our official recommended approach for writing Redux logic. It wraps around the Redux core, and contains packages and functions that we think are essential for building a Redux app. Redux Toolkit builds in our suggested best practices, simplifies most Redux tasks, prevents common mistakes, and makes it easier to write Redux applications.

Installation
------------

### Create a React Redux App

The recommended way to start new apps with React and Redux Toolkit is by using our official Redux Toolkit + TS template for Vite, or by creating a new Next.js project using Next's `with-redux` template.

Both of these already have Redux Toolkit and React-Redux configured appropriately for that build tool, and come with a small example app that demonstrates how to use several of Redux Toolkit's features.

# Vite with our Redux+TS template
# (using the \`degit\` tool to clone and extract the template)
npx degit reduxjs/redux-templates/packages/vite-template-redux my-app

# Next.js using the \`with-redux\` template
npx create-next-app --example with-redux my-app

We do not currently have official React Native templates, but recommend these templates for standard React Native and for Expo:

-   https://github.com/rahsheen/react-native-template-redux-typescript
-   https://github.com/rahsheen/expo-template-redux-typescript

```
npm install @reduxjs/toolkit react-redux
```

For the Redux core library by itself:

```
npm install redux
```

For more details, see the Installation docs page.

Documentation
-------------

The Redux core docs are located at **https://redux.js.org**, and include the full Redux tutorials, as well usage guides on general Redux patterns:

-   Introduction
-   Tutorials
-   Usage Guides
-   FAQ
-   API Reference

The Redux Toolkit docs are available at **https://redux-toolkit.js.org**, including API references and usage guides for all of the APIs included in Redux Toolkit.

Learn Redux
-----------

### Redux Essentials Tutorial

The **Redux Essentials tutorial** is a "top-down" tutorial that teaches "how to use Redux the right way", using our latest recommended APIs and best practices. We recommend starting there.

### Redux Fundamentals Tutorial

The **Redux Fundamentals tutorial** is a "bottom-up" tutorial that teaches "how Redux works" from first principles and without any abstractions, and why standard Redux usage patterns exist.

### Help and Discussion

The **#redux channel** of the **Reactiflux Discord community** is our official resource for all questions related to learning and using Redux. Reactiflux is a great place to hang out, ask questions, and learn - please come and join us there!

Before Proceeding Further
-------------------------

Redux is a valuable tool for organizing your state, but you should also consider whether it's appropriate for your situation. Please don't use Redux just because someone said you should - instead, please take some time to understand the potential benefits and tradeoffs of using it.

Here are some suggestions on when it makes sense to use Redux:

-   You have reasonable amounts of data changing over time
-   You need a single source of truth for your state
-   You find that keeping all your state in a top-level component is no longer sufficient

Yes, these guidelines are subjective and vague, but this is for a good reason. The point at which you should integrate Redux into your application is different for every user and different for every application.

> **For more thoughts on how Redux is meant to be used, please see:**  
> 
> -   **When (and when not) to reach for Redux**
> -   **You Might Not Need Redux**  
>     
> -   **The Tao of Redux, Part 1 - Implementation and Intent**  
>     
> -   **The Tao of Redux, Part 2 - Practice and Philosophy**
> -   **Redux FAQ**

Basic Example
-------------

The whole global state of your app is stored in an object tree inside a single _store_. The only way to change the state tree is to create an _action_, an object describing what happened, and _dispatch_ it to the store. To specify how state gets updated in response to an action, you write pure _reducer_ functions that calculate a new state based on the old state and the action.

Redux Toolkit simplifies the process of writing Redux logic and setting up the store. With Redux Toolkit, the basic app logic looks like:

import { createSlice, configureStore } from '@reduxjs/toolkit'

const counterSlice \= createSlice({
  name: 'counter',
  initialState: {
    value: 0
  },
  reducers: {
    incremented: state \=> {
      // Redux Toolkit allows us to write "mutating" logic in reducers. It
      // doesn't actually mutate the state because it uses the Immer library,
      // which detects changes to a "draft state" and produces a brand new
      // immutable state based off those changes
      state.value += 1
    },
    decremented: state \=> {
      state.value \-= 1
    }
  }
})

export const { incremented, decremented } \= counterSlice.actions

const store \= configureStore({
  reducer: counterSlice.reducer
})

// Can still subscribe to the store
store.subscribe(() \=> console.log(store.getState()))

// Still pass action objects to \`dispatch\`, but they're created for us
store.dispatch(incremented())
// {value: 1}
store.dispatch(incremented())
// {value: 2}
store.dispatch(decremented())
// {value: 1}

Redux Toolkit allows us to write shorter logic that's easier to read, while still following the original core Redux behavior and data flow.

Logo
----

You can find the official logo on GitHub.

Change Log
----------

This project adheres to Semantic Versioning. Every release, along with the migration instructions, is documented on the GitHub Releases page.

License
-------

MIT
