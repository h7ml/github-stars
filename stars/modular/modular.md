---
project: modular
stars: 25047
description: The Modular Platform (includes MAX & Mojo)
url: https://github.com/modular/modular
---

About Modular | Get started | API docs | Contributing | Changelog

Modular Platform
================

> A unified platform for AI development and deployment, including **MAX**🧑‍🚀 and **Mojo**🔥.

The Modular Platform is an open and fully-integrated suite of AI libraries and tools that accelerates model serving and scales GenAI deployments. It abstracts away hardware complexity so you can run the most popular open models with industry-leading GPU and CPU performance without any code changes.

Get started
-----------

You don't need to clone this repo.

You can install Modular as a `pip` or `conda` package and then start an OpenAI-compatible endpoint with a model of your choice.

To get started with the Modular Platform and serve a model using the MAX framework, see the quickstart guide.

Note

**Nightly vs. stable releases** If you cloned the repo and want a stable release, run `git checkout modular/vX.X` to match the version. The `main` branch tracks nightly builds, while the `stable` branch matches the latest released version.

After your model endpoint is up and running, you can start sending the model inference requests using our OpenAI-compatible REST API.

Try running hundreds of other models from our model repository.

Deploy our container
--------------------

The MAX container is our Kubernetes-compatible Docker container for convenient deployment, which uses the MAX framework's built-in inference server. We have separate containers for NVIDIA and AMD GPU environments, and a unified container that works with both.

For example, you can start a container for an NVIDIA GPU with this command:

docker run --gpus=1 \\
    -v ~/.cache/huggingface:/root/.cache/huggingface \\
    -p 8000:8000 \\
    modular/max-nvidia-full:latest \\
    --model-path google/gemma-3-27b-it

For more information, see our MAX container docs or the Modular Docker Hub repository.

About the repo
--------------

We're constantly open-sourcing more of the Modular Platform and you can find all of it in here. As of May, 2025, this repo includes over 450,000 lines of code from over 6000 contributors, providing developers with production-grade reference implementations and tools to extend the Modular Platform with new algorithms, operations, and hardware targets. It is quite likely **the world's largest repository of open source CPU and GPU kernels**!

Highlights include:

-   Mojo standard library: /mojo/stdlib
-   MAX GPU and CPU kernels: /max/kernels (Mojo kernels)
-   MAX inference server: /max/serve (OpenAI-compatible endpoint)
-   MAX model pipelines: /max/pipelines (Python-based graphs)
-   Code example: /examples

This repo has two major branches:

-   The `main` branch, which is in sync with the nightly build and subject to new bugs. Use this branch for contributions, or if you installed the nightly build.
    
-   The `stable` branch, which is in sync with the last stable released version of Mojo. Use the examples in here if you installed the stable build.
    

Contribute
----------

Thanks for your interest in contributing to this repository!

We accept contributions to the Mojo standard library, MAX AI kernels, code examples, and Mojo docs, but currently not to any other parts of the repository.

Please see the Contribution Guide for instructions.

We also welcome your bug reports. If you have a bug, please file an issue here.

Contact us
----------

If you'd like to chat with the team and other community members, please send a message to our Discord channel and our forum board.

License
-------

This repository and its contributions are licensed under the Apache License v2.0 with LLVM Exceptions (see the LLVM License). Modular, MAX and Mojo usage and distribution are licensed under the Modular Community License.

### Third party licenses

You are entirely responsible for checking and validating the licenses of third parties (i.e. Huggingface) for related software and libraries that are downloaded.

Thanks to our contributors
--------------------------
