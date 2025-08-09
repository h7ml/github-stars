---
project: coze-loop
stars: 4578
description: Next-generation AI Agent Optimization Platform: Cozeloop addresses challenges in AI agent development by providing full-lifecycle management capabilities from development, debugging, and evaluation to monitoring.  
url: https://github.com/coze-dev/coze-loop
---

Coze Loop • Feature list • Quick start • Developer guide

English | 中文

What is Coze Loop
-----------------

Coze Loop is a developer-oriented, platform-level solution focused on the development and operation of AI agents. It addresses various challenges faced during the AI agent development process, providing full lifecycle management capabilities from development, debugging, evaluation, to monitoring.

Based on the commercial version, Coze Loop introduces an open-source edition that offers developers free access to core foundational feature modules. By sharing its core technology framework in an open-source model, developers can customize and extend according to business needs, facilitating community co-construction, sharing, and exchange, helping developers participate in AI agent exploration and practice with zero barriers.

What can Coze Loop do?
----------------------

Coze Loop helps developers efficiently develop and operate AI agents by providing full-lifecycle management capabilities. Whether it's prompt engineering, AI agent evaluation, or monitoring and optimization after deployment, Coze Loop offers powerful tools and intelligent support, significantly simplifying the AI agent development process and improving the performance and stability of AI agents.

-   **Prompt development**: Coze Loop's prompt development module provides developers with full-process support from writing, debugging, and optimization to version management. With a visual Playground, developers can conduct real-time interactive testing of prompts, enabling intuitive comparisons of the output effects of different LLMs.
-   **Evaluation**: Coze Loop's evaluation module provides developers with systematic evaluation capabilities, enabling multi-dimensional automated testing of the output effects of prompts and Coze agents, such as accuracy, conciseness, and compliance.
-   **Observation**: Coze Loop provides developers with visual observation capabilities for the full-chain execution process, fully recording each processing step from user input to AI output. This includes key nodes such as prompt parsing, model invocation, and tool execution, while automatically capturing intermediate results and abnormal states.

Feature list
------------

**Module**

**Function**

Prompt Debugging

\* Playground debugging and comparison  
\* Prompt version management

Evaluation

\* Manage evaluation sets  
\* Manage evaluators  
\* Manage experiments

Observation

\* SDK reporting of Trace  
\* Trace data observation

Model

Support for integrating models such as OpenAI and Volcengine Ark

Quick Start
-----------

> Refer to Quick Start for detailed instructions on how to install and deploy the latest version of Coze Loop.

**Environment Requirements:**

-   Install Docker and Docker Compose in advance, and start the Docker service.

**Operation Steps:**

1.  Get the source code. Execute the following command to get the latest version of the Coze Loop source code.
    
    # Clone the code
    git clone https://github.com/coze-dev/coze-loop.git
    # Enter the Coze Loop directory
    cd coze-loop
    
2.  Configure the model. Go to the `conf/default/app/runtime/` directory, edit the `model_config.yaml` file, and modify the `api_key` and `model` fields. Taking Volcengine Ark as an example:
    -   `api_key`: Volcengine Ark API Key. For how to obtain it, please refer to Get API Key.
    -   `model`: The Endpoint ID of the Volcengine Ark model access point. For how to obtain it, please refer to Get Endpoint.
3.  Start the service. Execute the following command to quickly deploy the Coze Loop open-source edition using Docker Compose.
    
    # Start the service, default is development mode
    docker compose up --build
    
4.  Access the Coze Loop open-source edition by visiting `http://localhost:8082` in your browser.

Using Coze Loop Open-source Edition
-----------------------------------

-   Prompt development and debugging: Coze Loop provides a complete prompt development workflow.
-   Evaluation: Coze Loop's evaluation functionality offers standardized evaluation data management, automated assessment engines, and comprehensive experimental result statistics.
-   Trace reporting and querying: Coze Loop supports automatic Trace reporting for prompt debugging conducted on the platform, enabling real-time tracking of each Trace data.
-   Open-source Edition usage of the Coze Loop SDK: The Coze Loop SDK in three languages is suitable for both commercial and open-source editions. For the Open-source Edition, developers only need to modify some parameter configurations during initialization.

Developer guide
---------------

-   System architecture: Learn about the technical architecture and core components of Coze Loop Open-source Edition.
-   Startup mode: When installing and deploying Coze Loop Open-source Edition, the default development mode allows backend file modifications without requiring service redeployment.
-   Model configuration: Coze Loop Open-source Edition supports various LLM models through the Eino framework. Refer to this document to view the supported model list and learn how to configure models.
-   Code development and testing: Learn how to perform secondary development and testing based on Coze Loop Open-source Edition.
-   Fault troubleshooting: Learn how to check container status and system logs.

License
-------

This project uses the Apache 2.0 license. For more details, please refer to the LICENSE file.

Community Contributions
-----------------------

We welcome community contributions. For contribution guidelines, please refer to CONTRIBUTING and Code of conduct. We look forward to your contributions!

Security and Privacy
--------------------

If you identify potential security issues in this project or believe you may have found one, please notify Bytedance's security team via our Security Center or Vulnerability Report Email.

Please **do not** create public GitHub Issues.

Join the Community
------------------

We are committed to building an open and friendly developer community. All developers interested in AI Agent development are welcome to join us!

### Issue Reports & Feature Requests

To efficiently track and resolve issues while ensuring transparency and collaboration, we recommend participating through:

-   **GitHub Issues**: Submit bug reports or feature requests
-   **Pull Requests**: Contribute code or documentation improvements

### Technical Discussion & Communication

Join our technical discussion groups to share experiences with other developers and stay updated with the latest project developments:

-   Lark Group Chat: Scan the QR code below on the Lark mobile app to join the Coze Loop technical discussion group.

-   Discord Server: Coze Community
    
-   Telegram Group: Coze
    

Acknowledgments
---------------

Thanks to all developers and community members who contributed to the Coze Loop project Special thanks:

-   LLM integration support provided by the Eino framework team
-   High-performance frameworks developed by the CloudWeGo team
-   All users who participated in testing and feedback
