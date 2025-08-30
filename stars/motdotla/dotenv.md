---
project: dotenv
stars: 19990
description: Loads environment variables from .env for nodejs projects.
url: https://github.com/motdotla/dotenv
---

🎉 announcing dotenvx. _run anywhere, multi-environment, encrypted envs_.

dotenv
======

Dotenv is a zero-dependency module that loads environment variables from a `.env` file into `process.env`. Storing configuration in the environment separate from code is based on The Twelve-Factor App methodology.

-   🌱 Install
-   🏗️ Usage (.env)
-   🌴 Multiple Environments 🆕
-   🚀 Deploying (encryption) 🆕
-   📚 Examples
-   📖 Docs
-   ❓ FAQ
-   ⏱️ Changelog

🌱 Install
----------

npm install dotenv --save

You can also use an npm-compatible package manager like yarn, bun or pnpm:

yarn add dotenv

bun add dotenv

pnpm add dotenv

🏗️ Usage
---------

Create a `.env` file in the root of your project (if using a monorepo structure like `apps/backend/app.js`, put it in the root of the folder where your `app.js` process runs):

S3\_BUCKET\="YOURS3BUCKET"
SECRET\_KEY\="YOURSECRETKEYGOESHERE"

As early as possible in your application, import and configure dotenv:

require('dotenv').config()
console.log(process.env) // remove this after you've confirmed it is working

.. or using ES6?

import 'dotenv/config'

ES6 import if you need to set config options:

import dotenv from 'dotenv'

dotenv.config({ path: '/custom/path/to/.env' })

That's it. `process.env` now has the keys and values you defined in your `.env` file:

require('dotenv').config()
// or import 'dotenv/config' if you're using ES6

...

s3.getBucketCors({Bucket: process.env.S3\_BUCKET}, function(err, data) {})

### Multiline values

If you need multiline variables, for example private keys, those are now supported (`>= v15.0.0`) with line breaks:

PRIVATE\_KEY\="\-----BEGIN RSA PRIVATE KEY-----
...
Kh9NV...
...
\-----END RSA PRIVATE KEY-----"

Alternatively, you can double quote strings and use the `\n` character:

PRIVATE\_KEY\="\-----BEGIN RSA PRIVATE KEY-----\\nKh9NV...\\n-----END RSA PRIVATE KEY-----\\n"

### Comments

Comments may be added to your file on their own line or inline:

# This is a comment
SECRET\_KEY\=YOURSECRETKEYGOESHERE # comment
SECRET\_HASH\="something-with-a-#-hash"

Comments begin where a `#` exists, so if your value contains a `#` please wrap it in quotes. This is a breaking change from `>= v15.0.0` and on.

### Parsing

The engine which parses the contents of your file containing environment variables is available to use. It accepts a String or Buffer and will return an Object with the parsed keys and values.

const dotenv \= require('dotenv')
const buf \= Buffer.from('BASIC=basic')
const config \= dotenv.parse(buf) // will return an object
console.log(typeof config, config) // object { BASIC : 'basic' }

### Preload

> Note: Consider using `dotenvx` instead of preloading. I am now doing (and recommending) so.
> 
> It serves the same purpose (you do not need to require and load dotenv), adds better debugging, and works with ANY language, framework, or platform. – motdotla

You can use the `--require` (`-r`) command line option to preload dotenv. By doing this, you do not need to require and load dotenv in your application code.

$ node -r dotenv/config your\_script.js

The configuration options below are supported as command line arguments in the format `dotenv_config_<option>=value`

$ node -r dotenv/config your\_script.js dotenv\_config\_path=/custom/path/to/.env dotenv\_config\_debug=true

Additionally, you can use environment variables to set configuration options. Command line arguments will precede these.

$ DOTENV\_CONFIG\_<OPTION\>\=value node -r dotenv/config your\_script.js

$ DOTENV\_CONFIG\_ENCODING=latin1 DOTENV\_CONFIG\_DEBUG=true node -r dotenv/config your\_script.js dotenv\_config\_path=/custom/path/to/.env

### Variable Expansion

Use dotenvx to use variable expansion.

Reference and expand variables already on your machine for use in your .env file.

# .env
USERNAME\="username"
DATABASE\_URL\="postgres://${USERNAME}@localhost/my\_database"

// index.js
console.log('DATABASE\_URL', process.env.DATABASE\_URL)

$ dotenvx run --debug -- node index.js
\[dotenvx@0.14.1\] injecting env (2) from .env
DATABASE\_URL postgres://username@localhost/my\_database

### Command Substitution

Use dotenvx to use command substitution.

Add the output of a command to one of your variables in your .env file.

# .env
DATABASE\_URL\="postgres://$(whoami)@localhost/my\_database"

// index.js
console.log('DATABASE\_URL', process.env.DATABASE\_URL)

$ dotenvx run --debug -- node index.js
\[dotenvx@0.14.1\] injecting env (1) from .env
DATABASE\_URL postgres://yourusername@localhost/my\_database

### Syncing

You need to keep `.env` files in sync between machines, environments, or team members? Use dotenvx to encrypt your `.env` files and safely include them in source control. This still subscribes to the twelve-factor app rules by generating a decryption key separate from code.

### Multiple Environments

Use dotenvx to generate `.env.ci`, `.env.production` files, and more.

### Deploying

You need to deploy your secrets in a cloud-agnostic manner? Use dotenvx to generate a private decryption key that is set on your production server.

🌴 Manage Multiple Environments
-------------------------------

Use dotenvx

Run any environment locally. Create a `.env.ENVIRONMENT` file and use `--env-file` to load it. It's straightforward, yet flexible.

$ echo "HELLO=production" \> .env.production
$ echo "console.log('Hello ' + process.env.HELLO)" \> index.js

$ dotenvx run --env-file=.env.production -- node index.js
Hello production
\> ^^

or with multiple .env files

$ echo "HELLO=local" \> .env.local
$ echo "HELLO=World" \> .env
$ echo "console.log('Hello ' + process.env.HELLO)" \> index.js

$ dotenvx run --env-file=.env.local --env-file=.env -- node index.js
Hello local

more environment examples

🚀 Deploying
------------

Use dotenvx.

Add encryption to your `.env` files with a single command. Pass the `--encrypt` flag.

```
$ dotenvx set HELLO Production --encrypt -f .env.production
$ echo "console.log('Hello ' + process.env.HELLO)" > index.js

$ DOTENV_PRIVATE_KEY_PRODUCTION="<.env.production private key>" dotenvx run -- node index.js
[dotenvx] injecting env (2) from .env.production
Hello Production
```

learn more

📚 Examples
-----------

See examples of using dotenv with various frameworks, languages, and configurations.

-   nodejs
-   nodejs (debug on)
-   nodejs (override on)
-   nodejs (processEnv override)
-   esm
-   esm (preload)
-   typescript
-   typescript parse
-   typescript config
-   webpack
-   webpack (plugin)
-   react
-   react (typescript)
-   express
-   nestjs
-   fastify

📖 Documentation
----------------

Dotenv exposes four functions:

-   `config`
-   `parse`
-   `populate`

### Config

`config` will read your `.env` file, parse the contents, assign it to `process.env`, and return an Object with a `parsed` key containing the loaded content or an `error` key if it failed.

const result \= dotenv.config()

if (result.error) {
  throw result.error
}

console.log(result.parsed)

You can additionally, pass options to `config`.

#### Options

##### path

Default: `path.resolve(process.cwd(), '.env')`

Specify a custom path if your file containing environment variables is located elsewhere.

require('dotenv').config({ path: '/custom/path/to/.env' })

By default, `config` will look for a file called .env in the current working directory.

Pass in multiple files as an array, and they will be parsed in order and combined with `process.env` (or `option.processEnv`, if set). The first value set for a variable will win, unless the `options.override` flag is set, in which case the last value set will win. If a value already exists in `process.env` and the `options.override` flag is NOT set, no changes will be made to that value.

require('dotenv').config({ path: \['.env.local', '.env'\] })

##### quiet

Default: `false`

Suppress runtime logging message.

// index.js
require('dotenv').config({ quiet: false }) // change to true to suppress
console.log(\`Hello ${process.env.HELLO}\`)

# .env
.env

$ node index.js
\[dotenv@17.0.0\] injecting env (1) from .env
Hello World

##### encoding

Default: `utf8`

Specify the encoding of your file containing environment variables.

require('dotenv').config({ encoding: 'latin1' })

##### debug

Default: `false`

Turn on logging to help debug why certain keys or values are not being set as you expect.

require('dotenv').config({ debug: process.env.DEBUG })

##### override

Default: `false`

Override any environment variables that have already been set on your machine with values from your .env file(s). If multiple files have been provided in `option.path` the override will also be used as each file is combined with the next. Without `override` being set, the first value wins. With `override` set the last value wins.

require('dotenv').config({ override: true })

##### processEnv

Default: `process.env`

Specify an object to write your environment variables to. Defaults to `process.env` environment variables.

const myObject \= {}
require('dotenv').config({ processEnv: myObject })

console.log(myObject) // values from .env
console.log(process.env) // this was not changed or written to

### Parse

The engine which parses the contents of your file containing environment variables is available to use. It accepts a String or Buffer and will return an Object with the parsed keys and values.

const dotenv \= require('dotenv')
const buf \= Buffer.from('BASIC=basic')
const config \= dotenv.parse(buf) // will return an object
console.log(typeof config, config) // object { BASIC : 'basic' }

#### Options

##### debug

Default: `false`

Turn on logging to help debug why certain keys or values are not being set as you expect.

const dotenv \= require('dotenv')
const buf \= Buffer.from('hello world')
const opt \= { debug: true }
const config \= dotenv.parse(buf, opt)
// expect a debug message because the buffer is not in KEY=VAL form

### Populate

The engine which populates the contents of your .env file to `process.env` is available for use. It accepts a target, a source, and options. This is useful for power users who want to supply their own objects.

For example, customizing the source:

const dotenv \= require('dotenv')
const parsed \= { HELLO: 'world' }

dotenv.populate(process.env, parsed)

console.log(process.env.HELLO) // world

For example, customizing the source AND target:

const dotenv \= require('dotenv')
const parsed \= { HELLO: 'universe' }
const target \= { HELLO: 'world' } // empty object

dotenv.populate(target, parsed, { override: true, debug: true })

console.log(target) // { HELLO: 'universe' }

#### options

##### Debug

Default: `false`

Turn on logging to help debug why certain keys or values are not being populated as you expect.

##### override

Default: `false`

Override any environment variables that have already been set.

❓ FAQ
-----

### Why is the `.env` file not loading my environment variables successfully?

Most likely your `.env` file is not in the correct place. See this stack overflow.

Turn on debug mode and try again..

require('dotenv').config({ debug: true })

You will receive a helpful error outputted to your console.

### Should I commit my `.env` file?

No. We **strongly** recommend against committing your `.env` file to version control. It should only include environment-specific values such as database passwords or API keys. Your production database should have a different password than your development database.

### Should I have multiple `.env` files?

We recommend creating one `.env` file per environment. Use `.env` for local/development, `.env.production` for production and so on. This still follows the twelve factor principles as each is attributed individually to its own environment. Avoid custom set ups that work in inheritance somehow (`.env.production` inherits values form `.env` for example). It is better to duplicate values if necessary across each `.env.environment` file.

> In a twelve-factor app, env vars are granular controls, each fully orthogonal to other env vars. They are never grouped together as “environments”, but instead are independently managed for each deploy. This is a model that scales up smoothly as the app naturally expands into more deploys over its lifetime.
> 
> – The Twelve-Factor App

### What rules does the parsing engine follow?

The parsing engine currently supports the following rules:

-   `BASIC=basic` becomes `{BASIC: 'basic'}`
-   empty lines are skipped
-   lines beginning with `#` are treated as comments
-   `#` marks the beginning of a comment (unless when the value is wrapped in quotes)
-   empty values become empty strings (`EMPTY=` becomes `{EMPTY: ''}`)
-   inner quotes are maintained (think JSON) (`JSON={"foo": "bar"}` becomes `{JSON:"{\"foo\": \"bar\"}"`)
-   whitespace is removed from both ends of unquoted values (see more on `trim`) (`FOO= some value` becomes `{FOO: 'some value'}`)
-   single and double quoted values are escaped (`SINGLE_QUOTE='quoted'` becomes `{SINGLE_QUOTE: "quoted"}`)
-   single and double quoted values maintain whitespace from both ends (`FOO=" some value "` becomes `{FOO: ' some value '}`)
-   double quoted values expand new lines (`MULTILINE="new\nline"` becomes

```
{MULTILINE: 'new
line'}
```

-   backticks are supported (`` BACKTICK_KEY=`This has 'single' and "double" quotes inside of it.` ``)

### What happens to environment variables that were already set?

By default, we will never modify any environment variables that have already been set. In particular, if there is a variable in your `.env` file which collides with one that already exists in your environment, then that variable will be skipped.

If instead, you want to override `process.env` use the `override` option.

require('dotenv').config({ override: true })

### How come my environment variables are not showing up for React?

Your React code is run in Webpack, where the `fs` module or even the `process` global itself are not accessible out-of-the-box. `process.env` can only be injected through Webpack configuration.

If you are using `react-scripts`, which is distributed through `create-react-app`, it has dotenv built in but with a quirk. Preface your environment variables with `REACT_APP_`. See this stack overflow for more details.

If you are using other frameworks (e.g. Next.js, Gatsby...), you need to consult their documentation for how to inject environment variables into the client.

### Can I customize/write plugins for dotenv?

Yes! `dotenv.config()` returns an object representing the parsed `.env` file. This gives you everything you need to continue setting values on `process.env`. For example:

const dotenv \= require('dotenv')
const variableExpansion \= require('dotenv-expand')
const myEnv \= dotenv.config()
variableExpansion(myEnv)

### How do I use dotenv with `import`?

Simply..

// index.mjs (ESM)
import 'dotenv/config' // see https://github.com/motdotla/dotenv#how-do-i-use-dotenv-with-import
import express from 'express'

A little background..

> When you run a module containing an `import` declaration, the modules it imports are loaded first, then each module body is executed in a depth-first traversal of the dependency graph, avoiding cycles by skipping anything already executed.
> 
> – ES6 In Depth: Modules

What does this mean in plain language? It means you would think the following would work but it won't.

`errorReporter.mjs`:

class Client {
  constructor (apiKey) {
    console.log('apiKey', apiKey)

    this.apiKey \= apiKey
  }
}

export default new Client(process.env.API\_KEY)

`index.mjs`:

// Note: this is INCORRECT and will not work
import \* as dotenv from 'dotenv'
dotenv.config()

import errorReporter from './errorReporter.mjs' // process.env.API\_KEY will be blank!

`process.env.API_KEY` will be blank.

Instead, `index.mjs` should be written as..

import 'dotenv/config'

import errorReporter from './errorReporter.mjs'

Does that make sense? It's a bit unintuitive, but it is how importing of ES6 modules work. Here is a working example of this pitfall.

There are two alternatives to this approach:

1.  Preload with dotenvx: `dotenvx run -- node index.js` (_Note: you do not need to `import` dotenv with this approach_)
2.  Create a separate file that will execute `config` first as outlined in this comment on #133

### Why am I getting the error `Module not found: Error: Can't resolve 'crypto|os|path'`?

You are using dotenv on the front-end and have not included a polyfill. Webpack < 5 used to include these for you. Do the following:

npm install node-polyfill-webpack-plugin

Configure your `webpack.config.js` to something like the following.

require('dotenv').config()

const path \= require('path');
const webpack \= require('webpack')

const NodePolyfillPlugin \= require('node-polyfill-webpack-plugin')

module.exports \= {
  mode: 'development',
  entry: './src/index.ts',
  output: {
    filename: 'bundle.js',
    path: path.resolve(\_\_dirname, 'dist'),
  },
  plugins: \[
    new NodePolyfillPlugin(),
    new webpack.DefinePlugin({
      'process.env': {
        HELLO: JSON.stringify(process.env.HELLO)
      }
    }),
  \]
};

Alternatively, just use dotenv-webpack which does this and more behind the scenes for you.

### What about variable expansion?

Try dotenv-expand

### What about syncing and securing .env files?

Use dotenvx to unlock syncing encrypted .env files over git.

### What if I accidentally commit my `.env` file to code?

Remove it, remove git history and then install the git pre-commit hook to prevent this from ever happening again.

```
brew install dotenvx/brew/dotenvx
dotenvx precommit --install
```

### How can I prevent committing my `.env` file to a Docker build?

Use the docker prebuild hook.

# Dockerfile
...
RUN curl -fsS https://dotenvx.sh/ | sh
...
RUN dotenvx prebuild
CMD \["dotenvx", "run", "\--", "node", "index.js"\]

Contributing Guide
------------------

See CONTRIBUTING.md

CHANGELOG
---------

See CHANGELOG.md

Who's using dotenv?
-------------------

These npm modules depend on it.

Projects that expand it often use the keyword "dotenv" on npm.
