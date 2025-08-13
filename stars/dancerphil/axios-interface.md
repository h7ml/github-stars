---
project: axios-interface
stars: 9
description: Create your API with `pre&post` processing & type inference
url: https://github.com/dancerphil/axios-interface
---

axios-interface
===============

`axios-interface` helps you to define api, along with its type.

English | 中文

GetStarted
----------

```
yarn add axios-interface
```

### Basic Usage

`axios-interface` separate api into 3 stage: factory => interface => call. In each stage, you can pass in some options.

import {createFactory} from 'axios-interface';

// factory
const {createInterface} \= createFactory(options);

// interface
interface Params {
    companyId: string;
    keyword?: string;
}

interface User {
    name: string;
}

const getUsers \= createInterface<Params, User\[\]\>('GET', '/rest/companies/{companyId}/users', options);

// call
const result \= await getUsers({companyId: '1', keyword: 'jack'}); // GET /rest/companies/1/users?keyword=jack

### About Options

interface Options extends AxiosRequestConfig {
    onPending?: OnPending;
    onResolve?: OnResolve;
    onReject?: OnReject;
    interpolate?: RegExp; // Default as /{(\\w+)}/g
    encodePathVariable?: boolean; // Parse variable like \`a/b\` into \`a%2fb\`. Default as false
    transformDeleteParamsIntoBody?: boolean; // Change the way to treat with \`params\` when \`DELETE\`. Default as false.
    /\*\*
     \* Some axios options such as headers.
     \* Or whatever custom options you want. They will pass through 3 stages.
     \*/
    \[whatever: string\]: any;
}

// Some types can be imported as \`import {OnPending} from 'axios-interface'\`
type OnPending \= <TParams\>(params: TParams, options: Options) \=> Options | Promise<Options\>;
type OnResolve \= <TParams\>(response: AxiosResponse, params: TParams, options: Options) \=> any;
type OnReject \= <TParams\>(response: AxiosError, params: TParams, options: Options) \=> any;

> NOTE: you can use all the configs of axios.

// options with same key will be covered.
const {createInterface} \= createFactory(options);
const getUsers \= createInterface(method, urlTemplate, options);
const result \= getUsers(params);

### Lifecycle about onPending, onResolve, onReject

when call => onPending => transformRequest(axios) => Browsers => transformResponse(axios) => onResolve | onReject => return

### Custom Options

you can inject anything into options. In `onPending, onResolve, onReject`, options will be sent back, then you can do the logic with options and your custom onex.

### Options lifecycle that take effects

-   These options take effect only in `createFactory`
    
    -   interpolate，可以修改 urlTemplate 解析
-   These options take effect in `createFactory` and `createInterface`, not in `request`
    
    -   encodePathVariable
-   These options take effect in `createFactory`, `createInterface` and `request`
    
    -   onPending, onResolve, onReject, transformDeleteParamsIntoBody

Docs
----

Best Practice

FAQ
