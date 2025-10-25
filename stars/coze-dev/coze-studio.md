---
project: coze-studio
stars: 18118
description: An AI agent development platform with all-in-one visual tools, simplifying agent creation, debugging, and deployment like never before. Coze your way to AI Agent creation.
url: https://github.com/coze-dev/coze-studio
---

Coze Studio • Feature list • Quickstart • Developer Guide

English | 中文

What is Coze Studio?
--------------------

Coze Studio is an all-in-one AI agent development tool. Providing the latest large models and tools, various development modes and frameworks, Coze Studio offers the most convenient AI agent development environment, from development to deployment.

-   **Provides all core technologies needed for AI agent development**: prompt, RAG, plugin, workflow, enabling developers to focus on creating the core value of AI.
-   **Ready to use for professional AI agent development at the lowest cost**: Coze Studio provides developers with complete app templates and build frameworks, allowing you to quickly construct various AI agents and turn creative ideas into reality.

Coze Studio, derived from the "Coze Development Platform" which has served tens of thousands of enterprises and millions of developers, we have made its core engine completely open. It is a one-stop visual development tool for AI Agents that makes creating, debugging, and deploying AI Agents unprecedentedly simple. Through Coze Studio's visual design and build tools, developers can quickly create and debug agents, apps, and workflows using no-code or low-code approaches, enabling powerful AI app development and more customized business logic. It's an ideal choice for building low-code AI products tailored . Coze Studio aims to lower the threshold for AI agent development and application, encouraging community co-construction and sharing for deeper exploration and practice in the AI field.

The backend of Coze Studio is developed using Golang, the frontend uses React + TypeScript, and the overall architecture is based on microservices and built following domain-driven design (DDD) principles. Provide developers with a high-performance, highly scalable, and easy-to-customize underlying framework to help them address complex business needs.

Feature list
------------

**Module**

**Feature**

Model service

Manage the model list, integrate services such as OpenAI and Volcengine

Build agent

\* Build, publish, and manage agent  
\* Support configuring workflows, knowledge bases, and other resources

Build apps

\* Create and publish apps  
\* Build business logic through workflows

Build a workflow

Create, modify, publish, and delete workflows

Develop resources

Support creating and managing the following resources:  
\* Plugins  
\* Knowledge bases  
\* Databases  
\* Prompts

API and SDK

\* Create conversations, initiate chats, and other OpenAPI  
\* Integrate agents or apps into your own app through Chat SDK

Quickstart
----------

Learn how to obtain and deploy the open-source version of Coze Studio, quickly build projects, and experience Coze Studio's open-source version.

Environment requirements:

-   Before installing Coze Studio, please ensure that your machine meets the following minimum system requirements: 2 Core、4 GB
-   Pre-install Docker and Docker Compose, and start the Docker service.

Deployment steps:

1.  Retrieve the source code.
    
    # Clone code
    git clone https://github.com/coze-dev/coze-studio.git
    
2.  Deploy and start the service. When deploying and starting Coze Studio for the first time, it may take a while to retrieve images and build local images. Please be patient. If you see the message "Container coze-server Started," it means the Coze Studio service has started successfully.
    
    cd coze-studio
    # start service
    # for macOS or Linux
    make web  
    # for windows
    cp .env.example .env
    docker compose -f ./docker/docker-compose.yml up
    
    For common startup failure issues, **please refer to the FAQ**.
    
3.  Register an account by visiting `http://localhost:8888/sign`, entering your username and password, and clicking the Register button.
    
4.  Configure the model at `http://localhost:8888/admin/#model-management` by adding a new model. (The model management feature is currently in beta testing. To try it out, please change the images in `docker-compose.yml` to `cozedev/coze-studio-server:0.5.0.beta.3` and `cozedev/coze-studio-web:0.5.0.beta`.)
    
5.  Visit Coze Studio at `http://localhost:8888/`.
    

Warning

If you want to deploy Coze Studio in a public network environment, it is recommended to assess security risks before you begin, and take corresponding protection measures. Possible security risks include account registration functions, Python execution environments in workflow code nodes, Coze Server listening address configurations, SSRF (Server - Side Request Forgery), and some horizontal privilege escalations in APIs. For more details, refer to Quickstart.

Developer Guide
---------------

-   **Project Configuration**:
    -   Model Configuration: Before deploying the open-source version of Coze Studio, you must configure the model service. Otherwise, you cannot select models when building agents, workflows, and apps.
    -   Plugin Configuration: To use official plugins from the plugin store, you must first configure the plugins and add the authentication keys for third-party services.
    -   Basic Component Configuration: Learn how to configure components such as image uploaders to use functions like image uploading in Coze Studio .
-   API Reference: The Coze Studio Community Edition API and Chat SDK are authenticated using Personal Access Token, providing APIs for conversations and workflows.
-   Development Guidelines:
    -   Project Architecture: Learn about the technical architecture and core components of the open-source version of Coze Studio.
    -   Code Development and Testing: Learn how to perform secondary development and testing based on the open-source version of Coze Studio.
    -   Troubleshooting: Learn how to view container states and system logs.

Using the open-source version of Coze Studio
--------------------------------------------

> Regarding how to use Coze Studio, refer to the Coze Development Platform Official Documentation Center for more information. Please note that certain features, such as tone customization, are limited to the commercial version. Differences between the open-source and commercial versions can be found in the **Feature List**.

-   Quick Start: Quickly build an AI assistant agent with Coze Studio.
-   Developing Agents: Learn how to create, build, publish, and manage agents. You can use functions such as knowledge, plugins, etc., to resolve model hallucination and lack of expertise in professional fields. In addition, Coze Studio provides rich memory features that enable agents to generate more accurate responses based on a personal user's historical conversations during interactions.
-   Develop workflows: A workflow is a set of executable instructions used to implement business logic or complete specific tasks. It structures data flow and task processing for apps or agents. Coze Studio provides a visual canvas where you can quickly build workflows by dragging and dropping nodes.
-   Resources such as plugins: In Coze Studio, workflows, plugins, databases, knowledge bases, and variables are collectively referred to as resources.
-   **API & SDK**: Coze Studio supports API related to chat and workflows, and you can also integrate agents or apps with local business systems through Chat SDK.
-   Tutorials for practice: Learn how to use Coze Studio to implement various AI scenarios, such as building web-based online customer service using Chat SDK.

License
-------

This project uses the Apache 2.0 license. For details, please refer to the LICENSE file.

Community contributions
-----------------------

We welcome community contributions. For contribution guidelines, please refer to CONTRIBUTING and Code of conduct. We look forward to your contributions!

Security and privacy
--------------------

If you discover potential security issues in the project, or believe you may have found a security issue, please notify the ByteDance security team through our security center or vulnerability reporting email. Please **do not** create public GitHub Issues.

Join Community
--------------

We are committed to building an open and friendly developer community. All developers interested in AI Agent development are welcome to join us!

### 🐛 Issue Reports & Feature Requests

To efficiently track and resolve issues while ensuring transparency and collaboration, we recommend participating through:

-   **GitHub Issues**: Submit bug reports or feature requests
-   **Pull Requests**: Contribute code or documentation improvements

### 💬 Technical Discussion & Communication

Join our technical discussion groups to share experiences with other developers and stay updated with the latest project developments:

**Feishu Group Chat**  
Scan the QR code below with Feishu mobile app to join:

**Discord Server**  
Click to join: Coze Community

**Telegram Group**  
Click to join: Telegram Group Coze

Acknowledgments
---------------

Thank you to all the developers and community members who have contributed to the Coze Studio project. Special thanks:

-   The Eino framework team - providing powerful support for Coze Studio's agent and workflow runtime engines, model abstractions and implementations, and knowledge base indexing and retrieval
-   The FlowGram team - providing a high-quality workflow building engine for Coze Studio's frontend workflow canvas editor
-   The Hertz team - Go HTTP framework with high-performance and strong-extensibility for building micro-services
-   All users who participated in testing and feedback
