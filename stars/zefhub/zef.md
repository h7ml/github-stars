---
project: zef
stars: 117
description: Toolkit for graph-relational data across space and time
url: https://github.com/zefhub/zef
---

A data-oriented toolkit for graph data

_versioned graphs + streams + query using Python + GraphQL_

  
  
Docs   |   ZefHub

  
  

  

Description
-----------

Zef is an open source, data-oriented toolkit for graph data. It combines the access speed and local development experience of an in-memory data structure with the power of a fully versioned, immutable database (and distributed persistence if needed with ZefHub). Furthermore, Zef includes a library of composable functional operators, effects handling, and native GraphQL support. You can pick and choose what you need for your project.

If any of these apply to you, Zef might help:

-   I need a graph database with fast query speeds and hassle-free infra
-   I need a graph data model that's more powerful than NetworkX but easier than Neo4j
-   I need to "time travel" and access past states easily
-   I like Datomic but prefer something open source that feels like working with local data structures
-   I would prefer querying and traversing directly in Python, rather than a query language (like Cypher or GSQL)
-   I need a GraphQL API that's easy to spin up and close to my data model

  
  

Features
--------

-   a graph language you can use directly in Python code
-   fully versioned graphs
-   in-memory access speeds
-   free and real-time data persistence (via ZefHub)
-   work with graphs like local data structures
-   no separate query language
-   no ORM
-   GraphQL API with low impedance mismatch to data model
-   data streams and subscriptions

  
  

Status
------

Zef is currently in Public Alpha.

-   Private Alpha: Testing Zef internally and with a closed group of users.
-   Public Alpha: Anyone can use Zef but please be patient with very large graphs!
-   Public Beta: Stable enough for most non-enterprise use cases.
-   Public: Stable for all production use cases.

  
  

Installation
------------

The platforms we currently support are 64-bit Linux and MacOS. The latest version can be installed via the PyPI repository using:

pip install zef

This will attempt to install a wheel if supported by your system and compile from source otherwise. See INSTALL for more details if compiling from source.

Check out our installation doc for more details about getting up and running once installed.

  
  

Using Zef
---------

Here's some quick points to get going. Check out our Quick Start and docs for more details.

A quick note, in Zef, we overloaded the "|" pipe so users can chain together values, Zef operators (ZefOps), and functions in sequential, lazy, and executable pipelines where data flow is left to right.

  

### 💆 Get started 💆

from zef import \*          \# these imports unlock user friendly syntax and powerful Zef operators (ZefOps)
from zef.ops import \*

g \= Graph()                \# create an empty graph

  

### 🌱 Add some data 🌱

p1 \= ET.Person | g | run                  \# add an entity to the graph

(p1, RT.FirstName, "Yolandi") | g | run   \# add "fields" via relations triples: (source, relation, target)

  

### 🐾 Traverse the graph 🐾

p1 | out\_rel\[RT.FirstName\]   \# one hop: step onto the relation

p1 | Out\[RT.FirstName\]       \# two hops: step onto the target

  

### ⏳ Time travel ⌛

p1 | time\_travel\[\-2\]                                        \# move reference frame back two time slices

p1 | time\_travel\[Time('2023 January 1 12:34:56 (+0100)')\]   \# move to a specific date and time

  

### 👐 Share with other users (via ZefHub) 👐

g | sync\[True\] | run                            \# save and sync all future changes on ZefHub

\# ---------------- Python Session A (You) -----------------
g | uid | to\_clipboard | run                    \# copy uid onto local clipboard

\# ---------------- Python Session B (Friend) -----------------
graph\_uid: str \= '...'                          \# uid copied from Slack/WhatsApp/email/etc
g \= Graph(graph\_uid)
g | now | all\[ET\] | collect                     \# see all entities in the latest time slice

  

### 🚣 Choose your own adventure 🚣

-   Basic tutorial of Zef
-   Build Wordle clone with Zef
-   Import data from CSV
-   Import data from NetworkX
-   Set up a GraphQL API
-   Use Zef graphs in NetworkX

  

### 📌 A note on ZefHub 📌

Zef is designed so you can use it locally and drop it into any existing project. You have the option of syncing your graphs with ZefHub, a service that persists, syncs, and distributes graphs automatically (and the company behind Zef). ZefHub makes it possible to share graphs with other users and see changes live, by memory mapping across machines in real-time!

You can create a ZefHub account for free which gives you full access to storing and sharing graphs forever. For full transparency, our long-term hope is that many users will get value from Zef or Zef + ZefHub for free, while ZefHub power users will pay a fee for added features and services.

  
  

Roadmap
-------

We want to make it incredibly easy for developers to build fully distributed, reactive systems with consistent data and cross-language (Python, C++, Julia) support. If there's sufficient interest, we'd be happy to share a public board of items we're working on.

  
  

Contributing
------------

Thank you for considering contributing to Zef! We know your time is valuable and your input makes Zef better for all current and future users.

To optimize for feedback speed, please raise bugs or suggest features directly in our community chat https://zef.chat.

Please refer to our CONTRIBUTING file and CODE\_OF\_CONDUCT file for more details.

  
  

License
-------

Zef is licensed under the Apache License, Version 2.0 (the "License"). You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

  
  

Dependencies
------------

The compiled libraries make use of the following packages:

-   `asio` (https://github.com/chriskohlhoff/asio)
-   `JWT++` (https://github.com/Thalhammer/jwt-cpp)
-   `Curl` (https://github.com/curl/curl)
-   `JSON` (https://github.com/nlohmann/json)
-   `Parallel hashmap` (https://github.com/greg7mdp/parallel-hashmap)
-   `Ranges-v3` (https://github.com/ericniebler/range-v3)
-   `Websocket++` (https://github.com/zaphoyd/websocketpp)
-   `Zstandard` (https://github.com/facebook/zstd)
-   `pybind11` (https://github.com/pybind/pybind11)
-   `pybind_json` (https://github.com/pybind/pybind11\_json)
