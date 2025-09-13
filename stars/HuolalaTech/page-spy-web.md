---
project: page-spy-web
stars: 5411
description: A remote debugging platform you can definitely use.
url: https://github.com/HuolalaTech/page-spy-web
---

Page Spy
========

  
  

English | 中文 | 日本語

Intro
-----

**PageSpy** is a tool used for debugging projects on platforms such as Web, Mini Programs, and HarmonyOS apps.

Based on encapsulation of native web APIs, it filters and transforms the parameters of native methods when called, and converts into messages with specific format for consumption by the debugger client. The debugger presents ui in an interactive devtools-like for easy viewing after receives the message data.

Why is PageSpy?
---------------

> A picture is worth a thousand words.

When should I use?
------------------

It's **PageSpy** show time whenever you can't debug code with local devtools! Let's see the following instances:

-   Debugging of H5 or webview app locally: in the past, some products provided panels that could display information on H5, but the small screens of mobile devices make it inconvenient for operation, and the display is not user-friendly. Issues such as information being truncated are also common.
-   Remote work and cross-regional collaboration: traditional communications such as emails, phone calls, and video conferences are inefficient, and fault information is not comprehensive, making it prone to misunderstandings and misjudgments.
-   White screen issues on user devices: traditional approaches to troubleshooting, such as data monitoring and log analysis, depend on troubleshooters understanding business requirements and technical implementations.

The commonality among these issues is that developers cannot view runtime information as easily as they can using the console.

To address this, PageSpy provides a live view of the project for technical personnel to inspect on the debugging side. In remote collaborative scenarios, testers no longer need to frequently provide fault information to technical personnel through text, screenshots, voice messages, or screen recordings.

How to use?
-----------

In order to ensure data security and facilitate your usage, we offer comprehensive, out-of-the-box deployment solutions. Developers can choose any deployment method according to their own situations.

### Option 1: deploy by node

> Video tutorial:

yarn global add @huolala-tech/page-spy-api@latest

# if you use npm

npm install -g @huolala-tech/page-spy-api@latest

After the download is complete, you can directly execute `page-spy-api` in the command line to start the service. After the startup is complete, visit `http://localhost:6752` on the browser. Once local testing is complete, you can deploy it to the server.

### Option 2: deploy by docker

> Video tutorial:

docker run -d --restart=always -v ./log:/app/log -v ./data:/app/data -p 6752:6752 --name="pageSpy" ghcr.io/huolalatech/page-spy-web:latest

After the startup is complete, visit `http://localhost:6752` on the browser. Once local testing is complete, you can deploy it to the server.

How to contribute?
------------------

Click to see the Contributing.

FAQ
---

Click to see the FAQ.

Community
---------

Join us on our Official Discord Server!

Roadmap
-------

Click to see the Roadmap.
