---
project: tango-boot
stars: 13
description: A frontend framework for netease tango low-code app
url: https://github.com/NetEase/tango-boot
---

TangoBoot
=========

TangoBoot is a frontend framework that serves the NetEase Tango Low-Code applications. It provides standard data requests, state management, and routing solutions, as well as generic runtime utility functions, allowing developers to generate Single Page Applications through less codes.

Documentation: https://netease.github.io/tango/docs/boot/intro/

How to develop
--------------

Environment requirements:

-   Node >= 16.0.0
-   Yarn == 1.x stable

Run the example app via the following commands:

# install dependencies
yarn

# build the library
yarn build

# start the example app
yarn start

Application Architecture
------------------------

The application architecture of TangoBoot uses the View-Model-Service three-layer model. The model layer defines Observable States, the view layer observes the changes of the model and updates automatically, and the service layer is used to create a set of service functions for the consumption of the view layer and the model layer. The diagram is shown in the figure below:

Core API
--------

-   `runApp` create the app entry
-   `definePage` define reactive views
-   `defineStore` define observable states
-   `defineServices` define async service functions

How to use
----------

### Create app entry

The `index.js` is the app entry file，a simple example is:

import { runApp } from '@music163/tango-boot';
import routes from './routes';
import services from './services';
import home from './stores/home';
import counter from './stores/counter';
import './global.less';

const { mount, unmount, bootstrap } \= runApp({
  boot: {
    mountElement: document.querySelector('#root'),
    qiankun: false,
  },

  stores: {
    home,
    counter,
  },

  services,

  router: {
    type: 'browser',
    config: routes,
  },
});

export { mount, unmount, bootstrap };

### Create Observable States

Defining a view model through defineStore is very simple, simply declare the state and actions.

import { defineStore } from '@music163/tango-boot';

const counter \= defineStore({
  num: 0,

  get() {},

  decrement: function () {
    counter.num\--;
  },

  increment: () \=> counter.num++,
});

export default counter;

### Create Reactive Views

If the view layer needs to listen for state changes, it only needs to wrap the view component with `definePage`.

import React from 'react';
import tango, { definePage } from '@music163/tango-boot';

class App extends React.Component {
  increment \= () \=> {
    tango.stores.counter.increment();
  };

  render() {
    return (
      <div\>
        <h1\>Counter: {tango.stores.counter.num}</h1\>
        <button type\="primary" onClick\={this.increment}\>
          +1
        </button\>
      </div\>
    );
  }
}

export default definePage(App);

### Create Service Functions

Use `defineServices` to define your remote apis as service functions.

import { defineServices } from '@music163/tango-boot';

export default defineServices({
  list: {
    url: 'https://nei.hz.netease.com/api/apimock-v2/c45109399a1d33d83e32a59984b25b00/api/users',
    formatter: (res) \=> {
      const { data, message } \= res;
      return {
        code: 200,
        list: data,
        total: data.length,
        message,
      };
    },
  },
  add: {
    url: 'https://nei.hz.netease.com/api/apimock-v2/c45109399a1d33d83e32a59984b25b00/api/users',
    method: 'post',
  },
  update: {
    url: 'https://nei.hz.netease.com/api/apimock-v2/c45109399a1d33d83e32a59984b25b00/api/users',
    method: 'post',
  },
  delete: {
    url: 'https://nei.hz.netease.com/api/apimock-v2/c45109399a1d33d83e32a59984b25b00/api/users?id=1',
  },
});

License
-------

This project is licensed under the terms of the MIT license.
