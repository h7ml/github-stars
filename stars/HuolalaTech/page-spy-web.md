---
project: page-spy-web
stars: 5477
description: A remote debugging platform you can definitely use.
url: https://github.com/HuolalaTech/page-spy-web
---

Page Spy
========

  
  

English | 中文 | 日本語

Intro
-----

**PageSpy** is a tool used for debugging projects on platforms such as Web, Mini Programs, and HarmonyOS apps.

It encapsulates native APIs, filtering and transforming the parameters when native methods are invoked, and organizes them into a standard format for transmission to the debugging client. The debugging client then presents the data intuitively through an interface similar to the local console.

Why is PageSpy?
---------------

> A picture is worth a thousand words.

When to Use?
------------

_PageSpy shines in any scenario where local console debugging is not possible!_ Let's explore some use cases:

-   **Local Debugging of H5 and Webview Applications**: Mobile screens are too small, traditional debugging panels are inconvenient to operate, display poorly, and prone to information truncation.
    
-   **Remote Work and Cross-Region Collaboration**: Traditional communication methods (email, phone, video conferencing) are inefficient, fault information is incomplete, and misunderstandings and misjudgments easily occur.
    
-   **Troubleshooting White Screen Issues on User Terminals**: Data monitoring, log analysis and other traditional methods rely on the troubleshooting team's deep understanding of business and technology, resulting in low localization efficiency.
    

Yep, the goal of PageSpy is can help the people which in like above cases.

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
