---
project: flexsearch
stars: 12793
description: Next-Generation full text search library for Browser and Node.js
url: https://github.com/nextapps-de/flexsearch
---

FlexSearch v0.8: Overview and Migration Guide

==

### Next-Generation full-text search library for Browser and Node.js

Basic Start  •  API Reference  •  Encoder  •  Document Search  •  Persistent Indexes  •  Using Worker  •  Tag Search  •  Resolver  •  Customization  •  Changelog

Support this Project
--------------------

You can help me by making a personal donation to keep this project alive and also to provide all the contribution to solve your needs.

### FlexSearch Sponsors

  
Antithesis Operations LLC

FlexSearch performs queries up to 1,000,000 times faster compared to other libraries by also providing powerful search capabilities like multi-field search (document search), phonetic transformations, partial matching, tag-search or suggestions.

Bigger workloads are scalable through workers to perform any updates or queries on the index in parallel through dedicated balanced threads.

The latest generation v0.8 introduce Persistent Indexes, well optimized for scaling of large datasets and running in parallel. All available features was natively ported right into the database engine of your choice.

FlexSearch was nominated by the GitNation for the "Best Technology of the Year".

Supported Platforms:

-   Browser
-   Node.js

Supported Database:

-   InMemory (Default)
-   IndexedDB (Browser)
-   Redis
-   SQLite
-   Postgres
-   MongoDB
-   Clickhouse

Demos:

-   Auto-Complete

Library Comparison:

-   Performance Benchmark
-   Scoring Benchmark

Extern Projects & Plugins:

-   React: https://github.com/angeloashmore/react-use-flexsearch
-   Vue: https://github.com/Noction/vue-use-flexsearch
-   Gatsby: https://www.gatsbyjs.org/packages/gatsby-plugin-flexsearch/

Load Library (Node.js, ESM, Legacy Browser)
-------------------------------------------

npm install flexsearch

The **_dist_** folder are located in: `node_modules/flexsearch/dist/`

Build

File

CDN

flexsearch.bundle.debug.js

Download

https://cdn.jsdelivr.net/gh/nextapps-de/flexsearch@0.8.0/dist/flexsearch.bundle.debug.js

flexsearch.bundle.min.js

Download

https://cdn.jsdelivr.net/gh/nextapps-de/flexsearch@0.8.0/dist/flexsearch.bundle.min.js

flexsearch.bundle.module.debug.js

Download

https://cdn.jsdelivr.net/gh/nextapps-de/flexsearch@0.8.0/dist/flexsearch.bundle.module.debug.js

flexsearch.bundle.module.min.js

Download

https://cdn.jsdelivr.net/gh/nextapps-de/flexsearch@0.8.0/dist/flexsearch.bundle.module.min.js

flexsearch.es5.debug.js

Download

https://cdn.jsdelivr.net/gh/nextapps-de/flexsearch@0.8.0/dist/flexsearch.es5.debug.js

flexsearch.es5.min.js

Download

https://cdn.jsdelivr.net/gh/nextapps-de/flexsearch@0.8.0/dist/flexsearch.es5.min.js

flexsearch.light.debug.js

Download

https://cdn.jsdelivr.net/gh/nextapps-de/flexsearch@0.8.0/dist/flexsearch.light.debug.js

flexsearch.light.min.js

Download

https://cdn.jsdelivr.net/gh/nextapps-de/flexsearch@0.8.0/dist/flexsearch.light.min.js

flexsearch.light.module.debug.js

Download

https://cdn.jsdelivr.net/gh/nextapps-de/flexsearch@0.8.0/dist/flexsearch.light.module.debug.js

flexsearch.light.module.min.js

Download

https://cdn.jsdelivr.net/gh/nextapps-de/flexsearch@0.8.0/dist/flexsearch.light.module.min.js

Javascript Modules (ESM)

Download

https://github.com/nextapps-de/flexsearch/tree/0.8.0/dist/module

Javascript Modules Minified (ESM)

Download

https://github.com/nextapps-de/flexsearch/tree/0.8.0/dist/module-min

Javascript Modules Debug (ESM)

Download

https://github.com/nextapps-de/flexsearch/tree/0.8.0/dist/module-debug

flexsearch.custom.js

Read more about "Custom Build"

> All debug versions are providing debug information through the console and gives you helpful advices on certain situations. Do not use them in production, since they are special builds containing extra debugging processes which noticeably reduce performance.

The abbreviations used at the end of the filenames indicates:

-   `bundle` All features included, FlexSearch is available on `window.FlexSearch`
-   `light` Only basic features are included, FlexSearch is available on `window.FlexSearch`
-   `es5` bundle has support for EcmaScript5, FlexSearch is available on `window.FlexSearch`
-   `module` indicates that this bundle is a Javascript module (ESM), FlexSearch members are available by `import { Index, Document, Worker, Encoder, Charset } from "./flexsearch.bundle.module.min.js"` or alternatively using the default export `import FlexSearch from "./flexsearch.bundle.module.min.js"`
-   `min` bundle is minified
-   `debug` bundle has enabled debug mode and contains additional code just for debugging purposes (do not use for production)

### Compare Web-Bundles

> The Node.js package includes all features from `flexsearch.bundle.js`.

Feature

flexsearch.bundle.js

flexsearch.compact.js

flexsearch.light.js

Presets

✓

✓

✓

Async Search

✓

✓

\-

Workers (Web + Node.js)

✓

\-

\-

Contextual Indexes

✓

✓

✓

Document Search

✓

✓

\-

Document Store

✓

✓

\-

Partial Matching

✓

✓

✓

Relevance Scoring

✓

✓

✓

Auto-Balanced Cache by Popularity/Last Queries

✓

\-

\-

Tag Search

✓

\-

\-

Suggestions

✓

✓

✓

Phonetic Match (Fuzzy Search)

✓

✓

\-

Encoder

✓

✓

✓

Export / Import Indexes

✓

✓

\-

Resolver

✓

\-

\-

Persistent Index (IndexedDB)

✓

\-

\-

File Size (gzip)

14.0 kb

9.0 kb

4.4 kb

Performance Benchmark (Ranking)
-------------------------------

Run Comparison: Performance Benchmark "Gulliver's Travels"

The benchmark was measured in terms per seconds, higher values are better (except the test "Memory"). The memory value refers to the amount of memory which was additionally allocated during search.

Library

Memory

Query: Single

Query: Multi

Query: Large

Query: Not Found

flexsearch

6

58517675

43198115

51027989

62833661

jsii

1433

13588

881007

1567895

3474710

wade

717

60598

439914

424209

1287136

js-search

2100

22562

372234

417775

963609

minisearch

4126

29360

186900

5695

297981

elasticlunr

681

13913

46548

96998

93732

orama

12881

27918

167979

4327

221231

lunr

2495

11178

49087

85513

100487

ufuzzy

24802

2720

7569

57027

9413

bm25

33502

3681

4781

12923

12804

fuzzysearch

142915

145

221

436

266

fuse

363722

410

312

330

319

Load Library
------------

There are 3 types of indexes:

1.  `Index` is a flat high performance index which stores id-content-pairs.
2.  `Worker` / `WorkerIndex` is also a flat index which stores id-content-pairs but runs in background as a dedicated worker thread.
3.  `Document` is multi-field index which can store complex JSON documents (could also exist of worker indexes).

The most of you probably need just one of them according to your scenario.

### Non-Module Bundles (ES5 Legacy)

> Non-Module Bundles export all their features to the public namespace "FlexSearch" e.g. `window.FlexSearch.Index` or `window.FlexSearch.Document`.

Load the bundle by a script tag:

<script src\="dist/flexsearch.bundle.min.js"\></script\>
<script\>
  // ... access FlexSearch
  var Index \= window.FlexSearch.Index;
  var index \= new Index(/\* ... \*/);
</script\>

FlexSearch Members are accessible on:

var Index \= window.FlexSearch.Index;
var Document \= window.FlexSearch.Document;
var Encoder \= window.FlexSearch.Encoder;
var Charset \= window.FlexSearch.Charset;
var Resolver \= window.FlexSearch.Resolver;
var Worker \= window.FlexSearch.Worker;
var IdxDB \= window.FlexSearch.IndexedDB;
// only exported by non-module builds:
var Language \= window.FlexSearch.Language;

Load language packs:

<!-- English: -->
<script src\="dist/lang/en.min.js"\></script\>
<!-- German: -->
<script src\="dist/lang/de.min.js"\></script\>
<!-- French: -->
<script src\="dist/lang/fr.min.js"\></script\>
<script\>
  var EnglishEncoderPreset \= window.FlexSearch.Language.en;
  var GermanEncoderPreset \= window.FlexSearch.Language.de;
  var FrenchEncoderPreset \= window.FlexSearch.Language.fr;
</script\>

### Module (ESM)

When using modules you can choose from 2 variants: `flexsearch.xxx.module.min.js` has all features bundled ready for production, whereas the folder `/dist/module/` export all the features in the same structure as the source code but here compiler flags was resolved.

Also, for each variant there exist:

1.  A debug version for the development
2.  A pre-compiled minified version for production

Use the bundled version exported as a module (default export):

<script type\="module"\>
    import FlexSearch from "./dist/flexsearch.bundle.module.min.js";
    const index \= new FlexSearch.Index(/\* ... \*/);
</script\>

Or import FlexSearch members separately by:

<script type\="module"\>
    import { Index, Document, Encoder, Charset, Resolver, Worker, IdxDB } 
        from "./dist/flexsearch.bundle.module.min.js";
    const index \= new Index(/\* ... \*/);
</script\>

Use non-bundled modules:

<script type\="module"\>
    import Index from "./dist/module/index.js";
    import Document from "./dist/module/document.js";
    import Encoder from "./dist/module/encoder.js";
    import Charset from "./dist/module/charset.js";
    import Resolver from "./dist/module/resolver.js";
    import Worker from "./dist/module/worker.js";
    import IdxDB from "./dist/module/db/indexeddb/index.js";
    const index \= new Index(/\* ... \*/);
</script\>

Language packs are accessible via:

import EnglishEncoderPreset from "./dist/module/lang/en.js";
import GermanEncoderPreset from "./dist/module/lang/de.js";
import FrenchEncoderPreset from "./dist/module/lang/fr.js";

Also, pre-compiled non-bundled production-ready modules are located in `dist/module-min/`, whereas the debug version is located at `dist/module-debug/`.

You can also load modules via CDN:

<script type\="module"\>
    import Index from "https://unpkg.com/flexsearch@0.8.0/dist/module/index.js";
    const index \= new Index(/\* ... \*/);
</script\>

### Node.js

Install FlexSearch via NPM:

```
npm install flexsearch
```

Use the default export:

const FlexSearch \= require("flexsearch");
const index \= new FlexSearch.Index(/\* ... \*/);

Or require FlexSearch members separately by:

const { Index, Document, Encoder, Charset, Resolver, Worker, IdxDB } \= require("flexsearch");
const index \= new Index(/\* ... \*/);

When you are using ESM in Node.js then just use the Modules explained one section above.

Language packs are accessible via:

const EnglishEncoderPreset \= require("flexsearch/lang/en");
const GermanEncoderPreset \= require("flexsearch/lang/de");
const FrenchEncoderPreset \= require("flexsearch/lang/fr");

Persistent Connectors are accessible via:

const Postgres \= require("flexsearch/db/postgres");
const Sqlite \= require("flexsearch/db/sqlite");
const MongoDB \= require("flexsearch/db/mongodb");
const Redis \= require("flexsearch/db/redis");
const Clickhouse \= require("flexsearch/db/clickhouse");

Basic Usage and Variants
------------------------

index.add(id, text);
index.search(text);
index.search(text, limit);
index.search(text, options);
index.search(text, limit, options);
index.search(options);

document.add(doc);
document.add(id, doc);
document.search(text);
document.search(text, limit);
document.search(text, options);
document.search(text, limit, options);
document.search(options);

worker.add(id, text);
worker.search(text);
worker.search(text, limit);
worker.search(text, options);
worker.search(text, limit, options);
worker.search(text, limit, options, callback);
worker.search(options);

The `worker` inherits from type `Index` and does not inherit from type `Document`. Therefore, a WorkerIndex basically works like a standard FlexSearch Index. Worker-Support in documents needs to be enabled by just passing the appropriate option during creation `{ worker: true }`.

> Every method called on a `Worker` index is treated as async. You will get back a `Promise` or you can provide a callback function as the last parameter alternatively.

### Examples Node.js

-   nodejs-commonjs:
    -   basic
    -   basic-suggestion
    -   basic-persistent
    -   basic-resolver
    -   basic-worker
    -   basic-worker-extern-config
    -   basic-worker-export-import
    -   basic-export-import
    -   document
    -   document-persistent
    -   document-worker
    -   document-worker-extern-config
    -   document-export-import
    -   document-worker-export-import
    -   language-pack
-   nodejs-esm:
    -   basic
    -   basic-suggestion
    -   basic-persistent
    -   basic-resolver
    -   basic-worker
    -   basic-worker-extern-config
    -   basic-worker-export-import
    -   basic-export-import
    -   document
    -   document-persistent
    -   document-worker
    -   document-worker-extern-config
    -   document-export-import
    -   document-worker-export-import
    -   language-pack

### Examples Browser

-   browser-legacy:
    -   basic
    -   basic-suggestion
    -   basic-persistent
    -   basic-resolver
    -   basic-worker
    -   document
    -   document-highlighting
    -   document-persistent
    -   document-worker
    -   language-pack
-   browser-module:
    -   basic
    -   basic-suggestion
    -   basic-persistent
    -   basic-resolver
    -   basic-worker
    -   basic-worker-extern-config
    -   document
    -   document-highlighting
    -   document-persistent
    -   document-worker
    -   document-worker-extern-config
    -   language-pack

API Overview
------------

Global methods:

-   FlexSearch.**registerCharset**(name, charset)
-   FlexSearch.**registerLanguage**(name, language)

Index methods:

-   Index.**add**(id, string) \*
-   Index.**append**(id, string) \*
-   Index.**update**(id, string) \*
-   Index.**remove**(id) \*
-   Index.**search**(string, <limit>, <options>) \*
-   Index.**search**(options) \*
-   _async_ Index.**export**(handler)
-   _async_ Index.**import**(key, data)

WorkerIndex methods:

-   _async_ Index.**add**(id, string)
-   _async_ Index.**append**(id, string)
-   _async_ Index.**update**(id, string)
-   _async_ Index.**remove**(id)
-   _async_ Index.**search**(string, <limit>, <options>)
-   _async_ Index.**search**(options)
-   _async_ Index.**export**(handler) (WIP)
-   _async_ Index.**import**(key, data) (WIP)

Document methods:

-   Document.**add**(<id>, document) \*
-   Document.**append**(<id>, document) \*
-   Document.**update**(<id>, document) \*
-   Document.**remove**(id || document) \*
-   Document.**search**(string, <limit>, <options>) \*
-   Document.**search**(options) \*
-   _async_ Document.**export**(handler)
-   _async_ Document.**import**(key, data)

\* For each of those methods there exist an asynchronous equivalent:

Async Version:

-   _async_ .**addAsync**( ... , <callback>)
-   _async_ .**appendAsync**( ... , <callback>)
-   _async_ .**updateAsync**( ... , <callback>)
-   _async_ .**removeAsync**( ... , <callback>)
-   _async_ .**searchAsync**( ... , <callback>)

Async methods will return a `Promise`, alternatively you can pass a callback function as the last parameter.

Methods `export` and also `import` are always async as well as every method you call on a Worker-based Index.

Options
-------

FlexSearch is highly customizable. Make use of the right options can really improve your results as well as memory economy and query time.

### Index Options

Option

Values

Description

Default

preset

"memory"  
"performance"  
"match"  
"score"  
"default"

The configuration profile as a shortcut or as a base for your custom settings.  

"default"

tokenize

"strict"  
"forward"  
"reverse"  
"full"

The indexing mode (tokenizer).  
  
Choose one of the built-ins or pass a custom tokenizer function.  

"strict"

cache

Boolean  
Number

Enable/Disable and/or set capacity of cached entries.  
  
When passing a number as a limit the **cache automatically balance stored entries related to their popularity**.  
  
Note: When just using "true" the cache has no limits and growth unbounded.

false

resolution

Number

Sets the scoring resolution (default: 9).

9

context

Boolean  
Context Options

Enable/Disable contextual indexing. When passing "true" as value it will take the default values for the context.

false

optimize

Boolean

When enabled it uses a memory-optimized stack flow for the index.

true

boost

function(arr, str, int) => float

A custom boost function used when indexing contents to the index. The function has this signature: `Function(words[], term, index) => Float`. It has 3 parameters where you get an array of all words, the current term and the current index where the term is placed in the word array. You can apply your own calculation e.g. the occurrences of a term and return this factor (<1 means relevance is lowered, >1 means relevance is increased).  
  
Note: this feature is currently limited by using the tokenizer "strict" only.

null

Language-specific Options and Encoding:

charset  
  

Charset Payload  
String (key)

Provide a custom charset payload or pass one of the keys of built-in charsets.

"latin"

language  
  

Language Payload  
String (key)

Provide a custom language payload or pass in language shorthand flag (ISO-3166) of built-in languages.

null

encode  
  
  
  
  
  
  

false  
"default"  
"simple"  
"balance"  
"advanced"  
"extra"  
function(str) => \[words\]

The encoding type.  
  
Choose one of the built-ins or pass a custom encoding function.

"default"

stemmer  
  
  

false  
String  
Function

false

filter  
  
  

false  
String  
Function

false

matcher  
  
  

false  
String  
Function

false

Additional Options for Document Indexes:

worker  

Boolean

Enable/Disable and set count of running worker threads.

false

document  

Document Descriptor

Includes definitions for the document index and storage.

### Context Options

Option

Values

Description

Default

resolution

Number

Sets the scoring resolution for the context (default: 1).

1

depth  
  

false  
Number

Enable/Disable contextual indexing and also sets contextual distance of relevance. Depth is the maximum number of words/tokens away a term to be considered as relevant.

1

bidirectional

Boolean

Sets bidirectional search result. If enabled and the source text contains "red hat", it will be found for queries "red hat" and "hat red".

true

### Document Options

Option

Values

Description

Default

id  

String

"id""

tag  
  

false  
String

"tag"

index  
  
  

String  
Array<String>  
Array<Object>

store  
  
  

Boolean  
String  
Array<String>

false

### Charset Options

Option

Values

Description

Default

split  
  

false  
RegExp  
String

The rule to split words when using non-custom tokenizer (built-ins e.g. "forward"). Use a string/char or use a regular expression (default: `/\W+/`).  

`/[\W_]+/`

rtl  

Boolean

Enables Right-To-Left encoding.

false

encode  

function(str) => \[words\]

The custom encoding function.

/lang/latin/default.js

### Language Options

Option

Values

Description

stemmer  
  
  

false  
String  
Function

Disable or pass in language shorthand flag (ISO-3166) or a custom object.

filter  
  
  

false  
String  
Function

Disable or pass in language shorthand flag (ISO-3166) or a custom array.

matcher  
  
  

false  
String  
Function

Disable or pass in language shorthand flag (ISO-3166) or a custom array.

### Search Options

Option

Values

Description

Default

limit

number

Sets the limit of results.

100

offset

number

Apply offset (skip items).

0

suggest

Boolean

Enables suggestions in results.

false

### Document Search Options

-   Additionally, to the Index search options above.

Option

Values

Description

Default

index

String  
Array<String>  
Array<Object>

Sets the document fields which should be searched. When no field is set, all fields will be searched. Custom options per field are also supported.

tag

String  
Array<String>

Sets the document fields which should be searched. When no field is set, all fields will be searched. Custom options per field are also supported.

false

enrich

Boolean

Enrich IDs from the results with the corresponding documents.

false

bool

"and"  
"or"

Sets the used logical operator when searching through multiple fields or tags.

"or"

Tokenizer (Prefix Search)
-------------------------

Tokenizer affects the required memory also as query time and flexibility of partial matches. Try to choose the most upper of these tokenizer which fits your needs:

Option

Description

Example

Memory Factor (n = length of word)

**"strict"**

index whole words

`foobar`

\* 1

**"forward"**

incrementally index words in forward direction

`fo`obar  
`foob`ar  

\* n

**"reverse"**

incrementally index words in both directions

foob`ar`  
fo`obar`

\* 2n - 1

**"full"**

index every possible combination

fo`oba`r  
f`oob`ar

\* n \* (n - 1)

Encoders
--------

Encoding affects the required memory also as query time and phonetic matches. Try to choose the most upper of these encoders which fits your needs, or pass in a custom encoder:

Option

Description

False-Positives

Compression

**false**

Turn off encoding

no

0%

**"default"**

Case in-sensitive encoding

no

0%

**"simple"**

Case in-sensitive encoding  
Charset normalizations

no

~ 3%

**"balance"**

Case in-sensitive encoding  
Charset normalizations  
Literal transformations

no

~ 30%

**"advanced"**

Case in-sensitive encoding  
Charset normalizations  
Literal transformations  
Phonetic normalizations

no

~ 40%

**"extra"**

Case in-sensitive encoding  
Charset normalizations  
Literal transformations  
Phonetic normalizations  
Soundex transformations

yes

~ 65%

**function()**

Pass custom encoding via _function(string):\[words\]_

Usage
-----

#### Create a new index

var index \= new Index();

Create a new index and choosing one of the presets:

var index \= new Index("performance");

Create a new index with custom options:

var index \= new Index({
    charset: "latin:extra",
    tokenize: "reverse",
    resolution: 9
});

Create a new index and extend a preset with custom options:

var index \= new FlexSearch({
    preset: "memory",
    tokenize: "forward",
    resolution: 5
});

The resolution refers to the maximum count of scoring slots on which the content is divided into.

> A formula to determine a well-balanced value for the `resolution` is: $2\*floor(\\sqrt{content.length})$ where content is the value pushed by `index.add()`. Here the maximum length of all contents should be used.

See all available custom options.

#### Add text item to an index

Every content which should be added to the index needs an ID. When your content has no ID, then you need to create one by passing an index or count or something else as an ID (a value from type `number` is highly recommended). Those IDs are unique references to a given content. This is important when you update or adding over content through existing IDs. When referencing is not a concern, you can simply use something simple like `count++`.

> Index.**add(id, string)**

index.add(0, "John Doe");

#### Search items

> Index.**search(string | options, <limit>, <options>)**

index.search("John");

Limit the result:

index.search("John", 10);

#### Check existence of already indexed IDs

You can check if an ID was already indexed by:

if(index.contain(1)){
    console.log("ID is already in index");
}

Async
-----

You can call each method in its async version, e.g. `index.addAsync` or `index.searchAsync`.

You can assign callbacks to each async function:

index.addAsync(id, content, function(){
    console.log("Task Done");
});

index.searchAsync(query, function(result){
    console.log("Results: ", result);
});

Or do not pass a callback function and getting back a `Promise` instead:

index.addAsync(id, content).then(function(){
    console.log("Task Done");
});

index.searchAsync(query).then(function(result){
    console.log("Results: ", result);
});

Or use `async` and `await`:

async function add(){
    await index.addAsync(id, content);
    console.log("Task Done");
}

async function search(){
    const results \= await index.searchAsync(query);
    console.log("Results: ", result);
}

Append Contents (\*deprecated)
------------------------------

You can append contents to an existing index like:

index.append(id, content);

This will not overwrite the old indexed contents as it will do when perform `index.update(id, content)`. Keep in mind that `index.add(id, content)` will also perform "update" under the hood when the id was already being indexed.

Appended contents will have their own context and also their own full `resolution`. Therefore, the relevance isn't being stacked but gets its own context.

Let us take this example:

index.add(0, "some index");
index.append(0, "some appended content");

index.add(1, "some text");
index.append(1, "index appended content");

When you query `index.search("index")` then you will get index id 1 as the first entry in the result, because the context starts from zero for the appended data (isn't stacked to the old context) and here "index" is the first term.

If you didn't want this behavior than just use the standard `index.add(id, content)` and provide the full length of content.

#### Update item from an index

> Index.**update(id, string)**

index.update(0, "Max Miller");

#### Remove item from an index

> Index.**remove(id)**

index.remove(0);

#### Add custom tokenizer

> A tokenizer split words/terms into components or partials.

Define a private custom tokenizer during creation/initialization:

var index \= new FlexSearch({

    tokenize: function(str){

        return str.split(/\\s\-\\//g);
    }
});

> The tokenizer function gets a string as a parameter and has to return an array of strings representing a word or term. In some languages every char is a term and also not separated via whitespaces.

#### Add language-specific stemmer and/or filter

> **Stemmer:** several linguistic mutations of the same word (e.g. "run" and "running")

> **Filter:** a blacklist of words to be filtered out from indexing at all (e.g. "and", "to" or "be")

Assign a private custom stemmer or filter during creation/initialization:

var index \= new FlexSearch({

    stemmer: {

        // object {key: replacement}
        "ational": "ate",
        "tional": "tion",
        "enci": "ence",
        "ing": ""
    },
    filter: \[

        // array blacklist
        "in",
        "into",
        "is",
        "isn't",
        "it",
        "it's"
    \]
});

Using a custom filter, e.g.:

var index \= new FlexSearch({

    filter: function(value){

        // just add values with length > 1 to the index

        return value.length \> 1;
    }
});

Or assign stemmer/filters globally to a language:

> Stemmer are passed as a object (key-value-pair), filter as an array.

FlexSearch.registerLanguage("us", {

    stemmer: { /\* ... \*/ },
    filter:  \[ /\* ... \*/ \]
});

Or use some pre-defined stemmer or filter of your preferred languages:

<html\>
<head\>
    <script src\="js/flexsearch.bundle.js"\></script\>
    <script src\="js/lang/en.min.js"\></script\>
    <script src\="js/lang/de.min.js"\></script\>
</head\>
...

Now you can assign built-in stemmer during creation/initialization:

var index\_en \= new FlexSearch.Index({
    language: "en"
});

var index\_de \= new FlexSearch.Index({
    language: "de"
});

In Node.js all built-in language packs files are available:

const { Index } \= require("flexsearch");

var index\_en \= new Index({
    language: "en"
});

### Right-To-Left Support

> Set the tokenizer at least to "reverse" or "full" when using RTL.

Just set the field "rtl" to _true_ and use a compatible tokenizer:

var index \= new Index({
    encode: str \=> str.toLowerCase().split(/\[^a\-z\]+/),
    tokenize: "reverse",
    rtl: true
});

### CJK Word Break (Chinese, Japanese, Korean)

Set a custom tokenizer which fits your needs, e.g.:

var index \= FlexSearch.create({
    encode: str \=> str.replace(/\[\\x00\-\\x7F\]/g, "").split("")
});

You can also pass a custom encoder function to apply some linguistic transformations.

index.add(0, "一个单词");

var results \= index.search("单词");

Index Documents (Field-Search)
------------------------------

### The Document Descriptor

Assuming our document has a data structure like this:

{ 
    "id": 0, 
    "content": "some text"
}

Old syntax FlexSearch v0.6.3 (_**not supported anymore!**_):

const index \= new Document({
    doc: {
        id: "id",
        field: \["content"\]
    }
});

> The document descriptor has slightly changed, there is no `field` branch anymore, instead just apply one level higher, so `key` becomes a main member of options.

For the new syntax the field "doc" was renamed to `document` and the field "field" was renamed to `index`:

const index \= new Document({
    document: {
        id: "id",
        index: \["content"\]
    }
});

index.add({ 
    id: 0, 
    content: "some text"
});

The field `id` describes where the ID or unique key lives inside your documents. The default key gets the value `id` by default when not passed, so you can shorten the example from above to:

const index \= new Document({
    document: {
        index: \["content"\]
    }
});

The member `index` has a list of fields which you want to be indexed from your documents. When just selecting one field, then you can pass a string. When also using default key `id` then this shortens to just:

const index \= new Document({ document: "content" });
index.add({ id: 0, content: "some text" });

Assuming you have several fields, you can add multiple fields to the index:

var docs \= \[{
    id: 0,
    title: "Title A",
    content: "Body A"
},{
    id: 1,
    title: "Title B",
    content: "Body B"
}\];

const index \= new Document({
    id: "id",
    index: \["title", "content"\]
});

You can pass custom options for each field:

const index \= new Document({
    id: "id",
    index: \[{
        field: "title",
        tokenize: "forward",
        optimize: true,
        resolution: 9
    },{
        field:  "content",
        tokenize: "strict",
        optimize: true,
        resolution: 5,
        minlength: 3,
        context: {
            depth: 1,
            resolution: 3
        }
    }\]
});

Field options gets inherited when also global options was passed, e.g.:

const index \= new Document({
    tokenize: "strict",
    optimize: true,
    resolution: 9,
    document: {
        id: "id",
        index:\[{
            field: "title",
            tokenize: "forward"
        },{
            field: "content",
            minlength: 3,
            context: {
                depth: 1,
                resolution: 3
            }
        }\]
    }
});

Note: The context options from the field "content" also gets inherited by the corresponding field options, whereas this field options was inherited by the global option.

### Nested Data Fields (Complex Objects)

Assume the document array looks more complex (has nested branches etc.), e.g.:

{
  "record": {
    "id": 0,
    "title": "some title",
    "content": {
      "header": "some text",
      "footer": "some text"
    }
  }
}

Then use the colon separated notation `root:child:child` to define hierarchy within the document descriptor:

const index \= new Document({
    document: {
        id: "record:id",
        index: \[
            "record:title",
            "record:content:header",
            "record:content:footer"
        \]
    }
});

> Just add fields you want to query against. Do not add fields to the index, you just need in the result (but did not query against). For this purpose you can store documents independently of its index (read below).

When you want to query through a field you have to pass the exact key of the field you have defined in the `doc` as a field name (with colon syntax):

index.search(query, {
    index: \[
        "record:title",
        "record:content:header",
        "record:content:footer"
    \]
});

Same as:

index.search(query, \[
    "record:title",
    "record:content:header",
    "record:content:footer"
\]);

Using field-specific options:

index.search(\[{
    field: "record:title",
    query: "some query",
    limit: 100,
    suggest: true
},{
    field: "record:title",
    query: "some other query",
    limit: 100,
    suggest: true
}\]);

You can perform a search through the same field with different queries.

> When passing field-specific options you need to provide the full configuration for each field. They get not inherited like the document descriptor.

### Complex Documents

You need to follow 2 rules for your documents:

1.  The document cannot start with an Array at the root index. This will introduce sequential data and isn't supported yet. See below for a workaround for such data.

\[ // <-- not allowed as document start!
  {
    "id": 0,
    "title": "title"
  }
\]

1.  The id can't be nested inside an array (also none of the parent fields can't be an array). This will introduce sequential data and isn't supported yet. See below for a workaround for such data.

{
  "records": \[ // <-- not allowed when ID or tag lives inside!
    {
      "id": 0,
      "title": "title"
    }
  \]
}

Here an example for a supported complex document:

{
  "meta": {
    "tag": "cat",
    "id": 0
  },
  "contents": \[
    {
      "body": {
        "title": "some title",
        "footer": "some text"
      },
      "keywords": \["some", "key", "words"\]
    },
    {
      "body": {
        "title": "some title",
        "footer": "some text"
      },
      "keywords": \["some", "key", "words"\]
    }
  \]
}

The corresponding document descriptor (when all fields should be indexed) looks like:

const index \= new Document({
    document: {
        id: "meta:id",
        tag: "meta:tag",
        index: \[
            "contents\[\]:body:title",
            "contents\[\]:body:footer",
            "contents\[\]:keywords"
        \]
    }
});

Again, when searching you have to use the same colon-separated-string from your field definition.

index.search(query, { 
    index: "contents\[\]:body:title"
});

### Not Supported Documents (Sequential Data)

This example breaks both rules from above:

\[ // <-- not allowed as document start!
  {
    "tag": "cat",
    "records": \[ // <-- not allowed when ID or tag lives inside!
      {
        "id": 0,
        "body": {
          "title": "some title",
          "footer": "some text"
        },
        "keywords": \["some", "key", "words"\]
      },
      {
        "id": 1,
        "body": {
          "title": "some title",
          "footer": "some text"
        },
        "keywords": \["some", "key", "words"\]
      }
    \]
  }
\]

You need to apply some kind of structure normalization.

A workaround to such a data structure looks like this:

const index \= new Document({
    document: {
        id: "record:id",
        tag: "tag",
        index: \[
            "record:body:title",
            "record:body:footer",
            "record:body:keywords"
        \]
    }
});

function add(sequential\_data){

    for(let x \= 0, data; x < sequential\_data.length; x++){

        data \= sequential\_data\[x\];

        for(let y \= 0, record; y < data.records.length; y++){

            record \= data.records\[y\];

            index.add({
                id: record.id,
                tag: data.tag,
                record: record
            });
        }
    }  
}

// now just use add() helper method as usual:

add(\[{
    // sequential structured data
    // take the data example above
}\]);

You can skip the first loop when your document data has just one index as the outer array.

### Add/Update/Remove Documents to/from the Index

Add a document to the index:

index.add({
            id: 0,
            title: "Foo",
            content: "Bar"
          });

Update index with a single object or an array of objects:

index.update({
    data:{
        id: 0,
        title: "Foo",
        body: {
            content: "Bar"
        }
    }
});

Remove a single object or an array of objects from the index:

index.remove(docs);

When the id is known, you can also simply remove by (faster):

index.remove(id);

### Join / Append Arrays

On the complex example above, the field `keywords` is an array but here the markup did not have brackets like `keywords[]`. That will also detect the array but instead of appending each entry to a new context, the array will be joined into on large string and added to the index.

The difference of both kinds of adding array contents is the relevance when searching. When adding each item of an array via `append()` to its own context by using the syntax `field[]`, then the relevance of the last entry concurrent with the first entry. When you left the brackets in the notation, it will join the array to one whitespace-separated string. Here the first entry has the highest relevance, whereas the last entry has the lowest relevance.

So assuming the keyword from the example above are pre-sorted by relevance to its popularity, then you want to keep this order (information of relevance). For this purpose do not add brackets to the notation. Otherwise, it would take the entries in a new scoring context (the old order is getting lost).

Also you can left bracket notation for better performance and smaller memory footprint. Use it when you did not need the granularity of relevance by the entries.

### Field-Search

Search through all fields:

index.search(query);

Search through a specific field:

index.search(query, { index: "title" });

Search through a given set of fields:

index.search(query, { index: \["title", "content"\] });

Same as:

index.search(query, \["title", "content"\]);

Pass custom modifiers and queries to each field:

index.search(\[{
    field: "content",
    query: "some query",
    limit: 100,
    suggest: true
},{
    field: "content",
    query: "some other query",
    limit: 100,
    suggest: true
}\]);

You can perform a search through the same field with different queries.

See all available field-search options.

### The Result Set

Schema of the result-set:

> `fields[] => { field, result[] => { document }}`

The first index is an array of fields the query was applied to. Each of this field has a record (object) with 2 properties "field" and "result". The "result" is also an array and includes the result for this specific field. The result could be an array of IDs or as enriched with stored document data.

A non-enriched result set now looks like:

\[{
    field: "title",
    result: \[0, 1, 2\]
},{
    field: "content",
    result: \[3, 4, 5\]
}\]

An enriched result set now looks like:

\[{
    field: "title",
    result: \[
        { id: 0, doc: { /\* document \*/ }},
        { id: 1, doc: { /\* document \*/ }},
        { id: 2, doc: { /\* document \*/ }}
    \]
},{
    field: "content",
    result: \[
        { id: 3, doc: { /\* document \*/ }},
        { id: 4, doc: { /\* document \*/ }},
        { id: 5, doc: { /\* document \*/ }}
    \]
}\]

When using `pluck` instead of "field" you can explicitly select just one field and get back a flat representation:

index.search(query, { pluck: "title", enrich: true });

\[
    { id: 0, doc: { /\* document \*/ }},
    { id: 1, doc: { /\* document \*/ }},
    { id: 2, doc: { /\* document \*/ }}
\]

This result set is a replacement of "boolean search". Instead of applying your bool logic to a nested object, you can apply your logic by yourself on top of the result-set dynamically. This opens hugely capabilities on how you process the results. Therefore, the results from the fields aren't squashed into one result anymore. That keeps some important information, like the name of the field as well as the relevance of each field results which didn't get mixed anymore.

> A field search will apply a query with the boolean "or" logic by default. Each field has its own result to the given query.

There is one situation where the `bool` property is being still supported. When you like to switch the default "or" logic from the field search into "and", e.g.:

index.search(query, { 
    index: \["title", "content"\],
    bool: "and" 
});

You will just get results which contains the query in both fields. That's it.

### Tags

Like the `key` for the ID just define the path to the tag:

const index \= new Document({
    document: { 
        id: "id",
        tag: "tag",
        index: "content"
    }
});

index.add({
    id: 0,
    tag: "cat",
    content: "Some content ..."
});

Your data also can have multiple tags as an array:

index.add({
    id: 1,
    tag: \["animal", "dog"\],
    content: "Some content ..."
});

You can perform a tag-specific search by:

index.search(query, { 
    index: "content",
    tag: "animal" 
});

This just gives you result which was tagged with the given tag.

Use multiple tags when searching:

index.search(query, { 
    index: "content",
    tag: \["cat", "dog"\]
});

This gives you result which are tagged with one of the given tag.

> Multiple tags will apply as the boolean "or" by default. It just needs one of the tags to be existing.

This is another situation where the `bool` property is still supported. When you like to switch the default "or" logic from the tag search into "and", e.g.:

index.search(query, { 
    index: "content",
    tag: \["dog", "animal"\],
    bool: "and"
});

You will just get results which contains both tags (in this example there is just one records which has the tag "dog" and "animal").

### Tag Search

You can also fetch results from one or more tags when no query was passed:

index.search({ tag: \["cat", "dog"\] });

In this case the result-set looks like:

\[{
    tag: "cat",
    result: \[ /\* all cats \*/ \]
},{
    tag: "dog",
    result: \[ /\* all dogs \*/ \]
}\]

### Limit & Offset

> By default, every query is limited to 100 entries. Unbounded queries leads into issues. You need to set the limit as an option to adjust the size.

You can set the limit and the offset for each query:

index.search(query, { limit: 20, offset: 100 });

> You cannot pre-count the size of the result-set. That's a limit by the design of FlexSearch. When you really need a count of all results you are able to page through, then just assign a high enough limit and get back all results and apply your paging offset manually (this works also on server-side). FlexSearch is fast enough that this isn't an issue.

Document Store
--------------

Only a document index can have a store. You can use a document index instead of a flat index to get this functionality also when only storing ID-content-pairs.

You can define independently which fields should be indexed and which fields should be stored. This way you can index fields which should not be included in the search result.

> Do not use a store when: 1. an array of IDs as the result is good enough, or 2. you already have the contents/documents stored elsewhere (outside the index).

> When the `store` attribute was set, you have to include all fields which should be stored explicitly (acts like a whitelist).

> When the `store` attribute was not set, the original document is stored as a fallback.

This will add the whole original content to the store:

const index \= new Document({
    document: { 
        index: "content",
        store: true
    }
});

index.add({ id: 0, content: "some text" });

### Access documents from internal store

You can get indexed documents from the store:

var data \= index.get(1);

You can update/change store contents directly without changing the index by:

index.set(1, data);

To update the store and also update the index then just use `index.update`, `index.add` or `index.append`.

When you perform a query, weather it is a document index or a flat index, then you will always get back an array of IDs.

Optionally you can enrich the query results automatically with stored contents by:

index.search(query, { enrich: true });

Your results look now like:

\[{
    id: 0,
    doc: { /\* content from store \*/ }
},{
    id: 1,
    doc: { /\* content from store \*/ }
}\]

### Configure Storage (Recommended)

This will add just specific fields from a document to the store (the ID isn't necessary to keep in store):

const index \= new Document({
    document: {
        index: "content",
        store: \["author", "email"\]
    }
});

index.add(id, content);

You can configure independently what should being indexed and what should being stored. It is highly recommended to make use of this whenever you can.

Here a useful example of configuring doc and store:

const index \= new Document({
    document: { 
        index: "content",
        store: \["author", "email"\] 
    }
});

index.add({
    id: 0,
    author: "Jon Doe",
    email: "john@mail.com",
    content: "Some content for the index ..."
});

You can query through the contents and will get back the stored values instead:

index.search("some content", { enrich: true });

Your results are now looking like:

\[{
    field: "content",
    result: \[{
        id: 0,
        doc: {
            author: "Jon Doe",
            email: "john@mail.com",
        }
    }\]
}\]

Both field "author" and "email" are not indexed.

### Chaining

Simply chain methods like:

var index \= FlexSearch.create()
                      .addMatcher({'â': 'a'})
                      .add(0, 'foo')
                      .add(1, 'bar');

index.remove(0).update(1, 'foo').add(2, 'foobar');

Contextual Search
-----------------

> **Note:** This feature is disabled by default because of its extended memory usage. Read here get more information about and how to enable.

FlexSearch introduce a new scoring mechanism called **Contextual Search** which was invented by Thomas Wilkerling, the author of this library. A Contextual Search incredibly boost up queries to a complete new level but also requires some additional memory (depending on _**depth**_). The basic idea of this concept is to limit relevance by its context instead of calculating relevance through the whole distance of its corresponding document. This way contextual search also improves the results of relevance-based queries on a large amount of text data.

Enable Contextual Scoring
-------------------------

Create an index and use the default context:

var index \= new FlexSearch({

    tokenize: "strict",
    context: true
});

Create an index and apply custom options for the context:

var index \= new FlexSearch({

    tokenize: "strict",
    context: { 
        resolution: 5,
        depth: 3,
        bidirectional: true
    }
});

> Only the tokenizer "strict" is actually supported by the contextual index.

> The contextual index requires additional amount of memory depending on depth.

### Auto-Balanced Cache (By Popularity)

You need to initialize the cache and its limit during the creation of the index:

const index \= new Index({ cache: 100 });

const results \= index.searchCache(query);

A common scenario for using a cache is an autocomplete or instant search when typing.

> When passing a number as a limit the cache automatically balance stored entries related to their popularity.

> When just using "true" the cache is unbounded and perform actually 2-3 times faster (because the balancer do not have to run).

Worker Parallelism (Browser + Node.js)
--------------------------------------

The new worker model from v0.7.0 is divided into "fields" from the document (1 worker = 1 field index). This way the worker becomes able to solve tasks (subtasks) completely. The downside of this paradigm is they might not have been perfect balanced in storing contents (fields may have different length of contents). On the other hand there is no indication that balancing the storage gives any advantage (they all require the same amount in total).

When using a document index, then just apply the option "worker":

const index \= new Document({
    index: \["tag", "name", "title", "text"\],
    worker: true
});

index.add({ 
    id: 1, tag: "cat", name: "Tom", title: "some", text: "some" 
}).add({
    id: 2, tag: "dog", name: "Ben", title: "title", text: "content" 
}).add({ 
    id: 3, tag: "cat", name: "Max", title: "to", text: "to" 
}).add({ 
    id: 4, tag: "dog", name: "Tim", title: "index", text: "index" 
});

```
Worker 1: { 1: "cat", 2: "dog", 3: "cat", 4: "dog" }
Worker 2: { 1: "Tom", 2: "Ben", 3: "Max", 4: "Tim" }
Worker 3: { 1: "some", 2: "title", 3: "to", 4: "index" }
Worker 4: { 1: "some", 2: "content", 3: "to", 4: "index" }
```

When you perform a field search through all fields then this task is being balanced perfectly through all workers, which can solve their subtasks independently.

### Worker Index

Above we have seen that documents will create worker automatically for each field. You can also create a WorkerIndex directly (same like using `Index` instead of `Document`).

Use as ES6 module:

import WorkerIndex from "./worker/index.js";
const index \= new WorkerIndex(options);
index.add(1, "some")
     .add(2, "content")
     .add(3, "to")
     .add(4, "index");

Or when bundled version was used instead:

var index \= new FlexSearch.Worker(options);
index.add(1, "some")
     .add(2, "content")
     .add(3, "to")
     .add(4, "index");

Such a WorkerIndex works pretty much the same as a created instance of `Index`.

> A WorkerIndex only support the `async` variant of all methods. That means when you call `index.search()` on a WorkerIndex this will perform also in async the same way as `index.searchAsync()` will do.

### Worker Threads (Node.js)

The worker model for Node.js is based on "worker threads" and works exactly the same way:

const { Document } \= require("flexsearch");

const index \= new Document({
    index: \["tag", "name", "title", "text"\],
    worker: true
});

Or create a single worker instance for a non-document index:

const { Worker } \= require("flexsearch");
const index \= new Worker({ options });

### The Worker Async Model (Best Practices)

A worker will always perform as async. On a query method call you always should handle the returned promise (e.g. use `await`) or pass a callback function as the last parameter.

const index \= new Document({
    index: \["tag", "name", "title", "text"\],
    worker: true
});

All requests and sub-tasks will run in parallel (prioritize "all tasks completed"):

index.searchAsync(query, callback);
index.searchAsync(query, callback);
index.searchAsync(query, callback);

Also (prioritize "all tasks completed"):

index.searchAsync(query).then(callback);
index.searchAsync(query).then(callback);
index.searchAsync(query).then(callback);

Or when you have just one callback when all requests are done, simply use `Promise.all()` which also prioritize "all tasks completed":

Promise.all(\[
    index.searchAsync(query),
    index.searchAsync(query),
    index.searchAsync(query)
\]).then(callback);

Inside the callback of `Promise.all()` you will also get an array of results as the first parameter respectively for each query you put into.

When using `await` you can prioritize the order (prioritize "first task completed") and solve requests one by one and just process the sub-tasks in parallel:

await index.searchAsync(query);
await index.searchAsync(query);
await index.searchAsync(query);

Same for `index.add()`, `index.append()`, `index.remove()` or `index.update()`. Here there is a special case which isn't disabled by the library, but you need to keep in mind when using Workers.

When you call the "synced" version on a worker index:

index.add(doc);
index.add(doc);
index.add(doc);
// contents aren't indexed yet,
// they just queued on the message channel 

Of course, you can do that but keep in mind that the main thread does not have an additional queue for distributed worker tasks. Running these in a long loop fires content massively to the message channel via `worker.postMessage()` internally. Luckily the browser and Node.js will handle such incoming tasks for you automatically (as long enough free RAM is available). When using the "synced" version on a worker index, the content isn't indexed one line below, because all calls are treated as async by default.

> When adding/updating/removing large bulks of content to the index (or high frequency), it is recommended to use the async version along with `async/await` to keep a low memory footprint during long processes.

Export / Import (In-Memory)
---------------------------

### Node.js

> Persistent-Indexes and Worker-Indexes don't support Import/Export.

Export an `Index` or `Document-Index` to the folder `/export/`:

import { promises as fs } from "fs";

await index.export(async function(key, data){
  await fs.writeFile("./export/" + key, data, "utf8");
});

Import from folder `/export/` into an `Index` or `Document-Index`:

const index \= new Index({/\* keep old config and place it here \*/});

const files \= await fs.readdir("./export/");
for(let i \= 0; i < files.length; i++){
  const data \= await fs.readFile("./export/" + files\[i\], "utf8");
  await index.import(files\[i\], data);
}

> You'll need to use the same configuration as you used before the export. Any changes on the configuration needs to be re-indexed.

### Browser

index.export(function(key, data){ 
    
    // you need to store both the key and the data!
    // e.g. use the key for the filename and save your data
    
    localStorage.setItem(key, data);
});

> The size of the export corresponds to the memory consumption of the library. To reduce export size you have to use a configuration which has less memory footprint (use the table at the bottom to get information about configs and its memory allocation).

When your save routine runs asynchronously you have to use `async/await` or return a promise:

index.export(function(key, data){ 
    
    return new Promise(function(resolve){
        
        // do the saving as async

        resolve();
    });
});

Before you can import data, you need to create your index first. For document indexes provide the same document descriptor you used when export the data. This configuration isn't stored in the export.

const index \= new Index({/\* keep old config and place it here \*/});

To import the data just pass a key and data:

```
const data = localStorage.getItem(key);
index.import(key, data);
```

You need to import every key! Otherwise, your index does not work. You need to store the keys from the export and use this keys for the import (the order of the keys can differ).

> The feature "fastupdate" is automatically disabled on import.

This is just for demonstration and is not recommended, because you might have other keys in your localStorage which aren't supported as an import:

var keys \= Object.keys(localStorage);

for(let i \= 0, key, data; i < keys.length; i++){
    key \= keys\[i\]
    data \= localStorage.getItem(key);
    index.import(key, data);
}

Encoder
-------

Search capabilities highly depends on language processing. The old workflow wasn't really practicable. The new Encoder class is a huge improvement and fully replaces the encoding part. Some FlexSearch options was moved to the new `Encoder` instance.

New Encoding Pipeline:

1.  charset normalization
2.  custom preparation
3.  split into terms (apply includes/excludes)
4.  filter (pre-filter)
5.  matcher (substitute terms)
6.  stemmer (substitute term endings)
7.  filter (post-filter)
8.  replace chars (mapper)
9.  custom regex (replacer)
10.  letter deduplication
11.  apply finalize

### Example

const encoder \= new Encoder({
    normalize: true,
    dedupe: true,
    cache: true,
    include: {
        letter: true,
        number: true,
        symbol: false,
        punctuation: false,
        control: false,
        char: "@"
    }
});

You can use an `include` **instead** of an `exclude` definition:

const encoder \= new Encoder({
    exclude: {
        letter: false,
        number: false,
        symbol: true,
        punctuation: true,
        control: true
    }
});

Instead of using `include` or `exclude` you can pass a regular expression to the field `split`:

const encoder \= new Encoder({
    split: /\\s+/
});

> The definitions `include` and `exclude` is a replacement for `split`. You can just define one of those 3.

Adding custom functions to the encoder pipeline:

const encoder \= new Encoder({
    normalize: function(str){
        return str.toLowerCase();
    },
    prepare: function(str){
        return str.replace(/&/g, " and ");
    },
    finalize: function(arr){
        return arr.filter(term \=> term.length \> 2);
    }
});

Assign encoder to an index:

const index \= new Index({ 
    encoder: encoder
});

Define language specific transformations:

const encoder \= new Encoder({
    replacer: \[
        /\[´\`’ʼ\]/g, "'"
    \],
    filter: new Set(\[
        "and",
    \]),
    matcher: new Map(\[
        \["xvi", "16"\]
    \]),
    stemmer: new Map(\[
        \["ly", ""\]
    \]),
    mapper: new Map(\[
        \["é", "e"\]
    \])
});

Or use predefined language and extend it with custom options:

import EnglishBookPreset from "./lang/en.js";
const encoder \= new Encoder(EnglishBookPreset, {
    filter: false
});

Equivalent:

import EnglishBookPreset from "./lang/en.js";
const encoder \= new Encoder(EnglishBookPreset);
encoder.assign({ filter: false });

Assign extensions to the encoder instance:

import LatinEncoderPreset from "./charset/latin/simple.js";
import EnglishBookPreset from "./lang/en.js";
// stack definitions to the encoder instance
const encoder \= new Encoder()
    .assign(LatinEncoderPreset)
    .assign(EnglishBookPreset)
    // override preset options ...
    .assign({ minlength: 3 });
    // assign further presets ...

> When adding extension to the encoder every previously assigned configuration is still intact, very much like Mixins, also when assigning custom functions.

Add custom transformations to an existing index:

import LatinEncoderPreset from "./charset/latin/default.js";
const encoder \= new Encoder(LatinEncoderPreset);
encoder.addReplacer(/\[´\`’ʼ\]/g, "'");
encoder.addFilter("and");
encoder.addMatcher("xvi", "16");
encoder.addStemmer("ly", "");
encoder.addMapper("é", "e");

Shortcut for just assigning one encoder configuration to an index:

import LatinEncoderPreset from "./charset/latin/default.js";
const index \= new Index({ 
    encoder: LatinEncoderPreset
});

### Custom Encoder

Since it is very simple to create a custom Encoder, you are welcome to create your own. e.g.

function customEncoder(content){
   const tokens \= \[\];
   // split content into terms/tokens
   // apply your changes to each term/token
   // you will need to return an Array of terms/tokens
   // so just iterate through the input string and
   // push tokens to the array
   // ...
   return tokens;
}

const index \= new Index({
   // set to strict when your tokenization was already done
   tokenize: "strict",
   encode: customEncoder
});

If you get some good results please feel free to share your encoder.

Languages
---------

Language-specific definitions are being divided into two groups:

1.  Charset
    1.  _**encode**_, type: `function(string):string[]`
    2.  _**rtl**_, type: `boolean`
2.  Language
    1.  _**matcher**_, type: `{string: string}`
    2.  _**stemmer**_, type: `{string: string}`
    3.  _**filter**_, type: `string[]`

The charset contains the encoding logic, the language contains stemmer, stopword filter and matchers. Multiple language definitions can use the same charset encoder. Also this separation let you manage different language definitions for special use cases (e.g. names, cities, dialects/slang, etc.).

To fully describe a custom language **on the fly** you need to pass:

const index \= FlexSearch({
    // mandatory:
    encode: (content) \=> \[words\],
    // optionally:
    rtl: false,
    stemmer: {},
    matcher: {},
    filter: \[\]
});

When passing no parameter it uses the `latin:default` schema by default.

Field

Category

Description

**encode**

charset

The encoder function. Has to return an array of separated words (or an empty string).

**rtl**

charset

A boolean property which indicates right-to-left encoding.

**filter**

language

Filter are also known as "stopwords", they completely filter out words from being indexed.

**stemmer**

language

Stemmer removes word endings and is a kind of "partial normalization". A word ending just matched when the word length is bigger than the matched partial.

**matcher**

language

Matcher replaces all occurrences of a given string regardless of its position and is also a kind of "partial normalization".

### 1\. Language Packs: ES6 Modules

The most simple way to assign charset/language specific encoding via modules is:

import charset from "./dist/module/lang/latin/advanced.js";
import lang from "./dist/module/lang/en.js";

const index \= FlexSearch({
    charset: charset,
    lang: lang
});

Just import the **default export** by each module and assign them accordingly.

The full qualified example from above is:

import { encode, rtl } from "./dist/module/lang/latin/advanced.js";
import { stemmer, filter, matcher } from "./dist/module/lang/en.js";

const index \= FlexSearch({
    encode: encode,
    rtl: rtl,
    stemmer: stemmer,
    matcher: matcher,
    filter: filter
});

The example above is the standard interface which is at least exported from each charset/language.

You can also define the encoder directly and left all other options:

import simple from "./dist/module/lang/latin/simple.js";

const index \= FlexSearch({
    encode: simple
});

#### Available Latin Encoders

1.  default
2.  simple
3.  balance
4.  advanced
5.  extra

You can assign a charset by passing the charset during initialization, e.g. `charset: "latin"` for the default charset encoder or `charset: "latin:soundex"` for a encoder variant.

#### Dialect / Slang

Language definitions (especially matchers) also could be used to normalize dialect and slang of a specific language.

### 2\. Language Packs: ES5 (Language Packs)

You need to make the charset and/or language definitions available by:

1.  All charset definitions are included in the `flexsearch.bundle.js` build by default, but no language-specific definitions are included
2.  You can load packages located in `/dist/lang/` (files refers to languages, folders are charsets)
3.  You can make a custom build

When loading language packs, make sure that the library was loaded before:

<script src\="dist/flexsearch.light.js"\></script\>
<script src\="dist/lang/latin/default.min.js"\></script\>
<script src\="dist/lang/en.min.js"\></script\>

When using the full "bundle" version the built-in latin encoders are already included and you just have to load the language file:

<script src\="dist/flexsearch.bundle.js"\></script\>
<script src\="dist/lang/en.min.js"\></script\>

Because you loading packs as external packages (non-ES6-modules) you have to initialize them by shortcuts:

const index \= FlexSearch({
    charset: "latin:soundex",
    lang: "en"
});

> Use the `charset:variant` notation to assign charset and its variants. When just passing the charset without a variant will automatically resolve as `charset:default`.

You can also override existing definitions, e.g.:

const index \= FlexSearch({
    charset: "latin",
    lang: "en",
    matcher: {}
});

> Passed definitions will **not** extend default definitions, they will replace them.

When you like to extend a definition just create a new language file and put in all the logic.

#### Encoder Variants

It is pretty straight forward when using an encoder variant:

<script src\="dist/flexsearch.light.js"\></script\>
<script src\="dist/lang/latin/advanced.min.js"\></script\>
<script src\="dist/lang/latin/extra.min.js"\></script\>
<script src\="dist/lang/en.min.js"\></script\>

When using the full "bundle" version the built-in latin encoders are already included and you just have to load the language file:

<script src\="dist/flexsearch.bundle.js"\></script\>
<script src\="dist/lang/en.min.js"\></script\>

const index\_advanced \= FlexSearch({
    charset: "latin:advanced"
});

const index\_extra \= FlexSearch({
    charset: "latin:extra"
});

### Partial Tokenizer

In FlexSearch you can't provide your own partial tokenizer, because it is a direct dependency to the core unit. The built-in tokenizer of FlexSearch splits each word into fragments by different patterns:

1.  strict (supports contextual index)
2.  forward
3.  reverse (including forward)
4.  full

### Language Processing Pipeline

This is the default pipeline provided by FlexSearch:

#### Custom Pipeline

At first take a look into the default pipeline in `src/common.js`. It is very simple and straight forward. The pipeline will process as some sort of inversion of control, the final encoder implementation has to handle charset and also language specific transformations. This workaround has left over from many tests.

Inject the default pipeline by e.g.:

this.pipeline(

    /\* string: \*/ str.toLowerCase(),
    /\* normalize: \*/ false,
    /\* split: \*/ split,
    /\* collapse: \*/ false
);

Use the pipeline schema from above to understand the iteration and the difference of pre-encoding and post-encoding. Stemmer and matchers needs to be applied after charset normalization but before language transformations, filters also.

Here is a good example of extending pipelines: `src/lang/latin/extra.js` → `src/lang/latin/advanced.js` → `src/lang/latin/simple.js`.

### How to contribute?

Search for your language in `src/lang/`, if it exists you can extend or provide variants (like dialect/slang). If the language doesn't exist create a new file and check if any of the existing charsets (e.g. latin) fits to your language. When no charset exist, you need to provide a charset as a base for the language.

A new charset should provide at least:

1.  `encode` A function which normalize the charset of a passed text content (remove special chars, lingual transformations, etc.) and **returns an array of separated words**. Also stemmer, matcher or stopword filter needs to be applied here. When the language has no words make sure to provide something similar, e.g. each chinese sign could also be a "word". Don't return the whole text content without split.
2.  `rtl` A boolean flag which indicates right-to-left encoding

Basically the charset needs just to provide an encoder function along with an indicator for right-to-left encoding:

export function encode(str){ return \[str\] }
export const rtl \= false;

Fuzzy-Search
------------

Fuzzysearch describes a basic concept of how making queries more tolerant. FlexSearch provides several methods to achieve fuzziness:

1.  Use a tokenizer: `forward`, `reverse` or `full`
2.  Don't forget to use any of the builtin encoder `simple` > `balance` > `advanced` > `extra` > `soundex` (sorted by fuzziness)
3.  Use one of the language specific presets e.g. `/lang/en.js` for en-US specific content
4.  Enable suggestions by passing the search option `suggest: true`

Additionally, you can apply custom `Mapper`, `Replacer`, `Stemmer`, `Filter` or by assigning a custom `normalize(str)`, `prepare(str)` or `finalize(arr)` function to the Encoder.

### Compare Fuzzy-Search Encoding

Original term which was indexed: "Struldbrugs"

Encoder:

`LatinExact`

`LatinDefault`

`LatinSimple`

`LatinBalance`

`LatinAdvanced`

`LatinExtra`

`LatinSoundex`

Index Size

3.1 Mb

1.9 Mb

1.8 Mb

1.7 Mb

1.6 Mb

1.1 Mb

0.7 Mb

Struldbrugs

✓

✓

✓

✓

✓

✓

✓

struldbrugs

✓

✓

✓

✓

✓

✓

strũldbrųĝgs

✓

✓

✓

✓

✓

strultbrooks

✓

✓

✓

✓

shtruhldbrohkz

✓

✓

✓

zdroltbrykz

✓

✓

struhlbrogger

✓

The index size was measured after indexing the book "Gulliver's Travels".

Memory Allocation
-----------------

The book "Gulliver's Travels Swift Jonathan 1726" was fully indexed for the examples below.

The most memory-optimized meaningful setting will allocate just 1.2 Mb for the whole book indexed! This is probably the most tiny memory footprint you will get from a search library.

import { encode } from "./lang/latin/extra.js";

index \= new Index({
    encode: encode,
    tokenize: "strict",
    optimize: true,
    resolution: 1,
    minlength: 3,
    fastupdate: false,
    context: false
});

### Memory Consumption

The book "Gulliver's Travels" (Swift Jonathan 1726) was completely indexed for this test:

### Compare Impact of Memory Allocation

by default a lexical index is very small:  
`depth: 0, bidirectional: 0, resolution: 3, minlength: 0` => 2.1 Mb

a higher resolution will increase the memory allocation:  
`depth: 0, bidirectional: 0, resolution: 9, minlength: 0` => 2.9 Mb

using the contextual index will increase the memory allocation:  
`depth: 1, bidirectional: 0, resolution: 9, minlength: 0` => 12.5 Mb

a higher contextual depth will increase the memory allocation:  
`depth: 2, bidirectional: 0, resolution: 9, minlength: 0` => 21.5 Mb

a higher minlength will decrease memory allocation:  
`depth: 2, bidirectional: 0, resolution: 9, minlength: 3` => 19.0 Mb

using bidirectional will decrease memory allocation:  
`depth: 2, bidirectional: 1, resolution: 9, minlength: 3` => 17.9 Mb

enable the option "fastupdate" will increase memory allocation:  
`depth: 2, bidirectional: 1, resolution: 9, minlength: 3` => 6.3 Mb

Presets
-------

1.  `memory` (primary optimize for memory)
2.  `performance` (primary optimize for performance)
3.  `match` (primary optimize for matching)
4.  `score` (primary optimize for scoring)
5.  `default` (the default balanced profile)

These profiles are covering standard use cases. It is recommended to apply custom configuration instead of using profiles to get the best out for your situation. Every profile could be optimized further to its specific task, e.g. extreme performance optimized configuration or extreme memory and so on.

You can pass a preset during creation/initialization of the index.

Best Practices
--------------

### Use numeric IDs

It is recommended to use numeric id values as reference when adding content to the index. The byte length of passed ids influences the memory consumption significantly. If this is not possible you should consider to use a index table and map the ids with indexes, this becomes important especially when using contextual indexes on a large amount of content.

* * *

Copyright 2018-2025 Thomas Wilkerling, Hosted by Nextapps GmbH  
Released under the Apache 2.0 License
