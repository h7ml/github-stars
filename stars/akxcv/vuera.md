---
project: vuera
stars: 4309
description: :eyes: Vue in React, React in Vue. Seamless integration of the two. :dancers:
url: https://github.com/akxcv/vuera
---

vuera
=====

> ⚠️ Vuera has been archived.

> Check out veaury or vuera-ts for a more up-to date library.

Use Vue components in your React app:

import React from 'react'
import MyVueComponent from './MyVueComponent.vue'

export default props \=>
  <div\>
    <MyVueComponent message\={props.message} handleReset\={props.handleReset} />
  </div\>

Or use React components in your Vue app:

<template\>
  <div\>
    <my-react-component :message\="message" @reset\="reset" />
  </div\>
</template\>

<script\>
  import MyReactComponent from './MyReactComponent'
  export default {
    /\* data, methods, etc \*/
    components: { 'my-react-component': MyReactComponent },
  }
</script\>

Use cases
---------

-   👨‍👩‍👧 Using both Vue and React in one app
-   🏃 Migrating from React to Vue or from Vue to React

Installation
------------

Install with yarn:

$ yarn add vuera
# or with npm:
$ npm i -S vuera

You can also try the library out via unpkg:

<script src\="https://unpkg.com/vuera"\></script\>

Usage
-----

### Vue in React - Preferred usage

The preferred way to use Vue inside of a React app is to use a Babel plugin.

Add `vuera/babel` to `plugins` section of your `.babelrc`:

{
  "presets": "react",
  "plugins": \["vuera/babel"\]
}

Now, just use your Vue components like you would use your React components!

import React from 'react'
import MyVueComponent from './MyVueComponent.vue'

export default () \=> (
  <div\>
    <h1\>I'm a react component</h1\>
    <div\>
      <MyVueComponent message\='Hello from Vue!' />
    </div\>
  </div\>
)

### React in Vue - Preferred usage

The preferred way to use React inside of a Vue app is to use a Vue plugin.

import Vue from 'vue'
import { VuePlugin } from 'vuera'

Vue.use(VuePlugin)
/\* ... \*/

Now, use your React components like you would normally use your Vue components!

<template\>
  <div\>
    <h1\>I'm a Vue component</h1\>
    <my-react-component :message\="message" @reset\="reset" />
  </div\>
</template\>

<script\>
  import MyReactComponent from './MyReactComponent'
  export default {
    data () {
      message: 'Hello from React!',
    },
    methods: {
      reset () {
        this.message \= ''
      }
    },
    components: { 'my-react-component': MyReactComponent },
  }
</script\>

If you configure options in the root instance of a `Vue`, those will not be passed by default to Vue instances within React components. So, for example an i18n or a store instance option configured at the top level is not available in the children Vue components wrapped in React components. To fix this, configure `vueInstanceOptions` similar to:

import Vue from 'vue'
// import other plugins or modules
import { config } from 'vuera'

// Vue.use(...)

config.vueInstanceOptions \= { plugin: thePlugIn, store: myStore };

**NOTE**: If you're using Vue < 2.4, you _must_ pass all props to your React components via a special prop called `passedProps`:

<template\>
  <div\>
    <h1\>I'm a Vue component</h1\>
    <my-react-component :passedProps\="passedProps"\></my-react-component\>
  </div\>
</template\>

<script\>
  import { ReactWrapper } from 'vuera'
  import MyReactComponent from './MyReactComponent'
  export default {
    data () {
      message: 'Hello from React!',
    },
    methods: {
      reset () {
        this.message \= ''
      }
    },
    computed: {
      passedProps () {
        return {
          message: this.message,
          reset: this.reset,
        }
      },
    },
    components: { 'my-react-component': MyReactComponent },
  }
</script\>

### Vue in React - without the Babel plugin

If you don't want to use the Babel plugin, you still have two ways of using this library.

1.  Use a wrapper component:

import React from 'react'
import { VueWrapper } from 'vuera'
import MyVueComponent from './MyVueComponent.vue'

export default () \=> (
  <div\>
    <VueWrapper
      component\={MyVueComponent}
      message\='Hello from Vue!'
    />
  </div\>
)

1.  Or use the HOC API:

import React from 'react'
import { VueInReact } from 'vuera'
import MyVueComponent from './MyVueComponent.vue'

export default () \=> {
  const Component \= VueInReact(MyVueComponent)
  return (
    <div\>
      <Component message\='Hello from Vue!' />
    </div\>
  )
}

### React in Vue - without the Vue plugin

If you don't want to use the Vue plugin, you still have two ways of using this library.

1.  Use a wrapper component:

<template\>
  <div\>
    <react :component\="component" :message\="message" />
  </div\>
</template\>

<script\>
  import { ReactWrapper } from 'vuera'
  import MyReactComponent from './MyReactComponent'
  export default {
    data () {
      component: MyReactComponent,
      message: 'Hello from React!',
    },
    components: { react: ReactWrapper }
  }
</script\>

1.  Use the HOC API:

<template\>
  <div\>
    <my-react-component :message\="message" />
  </div\>
</template\>

<script\>
  import { ReactInVue } from 'vuera'
  import MyReactComponent from './MyReactComponent'
  export default {
    data () {
      message: 'Hello from React!',
    },
    components: { 'my-react-component': ReactInVue(MyReactComponent) }
  }
</script\>

FAQ (I think)
-------------

### Are children supported?

Yes. You can pass children from React to Vue and back as you usually would.

React (children will go to the default slot of the Vue component):

import React from 'react'
import MyVueComponent from './MyVueComponent.vue'

export default props \=>
  <div\>
    <MyVueComponent message\={props.message}\>
      Hello there!
    </MyVueComponent\>
  </div\>

Vue:

<template\>
  <div\>
    <my-react-component :message\="message"\>
      G'day sir
    </my-react-component\>
  </div\>
</template\>

<script\>
  import MyReactComponent from './MyReactComponent'
  export default {
    components: { 'my-react-component': MyReactComponent },
  }
</script\>

### What's the performance? How fast/slow is it compared to pure React / Vue?

I don't know, but the benchmark is coming. Stay tuned.

Articles
--------

Integrating React and Vue Components in One Application by @josephrexme

License
-------

MIT
