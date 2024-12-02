---
project: rxdb
stars: 21671
description: A fast, local first, reactive Database for JavaScript Applications https://rxdb.info/
url: https://github.com/pubkey/rxdb
---

  

  
  

### A fast, local-first, reactive Database for JavaScript Applications

       

     

  

  What is RxDB?
---------------

RxDB (short for **R**eactive **D**ata**b**ase) is a local-first, NoSQL-database for JavaScript Applications like Websites, hybrid Apps, Electron-Apps, Progressive Web Apps, Deno and Node.js. Reactive means that you can not only query the current state, but **subscribe** to all state changes like the result of a query or even a single field of a document. This is great for UI-based **realtime** applications in a way that makes it easy to develop and also has great performance benefits but can also be used to create fast backends in Node.js.  
RxDB provides an easy to implement protocol for realtime **replication** with your existing infrastructure or one of the plugins for HTTP, GraphQL, CouchDB, Websocket, WebRTC, Supabase, Firestore, NATS.  
RxDB is based on a storage interface that enables you to swap out the underlying storage engine. This increases **code reuse** because you can use the same database code for different JavaScript environments by just switching out the storage settings.

Use the quickstart, read the documentation or explore the example projects.

  Multiplayer realtime applications
-----------------------------------

  Replicate with your **existing infrastructure**
-------------------------------------------------

RxDB provides an easy to implement, **battle-tested** replication protocol for realtime sync with your existing infrastructure.  
There are also plugins to easily replicate with GraphQL, CouchDB, Websocket, WebRTC,Supabase, Firestore or NATS.

  **Flexible** storage layer
----------------------------

RxDB is based on a storage interface that enables you to swap out the underlying storage engine. This increases **code reuse** because the same database code can be used in different JavaScript environments by just switching out the storage settings.

You can use RxDB on top of IndexedDB, OPFS, LokiJS, Dexie.js, in-memory, SQLite, in a WebWorker thread and even on top of FoundationDB and DenoKV.

No matter what kind of runtime you have, as long as it runs JavaScript, it can run RxDB:

#### Browsers Node.js React Native Capacitor NativeScript Flutter or as an Electron Database

  Quick start
-------------

#### Install

npm install rxdb rxjs --save

#### Store data

import { 
  createRxDatabase
} from 'rxdb/plugins/core';

/\*\*
 \* For browsers, we use the dexie.js based storage
 \* which stores data in IndexedDB in the browser.
 \* In other JavaScript runtimes, we can use different storages:
 \* @link https://rxdb.info/rx-storage.html
 \*/
import { getRxStorageDexie } from 'rxdb/plugins/storage-dexie';

// create a database
const db \= await createRxDatabase({
    name: 'heroesdb', // the name of the database
    storage: getRxStorageDexie()
});

// add collections
await db.addCollections({
  heroes: {
    schema: mySchema
  }
});

// insert a document
await db.heroes.insert({
  name: 'Bob',
  healthpoints: 100
});

#### Query data once

const aliveHeroes \= await db.heroes.find({
  selector: {
    healthpoints: {
      $gt: 0
    }
  }
}).exec(); // the exec() returns the result once

#### Observe a Query

await db.heroes.find({
  selector: {
    healthpoints: {
      $gt: 0
    }
  }
})
.$ // the $ returns an observable that emits each time the result set of the query changes
.subscribe(aliveHeroes \=> console.dir(aliveHeroes));

Continue with the quickstart here.

  More Features (click to toggle)
---------------------------------

**Subscribe to events, query results, documents and event single fields of a document**

RxDB implements rxjs to make your data reactive. This makes it easy to always show the real-time database-state in the dom without manually re-submitting your queries. You can also add custom reactiveness libraries like signals or other state management.

db.heroes
  .find()
  .sort('name')
  .$ // <- returns observable of query
  .subscribe( docs \=> {
    myDomElement.innerHTML \= docs
      .map(doc \=> '<li>' + doc.name + '</li>')
      .join();
  });

**MultiWindow/Tab**

RxDB supports multi tab/window usage out of the box. When data is changed at one browser tab/window or Node.js process, the change will automatically be broadcasted to all other tabs so that they can update the UI properly.

**EventReduce**

One big benefit of having a realtime database is that big performance optimizations can be done when the database knows a query is observed and the updated results are needed continuously. RxDB internally uses the Event-Reduce algorithm. This makes sure that when you update/insert/remove documents, the query does not have to re-run over the whole database but the new results will be calculated from the events. This creates a huge performance-gain with zero cost.

### Use-Case-Example

Imagine you have a very big collection with many user-documents. At your page you want to display a toplist with users which have the most `points` and are currently logged in. You create a query and subscribe to it.

const query \= usersCollection.find().where('loggedIn').eq(true).sort('points');
query.$.subscribe(users \=> {
    document.querySelector('body').innerHTML \= users
        .reduce((prev, cur) \=> prev + cur.username+ '<br/>', '');
});

As you may detect, the query can take very long time to run, because you have thousands of users in the collection. When a user now logs off, the whole query will re-run over the database which takes again very long.

await anyUser.incrementalPatch({loggedIn: false});

But not with the EventReduce. Now, when one user logs off, it will calculate the new results from the current results plus the RxChangeEvent. This often can be done in-memory without making IO-requests to the storage-engine. EventReduce not only works on subscribed queries, but also when you do multiple `.exec()`'s on the same query.

**Schema**

Schemas are defined via jsonschema and are used to describe your data.

const mySchema \= {
    title: "hero schema",
    version: 0,                 // <- incremental version-number
    description: "describes a simple hero",
    primaryKey: 'name',         // <- 'name' is the primary key for the collection, it must be unique, required and of the type string 
    type: "object",
    properties: {
        name: {
            type: "string",
            maxLength: 30
        },
        secret: {
            type: "string",
        },
        skills: {
            type: "array",
            maxItems: 5,
            uniqueItems: true,
            item: {
                type: "object",
                properties: {
                    name: {
                        type: "string"
                    },
                    damage: {
                        type: "number"
                    }
                }
            }
        }
    },
    required: \["color"\],
    encrypted: \["secret"\] // <- this means that the value of this field is stored encrypted
};

**Mango / Chained queries**

RxDB can be queried by standard NoSQL mango queries like you maybe know from other NoSQL Databases like **mongoDB**.

Also you can use the query-builder plugin to create chained mango-queries.

// normal query
myCollection.find({
  selector: {
    name: {
      $ne: 'Alice'
    },
    age: {
      $gt: 67
    }
  },
  sort: \[{ age: 'desc' }\],
  limit: 10
})

// chained query
myCollection
  .find()
  .where('name').ne('Alice')
  .where('age').gt(18).lt(67)
  .limit(10)
  .sort('-age')
  .exec().then( docs \=> {
    console.dir(docs);
  });

**Encryption**

By setting a schema-field to `encrypted`, the value of this field will be stored in encryption-mode and can't be read without the password. Of course you can also encrypt nested objects. Example:

{
  "title": "my schema",
  "properties": {
    "secret": {
      "type": "string",
      "encrypted": true
    }
  },
  "encrypted": \[
    "secret"
  \]
}

**Import / Export**

RxDB lets you import and export the whole database or single collections into json-objects. This is helpful to trace bugs in your application or to move to a given state in your tests.

// export a single collection
const jsonCol \= await myCollection.dump();

// export the whole database
const jsonDB \= await myDatabase.dump();

// import the dump to the collection
await emptyCollection.importDump(json);

// import the dump to the database
await emptyDatabase.importDump(json);

**Key-Compression**

Depending on which adapter and in which environment you use RxDB, client-side storage is limited in some way or the other. To save disc-space, RxDB uses a schema based keycompression to minimize the size of saved documents. This saves about 40% of used storage.

Example:

// when you save an object with big keys
await myCollection.insert({
  firstName: 'foo'
  lastName:  'bar'
  stupidLongKey: 5
});

// key compression will internally transform it to
{
  '|a': 'foo'
  '|b':  'bar'
  '|c': 5
}

// so instead of 46 chars, the compressed-version has only 28
// the compression works internally, so you can of course still access values via the original key.names and run normal queries.
console.log(myDoc.firstName);
// 'foo'

And for any other use case, there are many more plugins and addons.

  Get started
-------------

Get started now by reading the docs or exploring the example-projects.

  Support and Contribute
------------------------

-   Check out how you can contribute to this project.
-   Read this when you have found a bug
-   Buy access to the premium plugins
-   Join us at discord to get help
-   Give Feedback (anonymous)

#### More content

Angular Database, Frontend Database, localStorage, React Database, Browser Database, React Native Database, PWA Database, In-memory NoSQL database, JSON database
