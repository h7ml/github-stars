---
project: rainbond
stars: 5926
description: A container platform that needs no Kubernetes learning, Build, deploy, assemble, and manage apps on Kubernetes, no K8s expertise needed, all in a graphical platform.
url: https://github.com/goodrain/rainbond
---

A container platform that needs no Kubernetes learning
------------------------------------------------------

Build, deploy, assemble, and manage apps on Kubernetes, no K8s expertise needed, all in a graphical platform.

Website • Documentation

What is Rainbond?
-----------------

Rainbond is a Kubernetes-based cloud-native application management platform that is 100% open-source. It is dedicated to transforming complex container orchestration and application management capabilities into a simple and user-friendly development and operations experience. Without needing in-depth knowledge of Kubernetes' underlying architecture, users can achieve full lifecycle management of applications through a graphical interface and standardized workflows. Ideal for enterprises to quickly build cloud-native application platforms, it reduces technical barriers and implementation costs.

Why Rainbond?
-------------

### Positioning Differences with Mainstream Platforms

**Platform Type**

Representative Products

Rainbond's Differentiation

**Developer-friendly PaaS**

Heroku, Vercel

▶ Self-hosted Support ▶ Full K8s Compatibility

**K8s Native Tools**

Rancher, Devtron

▶ Application-level Abstraction ▶ Zero YAML Experience ▶ Complex Application Topology ▶ Offline Environment Support

**Self-hosted Solutions**

CapRover, Coolify

▶ Enterprise Multi-tenancy ▶ Hybrid Cloud Management

### 🎯 What Pain Points Does It Solve?

**Developer Perspective**

-   "I need to deploy a system with 20 microservices, but don't want to study K8s configs for each component"
-   "The configuration differences between production and test environments make every deployment risky"
-   "How to quickly deliver complex systems in customer's offline environment?"

**Ops/Platform Admin Perspective**

-   "Need to give developers autonomy while ensuring cluster stability"
-   "Traditional application cloud-native transformation costs too much"
-   "Unified application management across multi/hybrid cloud environments"

### 🚀 Core Capabilities

-   **Install Enterprise Software Like Mobile Apps**: Through the built-in application marketplace, various published microservice application templates support one-click installation and upgrades, even for systems with 100+ microservices.
    
-   **Containerization Without Dockerfile and YAML**: The platform automatically recognizes multiple development languages like Java, Python, Golang, NodeJS, PHP, .NetCore, etc., completing build and deployment through a wizard-like process without writing Dockerfile or YAML.
    
-   **Full Application Lifecycle Management**: Serverless experience where regular developers can manage and maintain applications and components without learning, including start, stop, build, update, auto-scaling, gateway policy management, etc., with non-invasive microservice architecture.
    
-   **Microservice Modular Assembly**: Business components running on Rainbond support modular dependency orchestration, one-click publishing as reusable application templates, enabling business component accumulation and reuse.
    

### Who Is It Designed For?

👩💻 Developer Users

-   Need URL access within 5 minutes from code
-   Want cloud-native capabilities without learning K8s
-   Zero configuration differences between dev and prod environments

👨💼 Platform Managers

-   Traditional application cloud-native transformation
-   Building internal PaaS platforms
-   Achieving unified hybrid cloud management

### ✨ Differentiating Highlights Comparison

Dimension

Traditional Approach

Rainbond Approach

**Deployment Complexity**

Requires K8s experts to write YAML

Visual orchestration, auto-generates K8s resources

**Environment Consistency**

Manual maintenance of multiple configs

Environment config templating, one-click deployment

**Delivery Form**

Docs + scripts + manual deployment

Self-contained app template (code + config)

**Skill Requirements**

Need full container/K8s stack skills

Operation interface based on application model abstraction

Getting Started
---------------

Installation
------------

### Minimum Requirements

-   Linux OS (CentOS 7+/Ubuntu 18.04+)
-   2 CPU cores / 8GB RAM / 50GB disk space

### 3-Minute Quick Installation

You only need to execute the following command to run a container and quickly experience the full functionality of Rainbond. For more installation options, refer to Installation and Upgrade.

curl -o install.sh https://get.rainbond.com && IMGHUB\_MIRROR=rainbond bash ./install.sh

After the command is executed successfully, open a browser and enter `http://<IP>:7070` to access the platform and start deploying applications. `<IP>` is the IP address you selected or entered when running the script.

### Quick Start

Please refer to the Quick Start documentation.

Open Source Community
---------------------

If you encounter any issues while using Rainbond and need help, please refer to the Community Support.

Slack: Rainbond Slack Channel

Twitter: Rainbond Twitter

Discord: Rainbond Discord

Contribution
------------

We welcome contributions and sharing in the Rainbond community in areas such as platform usage experience, standardized applications, and plugin sharing.

If you are a Rainbond user who has a deep understanding of Rainbond and aligns with its technical direction, and you have significant demands within your organization, we welcome you to contribute to Rainbond.

Related Projects
----------------

This repository contains the core service implementation code of the Rainbond data center. The project also includes the following sub-projects:

-   Rainbond-Console: Rainbond console server project.
-   Rainbond-Console-UI: Rainbond console frontend project.
-   Rainbond-Operator: Rainbond installation and operation project.
-   Rainbond-Builder: Rainbond source code build toolset.

License
-------

This repository is licensed under the Rainbond Open Source License, based on Apache 2.0 with additional conditions.
