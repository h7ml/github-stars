---
project: flexsearch
stars: 12588
description: Next-Generation full text search library for Browser and Node.js
url: https://github.com/nextapps-de/flexsearch
---

Let's discuss the upcoming FlexSearch v0.8 here: #415

==

### Web's fastest and most memory-flexible full-text search library with zero dependencies.

Basic Start  •  API Reference  •  Document Indexes  •  Using Worker  •  Changelog

Support this Project
--------------------

You can help me by making a personal donation to keep this project alive and also to provide all the contribution to solve your needs.

### Sponsors

  
Antithesis Operations LLC

When it comes to raw search speed FlexSearch outperforms every single searching library out there and also provides flexible search capabilities like multi-field search, phonetic transformations or partial matching.

Depending on the used options it also provides the most memory-efficient index. FlexSearch introduce a new scoring algorithm called "contextual index" based on a pre-scored lexical dictionary architecture which actually performs queries up to 1,000,000 times faster compared to other libraries. FlexSearch also provides you a non-blocking asynchronous processing model as well as web workers to perform any updates or queries on the index in parallel through dedicated balanced threads.

Supported Platforms:

-   Browser
-   Node.js

Library Comparison "Gulliver's Travels":

-   Performance Benchmark
-   Scoring Benchmark
-   Memory Consumption

Plugins (extern projects):

-   React: https://github.com/angeloashmore/react-use-flexsearch
-   Vue: https://github.com/Noction/vue-use-flexsearch
-   Gatsby: https://www.gatsbyjs.org/packages/gatsby-plugin-flexsearch/

### Get Latest

Build

File

CDN

flexsearch.bundle.js

Download

https://rawcdn.githack.com/nextapps-de/flexsearch/0.7.31/dist/flexsearch.bundle.js

flexsearch.light.js

Download

https://rawcdn.githack.com/nextapps-de/flexsearch/0.7.31/dist/flexsearch.light.js

flexsearch.compact.js

Download

https://rawcdn.githack.com/nextapps-de/flexsearch/0.7.31/dist/flexsearch.compact.js

flexsearch.es5.js \*

Download

https://rawcdn.githack.com/nextapps-de/flexsearch/0.7.31/dist/flexsearch.es5.js

ES6 Modules

Download

The _/dist/module/_ folder of this Github repository

\* The bundle "flexsearch.es5.js" includes polyfills for EcmaScript 5 Support.

#### Get Latest (NPM)

npm install flexsearch

### Compare Web-Bundles

> The Node.js package includes all features from `flexsearch.bundle.js`.

Feature

flexsearch.bundle.js

flexsearch.compact.js

flexsearch.light.js

Presets

✓

✓

\-

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

Index Documents (Field-Search)

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

Auto-Balanced Cache by Popularity

✓

\-

\-

Tags

✓

\-

\-

Suggestions

✓

✓

\-

Phonetic Matching

✓

✓

\-

Customizable Charset/Language (Matcher, Encoder, Tokenizer, Stemmer, Filter, Split, RTL)

✓

✓

✓

Export / Import Indexes

✓

\-

\-

File Size (gzip)

6.8 kb

5.3 kb

2.9 kb

Performance Benchmark (Ranking)
-------------------------------

Run Comparison: Performance Benchmark "Gulliver's Travels"

Operation per seconds, higher is better, except the test "Memory" on which lower is better.

Rank

Library

Memory

Query (Single Term)

Query (Multi Term)

Query (Long)

Query (Dupes)

Query (Not Found)

1

FlexSearch

**17**

**7084129**

**1586856**

**511585**

**2017142**

3202006

2

JSii

27

6564

158149

61290

95098

534109

3

Wade

424

20471

78780

16693

225824

213754

4

JS Search

193

8221

64034

10377

95830

167605

5

Elasticlunr.js

646

5412

7573

2865

23786

13982

6

BulkSearch

1021

3069

3141

3333

3265

**21825569**

7

MiniSearch

24348

4406

10945

72

39989

17624

8

bm25

15719

1429

789

366

884

1823

9

Lunr.js

2219

255

271

272

266

267

10

FuzzySearch

157373

53

38

15

32

43

11

Fuse

7641904

6

2

1

2

3

Load Library
------------

There are 3 types of indexes:

1.  `Index` is a flat high performance index which stores id-content-pairs.
2.  `Worker` / `WorkerIndex` is also a flat index which stores id-content-pairs but runs in background as a dedicated worker thread.
3.  `Document` is multi-field index which can store complex JSON documents (could also exist of worker indexes).

The most of you probably need just one of them according to your scenario.

### Browser

#### Legacy ES5 Script Tag (Bundled)

<script src\="node\_modules/flexsearch/dist/flexsearch.bundle.min.js"\></script\>
<script\>

    // FlexSearch is available on window.FlexSearch
    // Access FlexSearch static methods via bundled export (static class methods of FlexSearch)

    const index \= FlexSearch.Index(options);
    const document \= FlexSearch.Document(options);
    const worker \= FlexSearch.Worker(options);

</script\>

#### ESM/ES6 Modules:

<script type\="module"\>

    // FlexSearch is NOT available on window.FlexSearch
    // Access FlexSearch static methods by importing them explicitly

    import Index from "./node\_modules/flexsearch/dist/module/index";
    import Document from "./node\_modules/flexsearch/dist/module/document";
    import Worker from "./node\_modules/flexsearch/dist/module/worker";

    const index \= new Index(options);
    const document \= new Document(options);
    const worker \= new Worker(options);

</script\>

#### ESM/ES6 Bundled Module:

<script type\="module"\>

    // FlexSearch is NOT available on window.FlexSearch
    // Access FlexSearch static methods via bundled export (static class methods of FlexSearch)

    import FlexSearch from "./node\_modules/flexsearch/dist/flexsearch.bundle.module.min.js";

    const index \= FlexSearch.Index(options);
    const document \= FlexSearch.Document(options);
    const worker \= FlexSearch.Worker(options);

</script\>

Or via CDN:

<script src\="https://cdn.jsdelivr.net/gh/nextapps-de/flexsearch@0.7.41/dist/flexsearch.bundle.min.js"\></script\>

AMD / CommonJS:

var FlexSearch \= require("./node\_modules/flexsearch/dist/flexsearch.bundle.min.js");

### Node.js

```
npm install flexsearch
```

In your code include as follows:

const { Index, Document, Worker } \= require("flexsearch");

const index \= new Index(options);
const document \= new Document(options);
const worker \= new Worker(options);

Or:

const FlexSearch \= require("flexsearch");

const index \= new FlexSearch.Index(options);
const document \= new FlexSearch.Document(options);
const worker \= new FlexSearch.Worker(options);

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

Append Contents
---------------

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

        return str.split(/\\s-\\//g);
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
    encode: str \=> str.toLowerCase().split(/\[^a-z\]+/),
    tokenize: "reverse",
    rtl: true
});

### CJK Word Break (Chinese, Japanese, Korean)

Set a custom tokenizer which fits your needs, e.g.:

var index \= FlexSearch.create({
    encode: str \=> str.replace(/\[\\x00-\\x7F\]/g, "").split("")
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

Export / Import
---------------

### Export

The export has slightly changed. The export now consist of several smaller parts, instead of just one large bulk. You need to pass a callback function which has 2 arguments "key" and "data". This callback function is called by each part, e.g.:

index.export(function(key, data){ 
    
    // you need to store both the key and the data!
    // e.g. use the key for the filename and save your data
    
    localStorage.setItem(key, data);
});

Exporting data to the localStorage isn't really a good practice, but if size is not a concern than use it if you like. The export primarily exists for the usage in Node.js or to store indexes you want to delegate from a server to the client.

> The size of the export corresponds to the memory consumption of the library. To reduce export size you have to use a configuration which has less memory footprint (use the table at the bottom to get information about configs and its memory allocation).

When your save routine runs asynchronously you have to return a promise:

index.export(function(key, data){ 
    
    return new Promise(function(resolve){
        
        // do the saving as async

        resolve();
    });
});

> You cannot export the additional table for the "fastupdate" feature. These table exists of references and when stored they fully get serialized and becomes too large. The lib will handle these automatically for you. When importing data, the index automatically disables "fastupdate".

### Import

Before you can import data, you need to create your index first. For document indexes provide the same document descriptor you used when export the data. This configuration isn't stored in the export.

var index \= new Index({ ... });

To import the data just pass a key and data:

index.import(key, localStorage.getItem(key));

You need to import every key! Otherwise, your index does not work. You need to store the keys from the export and use this keys for the import (the order of the keys can differ).

This is just for demonstration and is not recommended, because you might have other keys in your localStorage which aren't supported as an import:

var keys \= Object.keys(localStorage);

for(let i \= 0, key; i < keys.length; i++){
    
    key \= keys\[i\];
    index.import(key, localStorage.getItem(key));
}

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

Encoder Matching Comparison
---------------------------

> Reference String: **"Björn-Phillipp Mayer"**

Query

default

simple

advanced

extra

björn

**yes**

**yes**

**yes**

**yes**

björ

**yes**

**yes**

**yes**

**yes**

bjorn

no

**yes**

**yes**

**yes**

bjoern

no

no

**yes**

**yes**

philipp

no

no

**yes**

**yes**

filip

no

no

**yes**

**yes**

björnphillip

no

**yes**

**yes**

**yes**

meier

no

no

**yes**

**yes**

björn meier

no

no

**yes**

**yes**

meier fhilip

no

no

**yes**

**yes**

byorn mair

no

no

no

**yes**

_(false positives)_

**no**

**no**

**no**

yes

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

### Full Comparison Table

Every search library is constantly in competition with these 4 properties:

1.  Memory Allocation
2.  Performance
3.  Matching Capabilities
4.  Relevance Order (Scoring)

FlexSearch provides you many parameters you can use to adjust the optimal balance for your specific use-case.

Modifier

Memory Impact \*

Performance Impact \*\*

Matching Impact \*\*

Scoring Impact \*\*

resolution

+1 (per level)

+1 (per level)

0

+2 (per level)

depth

+4 (per level)

\-1 (per level)

\-10 + depth

+10

minlength

\-2 (per level)

+2 (per level)

\-3 (per level)

+2 (per level)

bidirectional

\-2

0

+3

\-1

fastupdate

+1

+10 (update, remove)

0

0

optimize: true

\-7

\-1

0

\-3

encoder: "icase"

0

0

0

0

encoder: "simple"

\-2

\-1

+2

0

encoder: "advanced"

\-3

\-2

+4

0

encoder: "extra"

\-5

\-5

+6

0

encoder: "soundex"

\-6

\-2

+8

0

tokenize: "strict"

0

0

0

0

tokenize: "forward"

+3

\-2

+5

0

tokenize: "reverse"

+5

\-4

+7

0

tokenize: "full"

+8

\-5

+10

0

document index

+3 (per field)

\-1 (per field)

0

0

document tags

+1 (per tag)

\-1 (per tag)

0

0

store: true

+5 (per document)

0

0

0

store: \[fields\]

+1 (per field)

0

0

0

cache: true

+10

+10

0

0

cache: 100

+1

+9

0

0

type of ids: number

0

0

0

0

type of ids: string

+3

\-3

0

0

\* range from -10 to 10, lower is better (-10 => big decrease, 0 => unchanged, +10 => big increase)  
\*\* range from -10 to 10, higher is better

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

##### Use numeric IDs

It is recommended to use numeric id values as reference when adding content to the index. The byte length of passed ids influences the memory consumption significantly. If this is not possible you should consider to use a index table and map the ids with indexes, this becomes important especially when using contextual indexes on a large amount of content.

##### Split Complexity

Whenever you can, try to divide content by categories and add them to its own index, e.g.:

var action \= new FlexSearch();
var adventure \= new FlexSearch();
var comedy \= new FlexSearch();

This way you can also provide different settings for each category. This is actually the fastest way to perform a fuzzy search.

To make this workaround more extendable you can use a short helper:

var index \= {};

function add(id, cat, content){
    (index\[cat\] || (
        index\[cat\] \= new FlexSearch
    )).add(id, content);
}

function search(cat, query){
    return index\[cat\] ?
        index\[cat\].search(query) : \[\];
}

Add content to the index:

add(1, "action", "Movie Title");
add(2, "adventure", "Movie Title");
add(3, "comedy", "Movie Title");

Perform queries:

var results \= search("action", "movie title"); // --> \[1\]

Split indexes by categories improves performance significantly.

* * *

Copyright 2018-2023 Thomas Wilkerling, Hosted by Nextapps GmbH  
Released under the Apache 2.0 License
