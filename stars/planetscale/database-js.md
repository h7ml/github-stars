---
project: database-js
stars: 1180
description: A Fetch API-compatible PlanetScale database driver
url: https://github.com/planetscale/database-js
---

PlanetScale serverless JavaScript driver for Vitess/MySQL
=========================================================

A Fetch API-compatible PlanetScale Vitess/MySQL database driver for serverless and edge compute platforms that require HTTP external connections, such as Cloudflare Workers or Vercel Edge Functions

Installation
------------

npm install @planetscale/database

Usage
-----

import { connect } from '@planetscale/database'

const config \= {
  host: '<host>',
  username: '<user>',
  password: '<password>'
}

const conn \= connect(config)
const results \= await conn.execute('select 1 from dual where 1=?', \[1\])
console.log(results)

### Database URL

A single database URL value can be used to configure the `host`, `username`, and `password` values.

import { connect } from '@planetscale/database'

const config \= {
  url: process.env\['DATABASE\_URL'\] || 'mysql://user:pass@host'
}

const conn \= connect(config)

### Connection factory

Use the `Client` connection factory class to create fresh connections for each transaction or web request handler.

import { Client } from '@planetscale/database'

const client \= new Client({
  host: '<host>',
  username: '<user>',
  password: '<password>'
})

const conn \= client.connection()
const results \= await conn.execute('select 1 from dual')
console.log(results)

### Transactions

Use the `transaction` function to safely perform database transactions. If any unhandled errors are thrown during execution of the transaction, the transaction will be rolled back.

The following example is based on the Slotted Counter Pattern.

import { connect } from '@planetscale/database'

const config \= {
  host: '<host>',
  username: '<user>',
  password: '<password>'
}

const conn \= connect(config)
const results \= await conn.transaction(async (tx) \=> {
  const whenBranch \= await tx.execute('INSERT INTO branches (database\_id, name) VALUES (?, ?)', \[42, "planetscale"\])
  const whenCounter \= await tx.execute('INSERT INTO slotted\_counters(record\_type, record\_id, slot, count) VALUES (?, ?, RAND() \* 100, 1) ON DUPLICATE KEY UPDATE count = count + 1', \['branch\_count', 42\])
  return \[whenBranch, whenCounter\]
})
console.log(results)

### Custom fetch function

Node.js version 18 includes a built-in global `fetch` function. When using an older version of Node.js, you can provide a custom fetch function implementation. We recommend the `undici` package on which Node's built-in fetch is based.

import { connect } from '@planetscale/database'
import { fetch } from 'undici'

const config \= {
  fetch,
  host: '<host>',
  username: '<user>',
  password: '<password>'
}

const conn \= connect(config)
const results \= await conn.execute('select 1 from dual')
console.log(results)

To leverage HTTP/2, you can use the `fetch-h2` shim. `fetch-h2` also supports Node.js 12+.

import { connect } from '@planetscale/database'
import { context } from 'fetch-h2'
const { fetch, disconnectAll } \= context()

const config \= {
  fetch,
  host: '<host>',
  username: '<user>',
  password: '<password>'
}

const conn \= connect(config)
const results \= await conn.execute('select 1 from dual')
console.log(results)
await disconnectAll()

### Custom query parameter format function

Query replacement parameters identified with `?` are replaced with escaped values. Named replacement parameters are supported with a colon prefix.

const results1 \= await conn.execute('select 1 from dual where 1=?', \[42\])
const results2 \= await conn.execute('select 1 from dual where 1=:id', { id: 42 })

Providing a custom format function overrides the built-in escaping with an external library, like `sqlstring`.

import { connect } from '@planetscale/database'
import SqlString from 'sqlstring'

const config \= {
  format: SqlString.format,
  host: '<host>',
  username: '<user>',
  password: '<password>'
}

const conn \= connect(config)
const results \= await conn.execute('select 1 from dual where 1=?', \[42\])
console.log(results)

### Custom type casting function

Column values are converted to their corresponding JavaScript data types. This can be customized by providing a `cast` function.

import { connect, cast } from '@planetscale/database'

function inflate(field, value) {
  if (field.type \=== 'INT64' || field.type \=== 'UINT64') {
    return BigInt(value)
  }
  return cast(field, value)
}

const config \= {
  cast: inflate,
  host: '<host>',
  username: '<user>',
  password: '<password>'
}

const conn \= connect(config)

You can also pass a custom `cast` function to `execute`. If present, this will override the `cast` function set by the connection:

const result \= await conn.execute(
  'SELECT userId, SUM(balance) AS balance FROM UserBalanceItem GROUP BY userId',
  {},
  {
    cast: (field, value) \=> {
      if (field.name \=== 'balance') {
        return BigInt(value)
      }
      return cast(field, value)
    }
  }
)

### Row return values

Rows can be returned as an object or an array of column values by passing an `as` option to `execute`.

const query \= 'select 1 as one, 2 as two where 1=?'
const objects \= conn.execute(query, \[1\], { as: 'object' })
// objects.rows => \[{one: '1', two: '2'}\]

const arrays \= conn.execute(query, \[1\], { as: 'array' })
// arrays.rows => \[\['1', '2'\]\]

Development
-----------

npm install
npm test

Need help?
----------

Get help from the PlanetScale support team, or join our community on Discord or GitHub discussion board to see how others are using PlanetScale.

License
-------

Distributed under the Apache 2.0 license. See LICENSE for details.
