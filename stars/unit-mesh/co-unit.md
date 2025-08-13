---
project: co-unit
stars: 30
description: CoUnit，一个基于 LLM 的虚拟团队接口人（API），通过向量化文档、知识库、SDK和 API 等，结合 LLM 智能化团队间对接与协作。Merge artificial intelligence seamlessly with team collaboration. Leverage intelligent vectorization to process documents, knowledge bases, SDKs, and APIs, empowering teams to unleash their creativity.
url: https://github.com/unit-mesh/co-unit
---

CoUnit
======

> CoUnit，一个基于 LLM 的虚拟团队接口人（API），通过向量化文档、知识库、SDK和 API 等，结合 LLM 智能化团队间对接与协作。

todos:

-   Semantic search for Team API
    -   ArchGuard API：Code, DatabaseMap, HTTP API
    -   Query for OpenAPI
    -   Documents
        -   Markdown
        -   PDF
-   Transpile / Translate language
    -   Unique language (aka Domain Language) dictionary
    -   Transpile for Code, Datamap, API
-   Prompt strategy
    -   HyDE
    -   Jieba.rs + StarDict spike
    -   Small LLM spike

CoUnit Prompt Strategy

Uses
----

1.  Download CoUnit-Server binary from https://github.com/unit-mesh/co-unit/releases
2.  push you `domain language` or config under `domain` directory (support, `.csv` and `.json` format)
3.  Run CoUnit-Server

Domain Language:

native

english

abbreviation

description

CoUnit

collaboration unit

CU

CoUnit，一个基于 LLM 的虚拟团队接口人（API），通过向量化文档、知识库、SDK和 API 等，结合 LLM 智能化团队间对接与协作。

大语言模型

Large Language Model

LLM

大语言模型，是指语言模型的参数量超过 10 亿的语言模型。

Use cases
---------

-   AutoDev -> code: counit.

Development
-----------

Tech stacks:

-   Rust, a language empowering everyone to build reliable and efficient software.
-   Frameworks:
    -   Axum, Ergonomic and modular web framework built with Tokio, Tower, and Hyper
-   Infrastructure:
    -   Qdrant, Vector similarity search engine
    -   Ort, ONNX Runtime is a performance-focused complete scoring engine for Open Neural Network Exchange (ONNX) models.
    -   Tokenizers, Fast State-of-the-Art Tokenizers optimized for Research and Production.

Setup:

1.  Install Rust
2.  Clone this repo: `git clone https://github.com/unit-mesh/co-unit`
3.  install Qdrant by Docker:

docker pull qdrant/qdrant
docker run -p 6333:6333 -p 6334:6334 \\
    -e QDRANT\_\_SERVICE\_\_GRPC\_PORT="6334" \\
    qdrant/qdrant

4.Run CoUnit-Server.

### API testing

use counit-server.http to test API.

Integration example with ArchGuard and AutoDev
----------------------------------------------

AutoDev: https://github.com/unit-mesh/auto-dev

ArchGuard: https://github.com/archguard/archguard

Full processes:

1.  Download ArchGuard CLI (scanner\_cli-2.0.x-all.jar) from: \[https://github.com/archguard/archguard/releases\]
2.  Run ArchGuard CLI to upload data to Co-Unit:

Usage: runner \[OPTIONS\]

  scanner cli

Options:
  --type \[SOURCE\_CODE|GIT|DIFF\_CHANGES|SCA|RULE|ARCHITECTURE|ESTIMATE|OPENAPI\]
  --system-id TEXT                 system id
  --server-url TEXT                the base url of the archguard api server
  --workspace TEXT                 the workspace directory
  --path TEXT                      the path of target project
  --output TEXT                    http, csv, json, console
  --output-dir TEXT                output directory
  --analyser-spec TEXT             Override the analysers via json.
  --slot-spec TEXT                 Override the slot via json.
  --language TEXT                  language: Java, Kotlin, TypeScript, CSharp,
                                   Python, Golang.
  --rules TEXT                     rules: webapi, test, sql
  --features TEXT                  features: apicalls, datamap.
  --repo-id TEXT                   repository id used for git analysing
  --branch TEXT                    repository branch
  --started-at INT                 TIMESTAMP, the start date of the scanned
                                   commit
  --since TEXT                     COMMIT ID, the specific revision of the
                                   baseline
  --until TEXT                     COMMIT ID, the specific revision of the
                                   target
  --depth INT                      INTEGER, the max loop depth
  --with-function-code             BOOLEAN, whether to include the function
                                   code
  -h, --help                       Show this message and exit

For example:

java -jar scanner\_cli-2.0.6-all.jar --language=Kotlin --path=your\_path\_to\_code --server-url=http://localhost:8765 --repo-id="archguard" --with-function-code --output=http  --features=apicalls

OpenAPI example:

java -jar scanner\_cli-2.0.6-all.jar --language=Kotlin --path=your\_swagger\_3\_file --server-url=http://localhost:8765 --repo-id="payment" --output=http --type=OPENAPI 

#### ArchGuard APIs:

\### ArchGuard Code datastrcuture
POST http://127.0.0.1:8765/scanner/:systemId/reporting/class-items

\### ArchGuard OpenAPI structure
POST http://127.0.0.1:8765/scanner/:systemId/reporting/openapi

\### ArchGuard Service Datamap
POST http://127.0.0.1:8765/scanner/:systemId/reporting/container-services

\### ArchGuard Datamap 
POST http://127.0.0.1:8765/scanner/:systemId/reporting/datamap-relations

License
-------

The Co-Unit index is licensed under the Apache 2.0 license based on https://github.com/BloopAI/bloop . See `LICENSE` in counit-index.

This code is distributed under the MPL 2.0 license. See `LICENSE` in this directory.
