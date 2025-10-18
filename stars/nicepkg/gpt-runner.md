---
project: gpt-runner
stars: 372
description: Conversations with your files! Manage and run your AI presets!
url: https://github.com/nicepkg/gpt-runner
---

GPT Runner
==========

English / 简体中文 🌏

Use GPT-Runner to manage your AI presets, engage in AI-powered conversations with your code, and significantly boost the development efficiency of both you and your team!

用 GPT-Runner 管理您的 AI 预设，通过 AI 与您的代码文件聊天，极大提升您和团队的开发效率！

CLI / Web Page / VSCode Extension / Issues / Buy Me a Coffee

终端工具 / 网页版 / VSCode 扩展 / 反馈 / 打赏开发者

gpt-runner-usage-en.mp4 📚 Table of Contents  

-   🤷‍♂️ Why GPT-Runner?
-   ⚙️ Features
-   🚀 Quick Start
    -   The first way: CLI
    -   The second way: VSCode Extension
-   📖 Documentation
    -   GPT-Runner Configs And AI Preset Files
    -   GPT-Runner Ui Usage
-   🗒️ Road map
-   🆕 What's New
-   ❓ FAQ
-   💖 Sponsor
-   🤝 Contributor
-   🙏 Acknowledgement
-   📜 LICENSE

  

🤷‍♂️ Why GPT-Runner?
---------------------

1.  **🔍 Conversations with Code Files:**
    
    -   Before using GPT-Runner: Manual copy and paste of multiple file codes into the ChatGPT window were required to propose features or fix bugs to AI.🙁
    -   After using GPT-Runner: Simply select your project files from the file tree. The AI will provide responses based on the most recent contents of those files.🤩
2.  **📑 Manage the Project's AI Presets:**
    
    -   Before using GPT-Runner: Project prompts saved in memos needed to be copied and pasted to ChatGPT for inquiries, making it difficult to put them under git version control.🤪
    -   After using GPT-Runner: Each xxx.gpt.md file represents an AI role preset. They are easy to read, modify, and can be version-controlled. Team members can share and enhance AI presets, making the code they produce closer to 100% usability.🥰

⚙️ Features
-----------

-   **🔍 Conversations with Code Files**: Select files or folders and engage in real-time conversations with AI.
-   **🛠️ Powerful CLI and IDE integration:** Implement efficient AI workflows in various IDEs.
-   **🔖 AI Preset Manager:** Manage your AI presets, Just like a locally Storybook for AI presets.
-   **🤖 Customize AI parameters:** Flexibly control the configuration of AI models.
-   **🔌 Support for third-party LLMs:** High compatibility and adaptability.
-   **🔒 Privacy-first:** Local data storage protects your privacy.
-   **🌎 Locale support:** Support for multiple languages.

🚀 Quick Start
--------------

> Make sure you have an Open AI Key or a Anthropic Key. You can get it from Open AI or Anthropic.

### The first way: CLI

> 1.  Requirements NodeJS >= 16.15.0
>     -   To check your NodeJS version, run `node -v` in your terminal. If you need to install or update NodeJS, visit the official NodeJS website for download and installation instructions.
> 2.  First run the following command to download this package, which will take a long time, which is normal.

cd <your project folder\>
npx gptr

You can see the web interface in your browser at http://localhost:3003.

### The second way: VSCode Extension

> Requirements VSCode >= 1.78.0

Install the GPT-Runner VSCode Extension from the VSCode Marketplace.

📖 Documentation
----------------

### GPT-Runner Configs And AI Preset Files

For details about `gptr.config.json` configuration file, `xxx.gpt.md` AI preset file, `.gpt-runner` special directory, please refer to here:

Introduction to GPT-Runner Configs And AI Preset Files

### GPT-Runner Ui Usage

Introduction to GPT-Runner Ui Usage

🗒️ Road map
------------

-   Jetbrains Plugin: Add Jetbrains IDE Plugin
-   Export And Import Chat History: Add dialogue import and export function
-   AI Preset Store: Add AI Preset Store for community sharing AI Preset File
-   Template Interpolation: Add template interpolation support
-   Electron: Add an Electron client to expand the target audience to non-developers

🆕 What's New
-------------

-   🚀 v1.0.0: First Release

❓ FAQ
-----

> You can contact me via 2214962083@qq.com
> 
> 对 AI 提升开发效率感兴趣的，可以加我 wechat: qq2214962083 入群交流
> 
> 要求：会科学上网，使用过 chatgpt

English > FAQ

💖 Sponsor
----------

Waiting for you...

🤝 Contributor
--------------

You can check out our Contribution Guidelines

This project exists thanks to all the people who contribute:

🙏 Acknowledgement
------------------

GPT-Runner is made possible thanks to the inspirations from the following projects:

> in alphabet order

-   Docusaurus
-   Gradio
-   LangchainJs
-   Monaco-React
-   UnoCss
-   VSCode-Material-Icon-Theme
-   VSCode-Webview-Ui-Toolkit

📜 LICENSE
----------

MIT License © 2023-PRESENT Jinming Yang
