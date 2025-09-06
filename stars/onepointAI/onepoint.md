---
project: onepoint
stars: 315
description: An AI assistant tool that integrates coding, writing, and reading functions. For better alternatives see https://monica.im/desktop
url: https://github.com/onepointAI/onepoint
---

onepoint
========

English | 中文

more than just chat

  

  

Onepoint is an open-source AI assistant based on Electron, designed to create the ultimate desktop productivity tool. Its initial goal was to develop a smart floating window similar to Apple's intelligent assistant that does not take up desktop space or system performance and can be quickly accessed through global hotkeys for user convenience.

With ChatGPT technology, users can continuously train onepoint to generate and reconstruct content with greater accuracy (onpoint), thereby improving efficiency. Onepoint currently supports various editing scenarios such as VSCode, Pages, Microsoft Word, Email etc, as well as reading scenarios like Safari and Chrome, achieving true full-scene intelligent coverage.

  

01 Features
-----------

  

**Basical**

-   Provide quick and concise functional access points that act globally and allow for immediate use.
-   Support one-click code writing and refactoring capabilities for multiple IDEs.
-   Translation and document writing assistant, supporting content summarization and output in various text editing scenarios.

**Advanced**

-   Reading assistant supporting content summarization and output on browsers such as Safari and Chrome.
-   Support for third-party device (such as Xiao Ai) voice output.
-   Personalized prompts and custom character presets.
-   Advanced question requesting parameter settings.

**More**

-   Plugin market support.
-   Local data storage and export.
-   Account balance inquiry.
-   Multi-language support.

  

02 Screenshots
--------------

Detail

#### Minimal Mode

#### History Mode

#### Code Assistant

#### Plugin List

#### Setting Page

#### Account Page

#### Custom Prompts

  

  

03 Getting Started
------------------

Please go to the official website to download and try out the tool.

If you encounter any bugs or have other feature requests, please feel free to submit an issue or related PR. You will not only receive our appreciation 👍 but also have the chance to receive a personalized avatar image, which will be gifted to your wallet for free in the form of an NFT (Detail in README of contributors).

  

04 Development
--------------

Welcome to submit a Pull Request (PR) or provide constructive feedback for us. Let's do something interesting together.

```
> git clone git@github.com:onepointAI/onepoint.git
> cd onepoint
> yarn
> yarn start
```

05 Vision & Roadmap
-------------------

In the long term, we hope to develop onepoint into a personalized intelligent assistant tool that extends the capabilities of various editing and reading software. At the same time, we aim to enrich its functionality through scalable plugin mechanisms, making it not only a tool but also an entry point that can help or inspire you in front of your screen.

-   🚗 High availability, fast access with good user experience, elegant interface and interaction, and high performance.
-   💻 Personalized service, providing users with tuning mechanisms to customize their personal intelligent assistants.
-   🔧 Efficient output, not to replace certain tools but to complement and enhance the capabilities of existing editors.
-   📖 Reading assistance, summarizing and organizing reading scenarios to improve the speed of information acquisition.
-   🎈 Creative play, providing plugin mechanisms as an entry point to meet various scenarios and providing an NFT ecosystem with a harmonious technical community atmosphere.
-   🤖 Model Training, providing ability to train models with custom datasets(LLMs).

06 QA
-----

Q1: Can onepoint be used on the Windows platform?

Basic abilities such as chatting and switching roles can be used normally, but others such as IDE code selection and application, and browser content acquisition require native capabilities (applescript is used on the Mac platform), which is not yet supported on Windows. In the future, vbscript will be considered to implement similar capabilities.

Q2: How to use code helpers or web scraping tools?

First, you need to click on the icon on the left to select and switch to the corresponding mode (such as code refactoring, summarization, etc.), and then select a piece of code in the IDE or focus the mouse on the current browser. Use `command + k` to globally call up onepoint. At this time, it will display whether to make changes to the application, choose `yes`.

Q3: What are the limitations of web scraping?

Currently, there is a character limit of 4000 for web page crawling (excluding line breaks, carriage returns, and HTML tags) to achieve faster speed. In the future, the ability to segment long web pages with context will be used to summarize their contents.

  

Contributors
------------

License
-------

MIT License
