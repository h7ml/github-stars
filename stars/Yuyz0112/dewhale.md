---
project: dewhale
stars: 1529
description: GitHub-Powered AI for effortless development. Start as an open-source alternative to v0.dev.
url: https://github.com/Yuyz0112/dewhale
---

I am rewriting this project, and its v2 version will be a general github-as-a-mcp-host project. If you are interested in its current functionality, please fork the repository and maintain it yourself. Thank you for your attention!
======================================================================================================================================================================================================================================

Dewhale
=======

Dewhale is a GitHub-Powered AI for effortless development.

中文文档

> If you are looking for vx.dev, check our rebranding discussion.

Quick Start
-----------

For detailed instructions on how to set up and use Dewhale, please refer to our Guide.

> With the power of our quota management feature, we allow stargazers to have 3 trials.

You can also watch this demo video.

More examples can be found in the issue list.

Features
--------

### Lower Usage Costs

Dewhale utilizes prompt engineering techniques under the GPT-4 model to issue commands. The main cost involves the number of input and completion tokens. Our current prompt, found in prompts/ui-gen.md, includes instructions for shadcn/ui, lucide, and nivo charts.

If you do not need certain components (e.g., charts), you can reduce the API cost per generation by removing instructions from the prompt.

And you can also switch to other AI models for lower usage costs.

### Easy Customization

Since Dewhale's prompt is open-sourced, you can refer to the existing prompt and replace it with other UI component libraries or coding styles as per your requirements.

You can also customize the whole workflow by yourself, e.g., a v0.dev-like Web App, and just use Dewhale's prompt as a core.

### Seamless GitHub Integration

The generated code is stored on GitHub, inherently equipped with version control, code review, and collaborative features.

Additionally, you can use a private repo to keep your code generation results visible only to collaborators.

How It Works
------------

To understand the underlying architecture and workings of Dewhale, please see our detailed Architecture Overview.

Join the Discussions
--------------------

If you like the design philosophy of Dewhale, feel free to join our Github Discussions.
