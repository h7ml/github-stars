---
project: koa-router
stars: 4837
description: Router middleware for koa.
url: https://github.com/ZijianHe/koa-router
---

koa-router
==========

> Router middleware for koa

-   Express-style routing using `app.get`, `app.put`, `app.post`, etc.
-   Named URL parameters.
-   Named routes with URL generation.
-   Responds to `OPTIONS` requests with allowed methods.
-   Support for `405 Method Not Allowed` and `501 Not Implemented`.
-   Multiple route middleware.
-   Multiple routers.
-   Nestable routers.
-   ES7 async/await support.

Migrating to 7 / Koa 2
----------------------

-   The API has changed to match the new promise-based middleware signature of koa 2. See the koa 2.x readme for more information.
-   Middleware is now always run in the order declared by `.use()` (or `.get()`, etc.), which matches Express 4 API.

Installation
------------

Install using npm:

npm install koa-router

API Reference
-------------

-   koa-router
    -   Router ⏏
        -   new Router(\[opts\])
        -   _instance_
            -   .get|put|post|patch|delete|del ⇒ `Router`
            -   .routes ⇒ `function`
            -   .use(\[path\], middleware) ⇒ `Router`
            -   .prefix(prefix) ⇒ `Router`
            -   .allowedMethods(\[options\]) ⇒ `function`
            -   .redirect(source, destination, \[code\]) ⇒ `Router`
            -   .route(name) ⇒ `Layer` | `false`
            -   .url(name, params, \[options\]) ⇒ `String` | `Error`
            -   .param(param, middleware) ⇒ `Router`
        -   _static_
            -   .url(path, params) ⇒ `String`

### Router ⏏

**Kind**: Exported class  

#### new Router(\[opts\])

Create a new router.

Param

Type

Description

\[opts\]

`Object`

\[opts.prefix\]

`String`

prefix router paths

**Example**  
Basic usage:

var Koa \= require('koa');
var Router \= require('koa-router');

var app \= new Koa();
var router \= new Router();

router.get('/', (ctx, next) \=> {
  // ctx.router available
});

app
  .use(router.routes())
  .use(router.allowedMethods());

#### router.get|put|post|patch|delete|del ⇒ `Router`

Create `router.verb()` methods, where _verb_ is one of the HTTP verbs such as `router.get()` or `router.post()`.

Match URL patterns to callback functions or controller actions using `router.verb()`, where **verb** is one of the HTTP verbs such as `router.get()` or `router.post()`.

Additionaly, `router.all()` can be used to match against all methods.

router
  .get('/', (ctx, next) \=> {
    ctx.body \= 'Hello World!';
  })
  .post('/users', (ctx, next) \=> {
    // ...
  })
  .put('/users/:id', (ctx, next) \=> {
    // ...
  })
  .del('/users/:id', (ctx, next) \=> {
    // ...
  })
  .all('/users/:id', (ctx, next) \=> {
    // ...
  });

When a route is matched, its path is available at `ctx._matchedRoute` and if named, the name is available at `ctx._matchedRouteName`

Route paths will be translated to regular expressions using path-to-regexp.

Query strings will not be considered when matching requests.

#### Named routes

Routes can optionally have names. This allows generation of URLs and easy renaming of URLs during development.

router.get('user', '/users/:id', (ctx, next) \=> {
 // ...
});

router.url('user', 3);
// => "/users/3"

#### Multiple middleware

Multiple middleware may be given:

router.get(
  '/users/:id',
  (ctx, next) \=> {
    return User.findOne(ctx.params.id).then(function(user) {
      ctx.user \= user;
      next();
    });
  },
  ctx \=> {
    console.log(ctx.user);
    // => { id: 17, name: "Alex" }
  }
);

### Nested routers

Nesting routers is supported:

var forums \= new Router();
var posts \= new Router();

posts.get('/', (ctx, next) \=> {...});
posts.get('/:pid', (ctx, next) \=> {...});
forums.use('/forums/:fid/posts', posts.routes(), posts.allowedMethods());

// responds to "/forums/123/posts" and "/forums/123/posts/123"
app.use(forums.routes());

#### Router prefixes

Route paths can be prefixed at the router level:

var router \= new Router({
  prefix: '/users'
});

router.get('/', ...); // responds to "/users"
router.get('/:id', ...); // responds to "/users/:id"

#### URL parameters

Named route parameters are captured and added to `ctx.params`.

router.get('/:category/:title', (ctx, next) \=> {
  console.log(ctx.params);
  // => { category: 'programming', title: 'how-to-node' }
});

The path-to-regexp module is used to convert paths to regular expressions.

**Kind**: instance property of `Router`

Param

Type

Description

path

`String`

\[middleware\]

`function`

route middleware(s)

callback

`function`

route callback

#### router.routes ⇒ `function`

Returns router middleware which dispatches a route matching the request.

**Kind**: instance property of `Router`  

#### router.use(\[path\], middleware) ⇒ `Router`

Use given middleware.

Middleware run in the order they are defined by `.use()`. They are invoked sequentially, requests start at the first middleware and work their way "down" the middleware stack.

**Kind**: instance method of `Router`

Param

Type

\[path\]

`String`

middleware

`function`

\[...\]

`function`

**Example**

// session middleware will run before authorize
router
  .use(session())
  .use(authorize());

// use middleware only with given path
router.use('/users', userAuth());

// or with an array of paths
router.use(\['/users', '/admin'\], userAuth());

app.use(router.routes());

#### router.prefix(prefix) ⇒ `Router`

Set the path prefix for a Router instance that was already initialized.

**Kind**: instance method of `Router`

Param

Type

prefix

`String`

**Example**

router.prefix('/things/:thing\_id')

#### router.allowedMethods(\[options\]) ⇒ `function`

Returns separate middleware for responding to `OPTIONS` requests with an `Allow` header containing the allowed methods, as well as responding with `405 Method Not Allowed` and `501 Not Implemented` as appropriate.

**Kind**: instance method of `Router`

Param

Type

Description

\[options\]

`Object`

\[options.throw\]

`Boolean`

throw error instead of setting status and header

\[options.notImplemented\]

`function`

throw the returned value in place of the default NotImplemented error

\[options.methodNotAllowed\]

`function`

throw the returned value in place of the default MethodNotAllowed error

**Example**

var Koa \= require('koa');
var Router \= require('koa-router');

var app \= new Koa();
var router \= new Router();

app.use(router.routes());
app.use(router.allowedMethods());

**Example with Boom**

var Koa \= require('koa');
var Router \= require('koa-router');
var Boom \= require('boom');

var app \= new Koa();
var router \= new Router();

app.use(router.routes());
app.use(router.allowedMethods({
  throw: true,
  notImplemented: () \=> new Boom.notImplemented(),
  methodNotAllowed: () \=> new Boom.methodNotAllowed()
}));

#### router.redirect(source, destination, \[code\]) ⇒ `Router`

Redirect `source` to `destination` URL with optional 30x status `code`.

Both `source` and `destination` can be route names.

router.redirect('/login', 'sign-in');

This is equivalent to:

router.all('/login', ctx \=> {
  ctx.redirect('/sign-in');
  ctx.status \= 301;
});

**Kind**: instance method of `Router`

Param

Type

Description

source

`String`

URL or route name.

destination

`String`

URL or route name.

\[code\]

`Number`

HTTP status code (default: 301).

#### router.route(name) ⇒ `Layer` | `false`

Lookup route with given `name`.

**Kind**: instance method of `Router`

Param

Type

name

`String`

#### router.url(name, params, \[options\]) ⇒ `String` | `Error`

Generate URL for route. Takes a route name and map of named `params`.

**Kind**: instance method of `Router`

Param

Type

Description

name

`String`

route name

params

`Object`

url parameters

\[options\]

`Object`

options parameter

\[options.query\]

`Object` | `String`

query options

**Example**

router.get('user', '/users/:id', (ctx, next) \=> {
  // ...
});

router.url('user', 3);
// => "/users/3"

router.url('user', { id: 3 });
// => "/users/3"

router.use((ctx, next) \=> {
  // redirect to named route
  ctx.redirect(ctx.router.url('sign-in'));
})

router.url('user', { id: 3 }, { query: { limit: 1 } });
// => "/users/3?limit=1"

router.url('user', { id: 3 }, { query: "limit=1" });
// => "/users/3?limit=1"

#### router.param(param, middleware) ⇒ `Router`

Run middleware for named route parameters. Useful for auto-loading or validation.

**Kind**: instance method of `Router`

Param

Type

param

`String`

middleware

`function`

**Example**

router
  .param('user', (id, ctx, next) \=> {
    ctx.user \= users\[id\];
    if (!ctx.user) return ctx.status \= 404;
    return next();
  })
  .get('/users/:user', ctx \=> {
    ctx.body \= ctx.user;
  })
  .get('/users/:user/friends', ctx \=> {
    return ctx.user.getFriends().then(function(friends) {
      ctx.body \= friends;
    });
  })
  // /users/3 => {"id": 3, "name": "Alex"}
  // /users/3/friends => \[{"id": 4, "name": "TJ"}\]

#### Router.url(path, params \[, options\]) ⇒ `String`

Generate URL from url pattern and given `params`.

**Kind**: static method of `Router`

Param

Type

Description

path

`String`

url pattern

params

`Object`

url parameters

\[options\]

`Object`

options parameter

\[options.query\]

`Object` | `String`

query options

**Example**

var url \= Router.url('/users/:id', {id: 1});
// => "/users/1"

const url \= Router.url('/users/:id', {id: 1}, {query: { active: true }});
// => "/users/1?active=true"

Contributing
------------

Please submit all issues and pull requests to the alexmingoia/koa-router repository!

Tests
-----

Run tests using `npm test`.

Support
-------

If you have any problem or suggestion please open an issue here.
