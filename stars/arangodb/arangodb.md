---
project: arangodb
stars: 13899
description: 🥑 ArangoDB is a native multi-model database with flexible data models for documents, graphs, and key-values. Build high performance applications using a convenient SQL-like query language or JavaScript extensions.
url: https://github.com/arangodb/arangodb
---

ArangoDB
========

ArangoDB is a scalable graph database system to drive value from connected data, faster. Native graphs, an integrated search engine, and JSON support, via a single query language. ArangoDB runs on-prem, in the cloud – anywhere.

ArangoDB Cloud Service
----------------------

The ArangoGraph Insights Platform is the simplest way to run ArangoDB. You can create deployments on all major cloud providers in many regions with ease.

Getting Started
---------------

-   ArangoDB University
-   Free Udemy Course
-   Training Center
-   Documentation

For the impatient:

-   Test ArangoDB in the cloud with ArangoGraph for free.
    
-   Alternatively, download and install ArangoDB. Start the server `arangod` if the installer did not do it for you.
    
    Or start ArangoDB in a Docker container:
    
    ```
    docker run -e ARANGO_ROOT_PASSWORD=test123 -p 8529:8529 -d arangodb
    ```
    
    Then point your browser to `http://127.0.0.1:8529/`.
    

Key Features of ArangoDB
------------------------

**Native Graph** - Store both data and relationships, for faster queries even with multiple levels of joins and deeper insights that simply aren't possible with traditional relational and document database systems.

**Document Store** - Every node in your graph is a JSON document: flexible, extensible, and easily imported from your existing document database.

**ArangoSearch** - Natively integrated cross-platform indexing, text-search and ranking engine for information retrieval, optimized for speed and memory.

ArangoDB is available in a free and fully featured **Community Edition** as well as an **Enterprise Edition** for commercial use and without a dataset size limit.

### Core Features

-   **Horizontal scalability**: Seamlessly shard your data across multiple machines.
-   **High availability** and **resilience**: Replicate data to multiple cluster nodes, with automatic failover.
-   **Flexible data modeling**: Model your data as combination of key-value pairs, documents, and graphs as you see fit for your application.
-   Work **schema-free** or use **schema validation** for data consistency. Store any type of data - date/time, geo-spatial, text, nested.
-   **Powerful query language** (_AQL_) to retrieve and modify data - from simple CRUD operations, over complex filters and aggregations, all the way to joins, graphs, and ranked full-text search.
-   **Transactions**: Run queries on multiple documents or collections with optional transactional consistency and isolation.
-   **Data-centric microservices**: Unify your data storage logic, reduce network overhead, and secure sensitive data with the _ArangoDB Foxx_ JavaScript framework.
-   **Fast access to your data**: Fine-tune your queries with a variety of index types for optimal performance. ArangoDB is written in C++ and can handle even very large datasets efficiently.
-   Easy to use **web interface** and **command-line tools** for interaction with the server.

### Scalability Features

Focus on solving enterprise-scale problems for mission critical workloads using secure graph data. ArangoDB offers special features for performance, compliance, and security, as well as advanced query capabilities.

-   Smartly shard and replicate graphs and datasets with features like **EnterpriseGraphs**, **SmartGraphs**, and **SmartJoins** for lightning fast query execution.
-   Combine the performance of a single server with the resilience of a cluster setup using **OneShard** deployments.
-   Increase fault tolerance with **Datacenter-to-Datacenter Replication** and and create incremental **Hot Backups** without downtime.
-   Enable highly secure work with **Encryption 360**, enhanced **Data Masking**, and detailed **Auditing**.
-   Perform **parallel graph traversals**.
-   Use ArangoSearch **search highlighting** and **nested search** for advanced information retrieval.

Latest Release
--------------

Packages for all supported platforms can be downloaded from https://www.arangodb.com/download/.

For what's new in ArangoDB, see the Release Notes in the Documentation.

Stay in Contact
---------------

-   Please use GitHub for feature requests and bug reports: https://github.com/arangodb/arangodb/issues
    
-   Ask questions about AQL, usage scenarios, etc. on StackOverflow: https://stackoverflow.com/questions/tagged/arangodb
    
-   Chat with the community and the developers on Slack: https://arangodb-community.slack.com/
    
-   Learn more about ArangoDB with our YouTube channel: https://www.youtube.com/@ArangoDB
    
-   Follow us on Twitter to stay up to date: https://twitter.com/arangodb
    
-   Find out more about our community: https://www.arangodb.com/community
