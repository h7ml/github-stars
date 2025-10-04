---
project: getting-started
stars: 842
description: A Starter Project Template for Wechaty works out-of-the-box
url: https://github.com/wechaty/getting-started
---

Wechaty Getting Started
=======================

About Wechaty
-------------

Wechaty is a Conversational RPA(Robotic Process Automation) SDK(Software Development Kit) for Chatbot Makers. It's well designed with an easy to use API. It supports all operating systems including Linux, OSX, Win32, Docker, and lots of IMs(Instant Messaging services) including WeChat, WeCom, Whatsapp, Lark, Gitter, etc.

As a developer, you can use Wechaty to easily build your bot, effectively manage message sending and receiving, room creation and sending out invitations, contact friends, and delightfully add artificial intelligence between users and your bot.

About Wechaty Getting Started Project
-------------------------------------

If you are a total beginner to Wechaty, this project is the best starting point for you. You can run it on a Cloud IDE in a couple of steps or on a local setup on your machine as described in the sections below.

If you encounter difficulties or have any questions, you are welcome to ask for help in our Discord Community at https://discord.gg/7q8NBZbQzt.

Notice: the current active version of Wechaty is v1.x which is not compatible with most of the v0.x modules.

-   **`wechaty@0.x`** - To use the Wechaty v0.x, please visit the Wechaty Getting Started v0.x branch.

### Features of Wechaty Getting Started project

1.  It works out of the box on Linux, Mac or Windows.
2.  Supports all puppets like Web, Pad, Windows, and Mac.
3.  It replies with a `dong` message when it receives a `ding` message.

### Wechaty Getting Started video tutorial

Above is a short run-through of deploying the ding-dong-bot using WeChat, WhatsApp, and WeCom.

### Running Wechaty Getting Started Project on a cloud based IDE

The fastest way to getting started with Wechaty is to use a Cloud based IDE for running the Wechaty Getting Started Project. You can either use Gitpod or Google Cloud Shell.

If you are a total beginner, then we recommed Gitpod.

#### Using Gitpod ❤️ Wechaty

Gitpod is an online and open source platform for automated and ready-to-code development environments. You can click the button below to access a complete setup of Wechaty Getting Started ding-dong BOT project on gitpod. If you have never used gitpod before, you will be required to login using your gitHub account.

You can learn more about Gitpod ❤️ Wechaty from our blog: Getting Started Without Leaving Your Browser: Wechaty ❤️ Gitpod, @huan, Feb 06, 2021

#### Using Google Cloud Shell

Google Cloud Shell is an online development and operations environment accessible anywhere with your browser. You can run this project on Google Cloud Shell by clicking the button below.

> Generated via open-in-cloud-shell

After opening the Google Cloud Shell editor, there should be an open tutorial in the right panel which you can follow to learn more about Wechaty.

Learn more about running this project on Google Cloud Shell from our blog: Google Cloud Shell Tutorials for Wechaty, @huan, Feb 20, 2021

### Running Wechaty Getting Started project on your local machine

#### Prerequisites

For you to run this project on your local machine, you need to:

1.  Have Node.js v16+ installed on your machine. You can run the command `node -v` on the terminal to check whether you have `Node.js` installed. If you have it, you should be able to see the version printed on the terminal like `v16.13.0`. Your version might be different from `v16.13.0`. If it is not installed or your version is below 16, You need to install the latest version by following the links below:
    
    -   Windows
    -   Linux(Debian/Ubuntu)
    -   macOS
    
    > Node.js for other platforms can be found at https://nodejs.org/en/download/package-manager/
    
2.  Have Wechaty Puppet Service TOKEN if you want to use RPA protocols other than Web
    

#### Step 1: Clone this Repository

You need to clone this repository to your local machine and then switch to `wechaty-getting-started` directory by running the commands below.

git clone https://github.com/wechaty/getting-started.git
cd getting-started

#### Step 2: Install Dependencies

You need to install dependencies by running the command below.

npm install

#### Step 3: Run the Bot

You can use `export` to set environment variables in Linux, and use `set` in Windows. If you run into errors while running this command, check the troubleshooting tips in step 4.

##### Linux

export WECHATY\_LOG=verbose
export WECHATY\_PUPPET=wechaty-puppet-wechat
npm start
# the above is equals to the below command:
# npx ts-node examples/ding-dong-bot.ts

##### Windows

set WECHATY\_LOG=verbose
set WECHATY\_PUPPET=wechaty-puppet-wechat
npm start
# the above is equals to the below command:
# npx ts-node examples/ding-dong-bot.ts

You are all set!

#### Step 4: Troubleshooting

If you run into problems while following the above steps, try the options below. You are also welcome to ask questions in our gitter chatroom.

1.  You might also need windows-build-tool if you are using windows:
    
    npm install windows-build-tools
    

Working with Different Puppets
------------------------------

In our getting started example, the ding-dong BOT uses wechaty-puppet-wechat4u when `WECHATY_PUPPET` is not set, which is just for newcomer's convenience.

By default, Wechaty will use the Puppet Service for logging in your bot. You can use other Puppet Provider like Whatsapp Web protocol( wechaty-puppet-whatsapp).

If you want to use a Wechaty Puppet Provider for a different protocol, then you need to specify a puppet service provider name (the same as its NPM name) by setting the `WECHATY_PUPPET` environment variable.

Thanks to the great contributions from our community, there are many Wechaty Puppets which can be used by Wechaty. They have helped us use protocols like Web, Pad, Mac, and Windows.

### Wechaty Puppets

Protocol

NPM

Puppet Service

`wechaty-puppet-service`

Whatsapp Web

`wechaty-puppet-whatsapp`

WeChat Web

`wechaty-puppet-wechat`

WeChat Pad

`wechaty-puppet-padlocal`

> Visit our website to learn more about Wechaty Puppet Service Providers

For example, if you want to use the `padlocal` puppet, you should set `WECHATY_PUPPET=wechaty-puppet-padlocal` before you run `npm start`. You also need a TOKEN for `wechaty-puppet-padlocal` which you need to set to the `WECHATY_PUPPET_PADLOCAL_TOKEN` environment variable. You can apply for the PadLocal TOKEN from here. The code snippets below illustrate what has been described above on Linux/ MacOS and on Windows.

### On Linux / macOS

export WECHATY\_PUPPET=wechaty-puppet-padlocal
export WECHATY\_PUPPET\_PADLOCAL\_TOKEN='puppet\_padlocal\_your-token-here'
npm start

### On Windows

set WECHATY\_PUPPET=wechaty-puppet-padlocal
set WECHATY\_PUPPET\_PADLOCAL\_TOKEN='puppet\_padlocal\_your-token-here'
npm start

Learn more about installing Wechaty on windows from this blog post.

Advanced tutorials
------------------

### 1\. Wechaty Tutorial

Above is a 10 minute video tutorial. It is using version 0.14 or older versions of Wechaty therefore it is also outdated. It is a good way to start if you are new to Wechaty.

### 2\. More Examples

> Note: Before you attempt more examples, make sure you have tried out the wechaty getting started project in this repository.

-   Official Wechaty Examples Directory

API REFERENCE
-------------

1.  Official API Docs: https://wechaty.js.org/docs/api

MORE RESOURCES
--------------

### 1\. Docker Wechaty Getting Started

https://github.com/wechaty/docker-wechaty-getting-started

### 2\. Heroku Wechaty Getting Started

https://github.com/wechaty/heroku-wechaty-getting-started

### 3\. Wechaty Home

https://wechaty.github.io

FAQ
---

### 1\. I can not login with my Wechat account

WeChat account registered after 2017 will not be able to login via Web API. Learn more about it at wechaty/wechaty#872

Solution: You can use Wechaty support protocols other than Web API, such as pad. Learn more at wechaty/wechaty#1296

### 2\. What is a `Puppet` in Wechaty

The term Puppet in Wechaty is an Abstract Class for implementing protocol plugins. The plugins are the components that help Wechaty to control Wechat and that's the reason why we call it puppet.

The plugins are named `PuppetXXX`, for example PuppetWeChat is using the google puppeteer to control the WeChat Web API via a chrome browser, PuppetPadchat uses the WebSocket protocol to connect with a Protocol Server for controlling the iPad Wechat program. For more details you can go to Puppet in wiki.

Learn more about Wechaty Puppet from our documentation at Wechaty Puppet

Wechaty Getting Started in Multiple Languages
---------------------------------------------

-   TypeScript Wechaty Getting Started
-   Python Wechaty Getting Started
-   Go Wechaty Getting Started
-   Java Wechaty Getting Started
-   Scala Wechaty Getting Started
-   PHP Wechaty Getting Started
-   .NET(C#) Wechaty Getting Started

History
-------

### main v1.18 (Mar 14, 2022)

Add CQRS Wechaty examples.

### v1.11 (Oct 30, 2021)

Branch: v1.11: release v1.11 of Wechaty.

1.  v0.13: Enable ESM (ES Module) support (chatie/tsconfig#16)

### v0.8 (Feb 20, 2021)

Using Google Cloud Shell for a quick setup!

### v0.6 (Feb 11, 2021)

Using Gitpod for a quick setup!

### v0.0.1 (Jan 12, 2017)

Init version

Contributors
------------

Maintainers
-----------

@wechaty/contributors

Copyright & License
-------------------

-   Code & Docs © 2018-now Huan and Wechaty Contributors
-   Code released under the Apache-2.0 License
-   Docs released under Creative Commons
