---
project: llama_index
stars: 44896
description: LlamaIndex is the leading framework for building LLM-powered agents over your data.
url: https://github.com/run-llama/llama_index
---

🗂️ LlamaIndex 🦙
=================

LlamaIndex (GPT Index) is a data framework for your LLM application. Building with LlamaIndex typically involves working with LlamaIndex core and a chosen set of integrations (or plugins). There are two ways to start building with LlamaIndex in Python:

1.  **Starter**: `llama-index`. A starter Python package that includes core LlamaIndex as well as a selection of integrations.
    
2.  **Customized**: `llama-index-core`. Install core LlamaIndex and add your chosen LlamaIndex integration packages on LlamaHub that are required for your application. There are over 300 LlamaIndex integration packages that work seamlessly with core, allowing you to build with your preferred LLM, embedding, and vector store providers.
    

The LlamaIndex Python library is namespaced such that import statements which include `core` imply that the core package is being used. In contrast, those statements without `core` imply that an integration package is being used.

\# typical pattern
from llama\_index.core.xxx import ClassABC  \# core submodule xxx
from llama\_index.xxx.yyy import (
    SubclassABC,
)  \# integration yyy for submodule xxx

\# concrete example
from llama\_index.core.llms import LLM
from llama\_index.llms.openai import OpenAI

### Important Links

LlamaIndex.TS (Typescript/Javascript)

Documentation

X (formerly Twitter)

LinkedIn

Reddit

Discord

### Ecosystem

-   LlamaHub (community library of data loaders)
-   LlamaLab (cutting-edge AGI projects using LlamaIndex)

🚀 Overview
-----------

**NOTE**: This README is not updated as frequently as the documentation. Please check out the documentation above for the latest updates!

### Context

-   LLMs are a phenomenal piece of technology for knowledge generation and reasoning. They are pre-trained on large amounts of publicly available data.
-   How do we best augment LLMs with our own private data?

We need a comprehensive toolkit to help perform this data augmentation for LLMs.

### Proposed Solution

That's where **LlamaIndex** comes in. LlamaIndex is a "data framework" to help you build LLM apps. It provides the following tools:

-   Offers **data connectors** to ingest your existing data sources and data formats (APIs, PDFs, docs, SQL, etc.).
-   Provides ways to **structure your data** (indices, graphs) so that this data can be easily used with LLMs.
-   Provides an **advanced retrieval/query interface over your data**: Feed in any LLM input prompt, get back retrieved context and knowledge-augmented output.
-   Allows easy integrations with your outer application framework (e.g. with LangChain, Flask, Docker, ChatGPT, or anything else).

LlamaIndex provides tools for both beginner users and advanced users. Our high-level API allows beginner users to use LlamaIndex to ingest and query their data in 5 lines of code. Our lower-level APIs allow advanced users to customize and extend any module (data connectors, indices, retrievers, query engines, reranking modules), to fit their needs.

💡 Contributing
---------------

Interested in contributing? Contributions to LlamaIndex core as well as contributing integrations that build on the core are both accepted and highly encouraged! See our Contribution Guide for more details.

New integrations should meaningfully integrate with existing LlamaIndex framework components. At the discretion of LlamaIndex maintainers, some integrations may be declined.

📄 Documentation
----------------

Full documentation can be found here

Please check it out for the most up-to-date tutorials, how-to guides, references, and other resources!

💻 Example Usage
----------------

# custom selection of integrations to work with core
pip install llama-index-core
pip install llama-index-llms-openai
pip install llama-index-llms-replicate
pip install llama-index-embeddings-huggingface

Examples are in the `docs/examples` folder. Indices are in the `indices` folder (see list of indices below).

To build a simple vector store index using OpenAI:

import os

os.environ\["OPENAI\_API\_KEY"\] \= "YOUR\_OPENAI\_API\_KEY"

from llama\_index.core import VectorStoreIndex, SimpleDirectoryReader

documents \= SimpleDirectoryReader("YOUR\_DATA\_DIRECTORY").load\_data()
index \= VectorStoreIndex.from\_documents(documents)

To build a simple vector store index using non-OpenAI LLMs, e.g. Llama 2 hosted on Replicate, where you can easily create a free trial API token:

import os

os.environ\["REPLICATE\_API\_TOKEN"\] \= "YOUR\_REPLICATE\_API\_TOKEN"

from llama\_index.core import Settings, VectorStoreIndex, SimpleDirectoryReader
from llama\_index.embeddings.huggingface import HuggingFaceEmbedding
from llama\_index.llms.replicate import Replicate
from transformers import AutoTokenizer

\# set the LLM
llama2\_7b\_chat \= "meta/llama-2-7b-chat:8e6975e5ed6174911a6ff3d60540dfd4844201974602551e10e9e87ab143d81e"
Settings.llm \= Replicate(
    model\=llama2\_7b\_chat,
    temperature\=0.01,
    additional\_kwargs\={"top\_p": 1, "max\_new\_tokens": 300},
)

\# set tokenizer to match LLM
Settings.tokenizer \= AutoTokenizer.from\_pretrained(
    "NousResearch/Llama-2-7b-chat-hf"
)

\# set the embed model
Settings.embed\_model \= HuggingFaceEmbedding(
    model\_name\="BAAI/bge-small-en-v1.5"
)

documents \= SimpleDirectoryReader("YOUR\_DATA\_DIRECTORY").load\_data()
index \= VectorStoreIndex.from\_documents(
    documents,
)

To query:

query\_engine \= index.as\_query\_engine()
query\_engine.query("YOUR\_QUESTION")

By default, data is stored in-memory. To persist to disk (under `./storage`):

index.storage\_context.persist()

To reload from disk:

from llama\_index.core import StorageContext, load\_index\_from\_storage

\# rebuild storage context
storage\_context \= StorageContext.from\_defaults(persist\_dir\="./storage")
\# load index
index \= load\_index\_from\_storage(storage\_context)

🔧 Dependencies
---------------

We use poetry as the package manager for all Python packages. As a result, the dependencies of each Python package can be found by referencing the `pyproject.toml` file in each of the package's folders.

cd <desired-package-folder\>
pip install poetry
poetry install --with dev

A note on Verification of Build Assets
--------------------------------------

By default, `llama-index-core` includes a `_static` folder that contains the nltk and tiktoken cache that is included with the package installation. This ensures that you can easily run `llama-index` in environments with restrictive disk access permissions at runtime.

To verify that these files are safe and valid, we use the github `attest-build-provenance` action. This action will verify that the files in the `_static` folder are the same as the files in the `llama-index-core/llama_index/core/_static` folder.

To verify this, you can run the following script (pointing to your installed package):

#!/bin/bash
STATIC\_DIR="venv/lib/python3.13/site-packages/llama\_index/core/\_static"
REPO="run-llama/llama\_index"

find "$STATIC\_DIR" -type f | while read -r file; do
    echo "Verifying: $file"
    gh attestation verify "$file" -R "$REPO" || echo "Failed to verify: $file"
done

📖 Citation
-----------

Reference to cite if you use LlamaIndex in a paper:

```
@software{Liu_LlamaIndex_2022,
author = {Liu, Jerry},
doi = {10.5281/zenodo.1234},
month = {11},
title = {{LlamaIndex}},
url = {https://github.com/jerryjliu/llama_index},
year = {2022}
}
```
