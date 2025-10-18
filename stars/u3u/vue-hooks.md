---
project: vue-hooks
stars: 495
description: ⚡️Awesome Vue Hooks
url: https://github.com/u3u/vue-hooks
---

vue-hooks
=========

> ⚡️ Awesome Vue Hooks

Using `@vue/composition-api` to implement useful vue hooks.  
Vue 3.0 has not been released yet, it allows you to use functional-based components in advance.

⚠️ 2.x has been switched to `@vue/composition-api`, if you are using version 1.x please use `vue-function-api`

Install
-------

yarn add @vue/composition-api @u3u/vue-hooks

Documentation
-------------

Docs are available at https://vue-hooks.netlify.com

Usage
-----

import Vue from 'vue';
import VueCompositionAPI from '@vue/composition-api';
import hooks from '@u3u/vue-hooks';

Vue.use(hooks);
Vue.use(VueCompositionAPI); // Don't forget to use the plugin!

import { createComponent } from '@vue/composition-api';
import { useWindowSize } from '@u3u/vue-hooks';

export default createComponent({
  setup() {
    const { width, height, widthPixel, heightPixel } \= useWindowSize();
    return { width, height, widthPixel, heightPixel };
  },

  render() {
    const { width, height, widthPixel, heightPixel } \= this;
    return (
      <div id\="app" style\={{ width: widthPixel, height: heightPixel }}\>
        dynamic window size: {width}, {height}
      </div\>
    );
  },
});

Hooks
-----

-   `useDate` — Using `dayjs` to process date.
-   `useWindowSize` — Tracks `window` dimensions.
-   `useCounter` — Tracks state of a number.
-   `usePrevious` — Returns the previous state or props.
-   `useRouter` — A hook for `vue-router`.
-   `useStore` — A hook for `vuex`.
-   `useState` — A hook for `mapState`.
-   `useGetters` — A hook for `mapGetters`.
-   `useMutations` — A hook for `mapMutations`.
-   `useActions` — A hook for `mapActions`.

Contributing
------------

1.  Fork it!
2.  Create your feature branch: `git checkout -b feat/new-hook`
3.  Commit your changes: `git commit -am 'feat(hooks): add a new hook'`
4.  Push to the branch: `git push origin feat/new-hook`
5.  Submit a pull request :D

Contributors
------------

Thanks goes to these wonderful people (emoji key):

  
**u3u**  
💻 📖 💡 ⚠️

This project follows the all-contributors specification. Contributions of any kind are welcome!

License
-------

MIT
