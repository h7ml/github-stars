---
project: ToolJet
stars: 36242
description: Low-code platform for building business applications. Connect to databases, cloud storages, GraphQL, API endpoints, Airtable, Google sheets, OpenAI, etc and build apps using drag and drop application builder. Built using JavaScript/TypeScript. 🚀
url: https://github.com/ToolJet/ToolJet
---

ToolJet is an **open-source low-code** platform for building and deploying internal tools with minimal engineering effort. With its drag-and-drop app-builder, you can create complex, responsive applications in minutes. ToolJet supports integration with a wide range of data sources, including databases like PostgreSQL, MongoDB, and Elasticsearch; API endpoints with OpenAPI spec and OAuth2 support; SaaS tools such as Stripe, Slack, Google Sheets, Airtable, and Notion; and object storage services like S3, Google Cloud Storage, and MinIO — enabling you to fetch, transform, and write data with ease.

ToolJet supports **AI integrations** with services like OpenAI, Hugging Face, Mistral, and more — allowing you to build secure AI-powered applications such as chat assistants, document analyzers, or content generators, all within the same low-code environment.

⭐ If you find ToolJet useful, please consider giving us a star on GitHub! Your support helps us continue to innovate and deliver exciting features.

All features
------------

-   **Visual App Builder:** 60+ built-in responsive components, including Tables, Charts, Lists, Forms, and Progress Bars.
-   **ToolJet Database:** Built-in no-code database.
-   **Multi-Page:** Build an application with multiple pages.
-   **Multiplayer editing:** Allows simultaneous app building by multiple developers.
-   **65+ data sources:** Integrate with external databases, cloud storage, and APIs.
-   **AI-powered applications:** Connect with OpenAI, Hugging Face, Mistral, and more to build intelligent apps powered by state-of-the-art language models.
-   **Desktop & mobile:** Customize layout widths to fit various screen sizes.
-   **Self-host:** Supports Docker, Kubernetes, AWS AMI, Google Cloud Run, and more.
-   **Collaborate:** Add comments anywhere on the canvas and tag your team members.
-   **Extend with plugins:** Use our command-line tool to easily bootstrap new connectors.
-   **Version control:** Manage multiple application versions with a structured release cycle.
-   **Run JS & Python code:** Execute custom JavaScript and Python snippets.
-   **Granular access control:** Set permissions at both group and app levels.
-   **No-code query editors:** Query Editors are available for all supported data sources.
-   **Transform data:** Process and transform complex data using JavaScript or Python code.
-   **Secure:** All the credentials are securely encrypted using `aes-256-gcm`.
-   **Data Privacy:** ToolJet serves solely as a proxy and does not store data.
-   **SSO:** Supports multiple Single Sign-On providers.

* * *

Quickstart
----------

The easiest way to get started with ToolJet is by creating a ToolJet Cloud account. ToolJet Cloud offers a hosted solution of ToolJet. If you want to self-host ToolJet, kindly proceed to deployment documentation.

### Try using Docker

Want to give ToolJet a quick spin on your local machine? You can run the following command from your terminal to have ToolJet up and running right away.

docker run \\
  --name tooljet \\
  --restart unless-stopped \\
  -p 80:80 \\
  --platform linux/amd64 \\
  -v tooljet\_data:/var/lib/postgresql/13/main \\
  tooljet/try:ee-lts-latest

_For users upgrading their ToolJet version, we recommend choosing the LTS version over the latest version. The LTS version ensures stability with production bug fixes, security patches, and performance enhancements._

Tutorials and examples
----------------------

Build an Employee Directory  
Build your own Ed Tech CRM  
Build an Employee Engagement Survey Dashboard  

Documentation
-------------

Documentation is available at https://docs.tooljet.ai.

-   Getting Started  
    
-   Data source Reference  
    
-   Component Reference

Self-hosted
-----------

You can use ToolJet Cloud for a fully managed solution. If you want to self-host ToolJet, we have guides on deploying ToolJet on Kubernetes, AWS AMI, Docker, and more.

Provider

Documentation

Digital Ocean

Link

Docker

Link

AWS AMI

Link

AWS ECS

Link

OpenShift

Link

Helm

Link

AWS EKS (Kubernetes)

Link

GCP GKE (Kubernetes)

Link

Azure AKS (Kubernetes)

Link

Azure Container

Link

Google Cloud Run

Link

Deploying ToolJet client

Link

Deploying ToolJet on a Subpath

Link

Marketplace
-----------

ToolJet can now be found on both AWS and Azure Marketplaces, making it simpler than ever to access and deploy our app-building platform.

Find ToolJet on AWS Marketplace here and explore seamless integration on Azure Marketplace here.

Community support
-----------------

For general help using ToolJet, please refer to the official documentation. For additional help, you can use one of these channels to ask a question:

-   Slack - Discussions with the community and the team.
-   GitHub - For bug reports and feature requests.
-   𝕏 (Twitter) - Get the product updates quickly.

Roadmap
-------

Check out our roadmap to stay updated on recently released features and learn about what's coming next.

Branching model
---------------

We use the git-flow branching model. The base branch is `develop`. If you are looking for a stable version, please use the main branch or tags labeled as v1.x.x.

Contributing
------------

Kindly read our Contributing Guide to familiarize yourself with ToolJet's development process, how to suggest bug fixes and improvements, and the steps for building and testing your changes.  

Contributors
------------

License
-------

ToolJet © 2023, ToolJet Solutions Inc - Released under the GNU Affero General Public License v3.0.
