---
project: codemirror-editor-vue3
stars: 238
description: CodeMirror component for Vue3
url: https://github.com/rennzhang/codemirror-editor-vue3
---

Introduction
============

简体中文

The codemirror component of vue3. This component is developed based on Codemirror 5 and only vue3 is supported.

In addition to the officially supported modes, the log output presentation mode is added, out of the box, but not necessarily suitable for all scenarios.

For complete documentation and more cases, please check codemirror-editor-vue3 docs.

Install
-------

npm install codemirror-editor-vue3 codemirror@^5 -S

yarn add codemirror-editor-vue3 codemirror@"\>=5.64.0 <6"

pnpm i codemirror-editor-vue3 codemirror@^5 -S

> If your project requires Typescript support, you will also need to install the '@types/codemirror' dependency.

npm install @types/codemirror -D

Register global component
-------------------------

> **Do not recommend global registration components**, which will result in the type of prompt on the template that cannot be properly obtained.

`main.js:`

import { createApp } from "vue";
import App from "./App.vue";
import { InstallCodeMirror } from "codemirror-editor-vue3";

const app \= createApp(App);
app.use(InstallCodeMirror);
app.mount("#app");

The global registered component name is Codemirror or you can customize a component name, for example:

app.use(InstallCodeMirror, { componentName: "customName" });

Use in components
-----------------

<template\>
  <Codemirror
    v-model:value\="code"
    :options\="cmOptions"
    border
    placeholder\="test placeholder"
    :height\="200"
    @change\="change"
  />
</template\>

<script\>
import Codemirror from "codemirror-editor-vue3";
// placeholder
import "codemirror/addon/display/placeholder.js";
// language
import "codemirror/mode/javascript/javascript.js";
// placeholder
import "codemirror/addon/display/placeholder.js";
// theme
import "codemirror/theme/dracula.css";
import { ref } from "vue";
export default {
  components: { Codemirror },
  setup() {
    const code \= ref(\`
var i = 0;
for (; i < 9; i++) {
  console.log(i);
  // more statements
}\`);
    return {
      code,
      cmOptions: {
        mode: "text/javascript", // Language mode
        theme: "dracula", // Theme
      },
    };
  },
};
</script\>

Language highlighting
---------------------

> You can click on the following link to view corresponding language cases

-   javascript
-   json
-   css
-   html
-   apl
-   yaml

More cases are gradually being added, and you can also refer to document to achieve more language modes.

Component Props
---------------

name

description

type

default

**value(v-model)**

Editor content

`string`

""

**options**

Configuration options of codemirror5

EditorConfiguration

DEFAULT\_OPTIONS

**placeholder**

Editor placeholder content to introduce codemirror related files

`string`

""

**border**

Whether to display editor borders

`boolean`

`false`

**width**

width

`string`

`100%`

**height**

height

`string`

`100%`

**original-style**

Using the original style, disable the second modification of the style for this component (but does not affect width, height, and border)

`boolean`

`false`

**KeepCursorInEnd**

Always keep the mouse position on the last line

`boolean`

`false`

**merge**

merge mode, can also be used as diff pattern

`boolean`

`false`

Events
------

### Component Events

> The following three are only the events encapsulated by this component. Please refer to more events Codemirror Events

event name

description

params

`change`

value or instance changes

`(value: string, cm: Editor) => void`

`input`

input

`(value: string) => void`

`ready`

The Codemirror component is mounted

`(cm: Editor) => void;`

* * *

### Codemirror Events

The following events are official events of Codemirror5. You can refer to the official documents for details Codemirror Event，You can use this component to bind events directly through components, for example：

<Codemirror
  v-model:value\="code"
  :options\="{ mode: 'text/x-vue', theme: 'default' }"
  border
  placeholder="test-placeholder"
  :height\="200"
  @change\="onChange"
  @blur\="onBlur"
  @focus\="onFocus"
  @scroll\="onScroll"
/>

> All event names are as follows：

-   `changes`
-   `scroll`
-   `beforeChange`
-   `cursorActivity`
-   `keyHandled`
-   `inputRead`
-   `electricInput`
-   `beforeSelectionChange`
-   `viewportChange`
-   `swapDoc`
-   `gutterClick`
-   `gutterContextMenu`
-   `focus`
-   `blur`
-   `refresh`
-   `optionChange`
-   `scrollCursorIntoView`
-   `update`
