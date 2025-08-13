---
project: schema-plugin-flow
stars: 425
description: A highly extensible JavaScript library, abbreviated as Sifo. 一个高扩展性、可二开的插件式前端开发框架
url: https://github.com/alibaba/schema-plugin-flow
---

schema-plugin-flow
==================

English | 简体中文

Introduction
------------

schema-plugin-flow, abbreviated as Sifo (\[sɪfɔ\])，is a highly extensible JavaScript library. This library allows developers to extend business logic and page layout without touching source code, when the source code is written in Sifo.

-   sifo-model is the core of Sifo, which using JSON (as Schema) to describe page's structures and using plugins as logic controller. There are three kinds of plugin: modelPlugin、pagePlugin and componentPluign. You can learn about Sifo's basic information and the usage patterns by reading this package's README.
-   sifo-react is a React Component encapsulates sifo-model and sifo-singleton. sifo-react also support `sifoAppDecorator`, with which a normal React Commponent will has extension ability. You can learn about that via package's README or online demos.
-   sifo-vue is a Vue Component encapsulates sifo-model and sifo-singleton. sifo-vue also support `sifoAppDecorator`, with which a normal Vue Commponent will has extension ability. You can learn about that via package's README or online demos.
-   sifo-singleton is a global extensions holder. All kinds of extend-plugins and extend-components are registered to it.

Three elements of Sifo
----------------------

-   schema: to describe page's structures
-   components
-   plugins: logic controller

SifoApp (sifo-react/sifo-vue) Demo
----------------------------------

-   form-extend-demo
    
    sifo-react-extends-demo
    
-   simple demo
    
    In this demo, there are seven extend-plugins in seven independent js. The checkbox set which plugin should be registered. Each plugin control different logic and all registered plugins make up a integrated page.
    

### modelPlugins

-   sifo-mplg-react-optimize is a modelPlugin for sifo-react optimization.
-   sifo-mplg-form-core is a sifo form-core model plugin. This model plugin, basing on simple schema setting, realized the form fields' control and supplied form operations with a serial of api.
-   sifo-mplg-form-antdv is a sifo form with Ant-Design-Vue, works with sifo-mplg-form-core and sifo-vue.
-   sifo-mplg-form-antd is a sifo form with Ant-Design, works with sifo-mplg-form-core and sifo-react.
-   sifo-mplg-form-fusion is a sifo form with Fusion, works with sifo-mplg-form-core and sifo-react.
-   sifo-mplg-form-antd-mobile is a sifo form with Ant-Design-Mobile, works with sifo-mplg-form-core and sifo-react.
-   sifo-mplg-drag Sifo drag model plugin. Basing on custom Components and Schema rendering, you can drag and drop component instantaneously and reconstruct a Schema. Please refer to sifo-mplg-drag-react and sifo-mplg-drag-vue.
-   sifo-mplg-drag-react Sifo drag model plugin for React components.
-   sifo-mplg-drag-vue Sifo drag model plugin for Vue components.

Sifo family
-----------

-   `sifo-model` + `react` = `sifo-react`
-   `sifo-model` + `vue` = `sifo-vue`
-   `sifo-react` + `sifo-mplg-form-core` + `ant-design` = `sifo-mplg-form-antd`
-   `sifo-react` + `sifo-mplg-form-core` + `fusion` = `sifo-mplg-form-fusion`
-   `sifo-vue` + `sifo-mplg-form-core` + `ant-design-vue` = `sifo-mplg-form-antdv`

Installation
------------

$ npm i @schema-plugin-flow/sifo-model --save
$ npm i @schema-plugin-flow/sifo-react --save
$ npm i @schema-plugin-flow/sifo-vue --save

How Sifo extensions works
-------------------------

How to use
----------

-   project
    
    -   extend.js
        
        import SifoSingleton from '@schema-plugin-flow/sifo-singleton';
        const singleton \= new SifoSingleton('quick-start'); // target namespace
        singleton.registerItem('testExtendId', () \=> {
          return {
            plugins,
            components
          }
        });
        
    -   app.js
        
        import React from 'react';
        import ReactDOM from "react-dom";
        import SifoApp from '@schema-plugin-flow/sifo-react';
        const plugins \= \[{ modelPlugin, componentPlugin, pagePlugin }\];
        class App extends React.Component {
          render() {
            return (
              <SifoApp
                namespace\='quick-start'
                components\={components}
                schema\={schema}
                plugins\={plugins}
              />
            );
          }
        }
        ReactDOM.render(
          <App />
          rootElement
        );
        
-   runtime
    
    -   load extend js
        
    -   load app js
        
        you should load the extend js before sifoApp rendered.
        
        <script src\="extend.js"\></script\>
        <script src\="app.js"\></script\>
        

Try in local
------------

-   React
    
    -   clone code and start
    
    $ git clone https://github.com/alibaba/schema-plugin-flow.git
    $ cd schema-plugin-flow
    $ npm run i
    $ npm run start
    
    -   then visit `http://localhost:8000`.
-   Vue
    
    -   clone code and start
    
    $ git clone https://github.com/alibaba/schema-plugin-flow.git
    $ cd schema-plugin-flow
    $ npm run i
    $ npm run i-vue
    $ npm run start-vue
    
    -   then visit `http://localhost:8080`.

Try online (codesandbox.io)
---------------------------

-   sifo-react
    
    -   sifo-react-quick-start
    -   sifo-react-decorator
    -   sifo-mplg-form-antd
    -   sifo-react-mplg-optimize
    -   sifo-mplg-drag-react
-   sifo-vue
    
    -   sifo-vue-quick-start
    -   sifo-vue-decorator
    -   sifo-vue-use-optimize
    -   sifo-mplg-form-antdv
    -   sifo-mplg-drag-vue
