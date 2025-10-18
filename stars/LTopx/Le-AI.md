---
project: Le-AI
stars: 165
description: Le-AI, Your open-source AI Assistant Hub, helping you boost efficiency UP~
url: https://github.com/LTopx/Le-AI
---

#### English | **中文**

Le-AI
=====

Your open-source AI Assistant Hub, helping you boost efficiency UP UP~

Demo | Docs | Q&A | Change Log | Feedback | Telegram | Contact Me

✨ Demo
------

Direct access: https://le-ai.app

Project documentation: https://docs.le-ai.app

🎯 Key Features
---------------

-   No need to configure additional environment variables, can be easily deployed to Vercel for free
-   Ensures privacy and security, all session records and system configurations are stored locally in the browser
-   Responsive design with dark mode, providing a great experience on different devices
-   Supports voice reading with customizable voices and speeds
-   Supports displaying markdown with code highlighting and copy operations
-   Supports OpenAI and Azure OpenAI
-   Supports custom role templates to create more AI possibilities
-   Supports i18n multilingual internationalization: English, Simplified Chinese
-   Support Docker deployment
-   For more information, please refer to the documentation

📍 Development Plan
-------------------

-   Support custom prompt repository
-   Support Function call for implementing more functionalities
-   Support for large language model APIs such as Claude, PaLM, and Llama 2
-   Support distributing keys for use in an unauthenticated state
-   Support unlimited sessions
-   Support integration of Midjourney drawing
-   Desktop version development

💿 Deployment
-------------

### Docker Deployment (Recommended)

```
docker pull ltopx/le-ai:latest

docker run -d -p 3000:3000 ltopx/le-ai:latest
```

### Docker Local Deployment

```
docker build -t ltopx/le-ai .

docker run -d -p 3000:3000 ltopx/le-ai
```

### One-click Deployment

Currently supports one-click deployment to Vercel.

🪄 Local Development
--------------------

**0\. Node Environment Requirements**

NodeJS >= 18

**1\. Install PNPM**

If you have not previously installed or used `pnpm`, you can install it by running the following command.

npm install pnpm -g

**2\. Install Dependencies**

pnpm i

**3\. Configure Environment Variables**

Rename .evn.local.demo to .env.local

**4\. Run the Project**

pnpm dev

**5\. Build the Project**

pnpm build && pnpm start

More Optional Environment Variables
-----------------------------------

Refer to the documentation: https://docs.le-ai.app

License
-------

GNU
