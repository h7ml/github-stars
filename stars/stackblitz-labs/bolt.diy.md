---
project: bolt.diy
stars: 17668
description: Prompt, run, edit, and deploy full-stack web applications using any LLM you want!
url: https://github.com/stackblitz-labs/bolt.diy
---

bolt.diy
========

Welcome to bolt.diy, the official open source version of Bolt.new, which allows you to choose the LLM that you use for each prompt! Currently, you can use OpenAI, Anthropic, Ollama, OpenRouter, Gemini, LMStudio, Mistral, xAI, HuggingFace, DeepSeek, or Groq models - and it is easily extended to use any other model supported by the Vercel AI SDK! See the instructions below for running this locally and extending it to include more models.

* * *

Check the bolt.diy Docs for more offical installation instructions and more informations.

* * *

Also this pinned post in our community has a bunch of incredible resources for running and deploying bolt.diy yourself!

We have also launched an experimental agent called the "bolt.diy Expert" that can answer common questions about bolt.diy. Find it here on the oTTomator Live Agent Studio.

bolt.diy was originally started by Cole Medin but has quickly grown into a massive community effort to build the BEST open source AI coding assistant!

Table of Contents
-----------------

-   Join the Community
-   Requested Additions
-   Features
-   Setup
-   Run the Application
-   Available Scripts
-   Contributing
-   Roadmap
-   FAQ

Join the community
------------------

Join the bolt.diy community here, in the oTTomator Think Tank!

Project management
------------------

Bolt.diy is a community effort! Still, the core team of contributors aims at organizing the project in way that allows you to understand where the current areas of focus are.

If you want to know what we are working on, what we are planning to work on, or if you want to contribute to the project, please check the project management guide to get started easily.

Requested Additions
-------------------

-   ✅ OpenRouter Integration (@coleam00)
-   ✅ Gemini Integration (@jonathands)
-   ✅ Autogenerate Ollama models from what is downloaded (@yunatamos)
-   ✅ Filter models by provider (@jasonm23)
-   ✅ Download project as ZIP (@fabwaseem)
-   ✅ Improvements to the main bolt.new prompt in `app\lib\.server\llm\prompts.ts` (@kofi-bhr)
-   ✅ DeepSeek API Integration (@zenith110)
-   ✅ Mistral API Integration (@ArulGandhi)
-   ✅ "Open AI Like" API Integration (@ZerxZ)
-   ✅ Ability to sync files (one way sync) to local folder (@muzafferkadir)
-   ✅ Containerize the application with Docker for easy installation (@aaronbolton)
-   ✅ Publish projects directly to GitHub (@goncaloalves)
-   ✅ Ability to enter API keys in the UI (@ali00209)
-   ✅ xAI Grok Beta Integration (@milutinke)
-   ✅ LM Studio Integration (@karrot0)
-   ✅ HuggingFace Integration (@ahsan3219)
-   ✅ Bolt terminal to see the output of LLM run commands (@thecodacus)
-   ✅ Streaming of code output (@thecodacus)
-   ✅ Ability to revert code to earlier version (@wonderwhy-er)
-   ✅ Chat history backup and restore functionality (@sidbetatester)
-   ✅ Cohere Integration (@hasanraiyan)
-   ✅ Dynamic model max token length (@hasanraiyan)
-   ✅ Better prompt enhancing (@SujalXplores)
-   ✅ Prompt caching (@SujalXplores)
-   ✅ Load local projects into the app (@wonderwhy-er)
-   ✅ Together Integration (@mouimet-infinisoft)
-   ✅ Mobile friendly (@qwikode)
-   ✅ Better prompt enhancing (@SujalXplores)
-   ✅ Attach images to prompts (@atrokhym)(@stijnus)
-   ✅ Added Git Clone button (@thecodacus)
-   ✅ Git Import from url (@thecodacus)
-   ✅ PromptLibrary to have different variations of prompts for different use cases (@thecodacus)
-   ✅ Detect package.json and commands to auto install & run preview for folder and git import (@wonderwhy-er)
-   ✅ Selection tool to target changes visually (@emcconnell)
-   ✅ Detect terminal Errors and ask bolt to fix it (@thecodacus)
-   ✅ Detect preview Errors and ask bolt to fix it (@wonderwhy-er)
-   ✅ Add Starter Template Options (@thecodacus)
-   ✅ Perplexity Integration (@meetpateltech)
-   ✅ AWS Bedrock Integration (@kunjabijukchhe)
-   ✅ Add a "Diff View" to see the changes (@toddyclipsgg)
-   ⬜ **HIGH PRIORITY** - Prevent bolt from rewriting files as often (file locking and diffs)
-   ⬜ **HIGH PRIORITY** - Better prompting for smaller LLMs (code window sometimes doesn't start)
-   ⬜ **HIGH PRIORITY** - Run agents in the backend as opposed to a single model call
-   ✅ Deploy directly to Netlify (@xKevIsDev)
-   ✅ Supabase Integration (@xKevIsDev)
-   ⬜ Have LLM plan the project in a MD file for better results/transparency
-   ⬜ VSCode Integration with git-like confirmations
-   ⬜ Upload documents for knowledge - UI design templates, a code base to reference coding style, etc.
-   ✅ Voice prompting
-   ⬜ Azure Open AI API Integration
-   ⬜ Vertex AI Integration
-   ⬜ Granite Integration
-   ✅ Popout Window for Web Container(@stijnus)
-   ✅ Ability to change Popout window size (@stijnus)

Features
--------

-   **AI-powered full-stack web development** for **NodeJS based applications** directly in your browser.
-   **Support for multiple LLMs** with an extensible architecture to integrate additional models.
-   **Attach images to prompts** for better contextual understanding.
-   **Integrated terminal** to view output of LLM-run commands.
-   **Revert code to earlier versions** for easier debugging and quicker changes.
-   **Download projects as ZIP** for easy portability Sync to a folder on the host.
-   **Integration-ready Docker support** for a hassle-free setup.
-   **Deploy** directly to **Netlify**

Setup
-----

If you're new to installing software from GitHub, don't worry! If you encounter any issues, feel free to submit an "issue" using the provided links or improve this documentation by forking the repository, editing the instructions, and submitting a pull request. The following instruction will help you get the stable branch up and running on your local machine in no time.

Let's get you up and running with the stable version of Bolt.DIY!

Quick Installation
------------------

← Click here to go the the latest release version!

-   Download the binary for your platform
-   Note: For macOS, if you get the error "This app is damaged", run `xattr -cr /path/to/Bolt.app`

Manual installation
-------------------

### Option 1: Node.js

Node.js is required to run the application.

1.  Visit the Node.js Download Page
2.  Download the "LTS" (Long Term Support) version for your operating system
3.  Run the installer, accepting the default settings
4.  Verify Node.js is properly installed:
    -   **For Windows Users**:
        1.  Press `Windows + R`
        2.  Type "sysdm.cpl" and press Enter
        3.  Go to "Advanced" tab → "Environment Variables"
        4.  Check if `Node.js` appears in the "Path" variable
    -   **For Mac/Linux Users**:
        1.  Open Terminal
        2.  Type this command:
            
            echo $PATH
            
        3.  Look for `/usr/local/bin` in the output

Running the Application
-----------------------

You have two options for running Bolt.DIY: directly on your machine or using Docker.

### Option 1: Direct Installation (Recommended for Beginners)

1.  **Install Package Manager (pnpm)**:
    
    npm install -g pnpm
    
2.  **Install Project Dependencies**:
    
    pnpm install
    
3.  **Start the Application**:
    
    pnpm run dev
    

### Option 2: Using Docker

This option requires some familiarity with Docker but provides a more isolated environment.

#### Additional Prerequisite

-   Install Docker: Download Docker

#### Steps:

1.  **Build the Docker Image**:
    
    # Using npm script:
    npm run dockerbuild
    
    # OR using direct Docker command:
    docker build . --target bolt-ai-development
    
2.  **Run the Container**:
    
    docker compose --profile development up
    

Configuring API Keys and Providers
----------------------------------

### Adding Your API Keys

Setting up your API keys in Bolt.DIY is straightforward:

1.  Open the home page (main interface)
2.  Select your desired provider from the dropdown menu
3.  Click the pencil (edit) icon
4.  Enter your API key in the secure input field

### Configuring Custom Base URLs

For providers that support custom base URLs (such as Ollama or LM Studio), follow these steps:

1.  Click the settings icon in the sidebar to open the settings menu
    
2.  Navigate to the "Providers" tab
    
3.  Search for your provider using the search bar
    
4.  Enter your custom base URL in the designated field
    

> **Note**: Custom base URLs are particularly useful when running local instances of AI models or using custom API endpoints.

### Supported Providers

-   Ollama
-   LM Studio
-   OpenAILike

Setup Using Git (For Developers only)
-------------------------------------

This method is recommended for developers who want to:

-   Contribute to the project
-   Stay updated with the latest changes
-   Switch between different versions
-   Create custom modifications

#### Prerequisites

1.  Install Git: Download Git

#### Initial Setup

1.  **Clone the Repository**:
    
    git clone -b stable https://github.com/stackblitz-labs/bolt.diy.git
    
2.  **Navigate to Project Directory**:
    
    cd bolt.diy
    
3.  **Install Dependencies**:
    
    pnpm install
    
4.  **Start the Development Server**:
    
    pnpm run dev
    
5.  **(OPTIONAL)** Switch to the Main Branch if you want to use pre-release/testbranch:
    
    git checkout main
    pnpm install
    pnpm run dev
    

Hint: Be aware that this can have beta-features and more likely got bugs than the stable release

> **Open the WebUI to test (Default: http://localhost:5173)**
> 
> -   Beginngers:
>     -   Try to use a sophisticated Provider/Model like Anthropic with Claude Sonnet 3.x Models to get best results
>     -   Explanation: The System Prompt currently implemented in bolt.diy cant cover the best performance for all providers and models out there. So it works better with some models, then other, even if the models itself are perfect for >programming
>     -   Future: Planned is a Plugin/Extentions-Library so there can be different System Prompts for different Models, which will help to get better results

#### Staying Updated

To get the latest changes from the repository:

1.  **Save Your Local Changes** (if any):
    
    git stash
    
2.  **Pull Latest Updates**:
    
    git pull 
    
3.  **Update Dependencies**:
    
    pnpm install
    
4.  **Restore Your Local Changes** (if any):
    
    git stash pop
    

#### Troubleshooting Git Setup

If you encounter issues:

1.  **Clean Installation**:
    
    # Remove node modules and lock files
    rm -rf node\_modules pnpm-lock.yaml
    
    # Clear pnpm cache
    pnpm store prune
    
    # Reinstall dependencies
    pnpm install
    
2.  **Reset Local Changes**:
    
    # Discard all local changes
    git reset --hard origin/main
    

Remember to always commit your local changes or stash them before pulling updates to avoid conflicts.

* * *

Available Scripts
-----------------

-   **`pnpm run dev`**: Starts the development server.
-   **`pnpm run build`**: Builds the project.
-   **`pnpm run start`**: Runs the built application locally using Wrangler Pages.
-   **`pnpm run preview`**: Builds and runs the production build locally.
-   **`pnpm test`**: Runs the test suite using Vitest.
-   **`pnpm run typecheck`**: Runs TypeScript type checking.
-   **`pnpm run typegen`**: Generates TypeScript types using Wrangler.
-   **`pnpm run deploy`**: Deploys the project to Cloudflare Pages.
-   **`pnpm run lint:fix`**: Automatically fixes linting issues.

* * *

Contributing
------------

We welcome contributions! Check out our Contributing Guide to get started.

* * *

Roadmap
-------

Explore upcoming features and priorities on our Roadmap.

* * *

FAQ
---

For answers to common questions, issues, and to see a list of recommended models, visit our FAQ Page.

Licensing
=========

**Who needs a commercial WebContainer API license?**

bolt.diy source code is distributed as MIT, but it uses WebContainers API that requires licensing for production usage in a commercial, for-profit setting. (Prototypes or POCs do not require a commercial license.) If you're using the API to meet the needs of your customers, prospective customers, and/or employees, you need a license to ensure compliance with our Terms of Service. Usage of the API in violation of these terms may result in your access being revoked.
