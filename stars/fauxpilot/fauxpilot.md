---
project: fauxpilot
stars: 14740
description: FauxPilot - an open-source alternative to GitHub Copilot server
url: https://github.com/fauxpilot/fauxpilot
---

FauxPilot
=========

This is an attempt to build a locally hosted alternative to GitHub Copilot. It uses the SalesForce CodeGen models inside of NVIDIA's Triton Inference Server with the FasterTransformer backend.

Prerequisites
-------------

You'll need:

-   Docker
-   `docker compose` >= 1.28
-   An NVIDIA GPU with Compute Capability >= 6.0 and enough VRAM to run the model you want.
-   `nvidia-docker`
-   `curl` and `zstd` for downloading and unpacking the models.

Note that the VRAM requirements listed by `setup.sh` are _total_ -- if you have multiple GPUs, you can split the model across them. So, if you have two NVIDIA RTX 3080 GPUs, you _should_ be able to run the 6B model by putting half on each GPU.

Support and Warranty
--------------------

lmao

Okay, fine, we now have some minimal information on the wiki and a discussion forum where you can ask questions. Still no formal support or warranty though!

Setup
-----

This section describes how to install a Fauxpilot server and clients.

### Setting up a FauxPilot Server

Run the setup script to choose a model to use. This will download the model from Huggingface/Moyix in GPT-J format and then convert it for use with FasterTransformer.

Please refer to How to set-up a FauxPilot server.

### Client configuration for FauxPilot

We offer some ways to connect to FauxPilot Server. For example, you can create a client by how to open the Openai API, Copilot Plugin, REST API.

Please refer to How to set-up a client.

Terminology
-----------

-   API: Application Programming Interface
-   CC: Compute Capability
-   CUDA: Compute Unified Device Architecture
-   FT: Faster Transformer
-   JSON: JavaScript Object Notation
-   gRPC: Remote Procedure call by Google
-   GPT-J: A transformer model trained using Ben Wang's Mesh Transformer JAX
-   REST: REpresentational State Transfer
