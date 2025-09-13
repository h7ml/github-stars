---
project: node-telegram-bot-api
stars: 8987
description: Telegram Bot API for NodeJS
url: https://github.com/yagop/node-telegram-bot-api
---

Node.js Telegram Bot API
========================

Node.js module to interact with the official Telegram Bot API.

📦 Install
----------

npm i node-telegram-bot-api

  

> ✍️ **Note:** If you use Typescript you can install this package that contains type definitions for this library
> 
> npm install --save-dev @types/node-telegram-bot-api

🚀 Usage
--------

const TelegramBot \= require('node-telegram-bot-api');

// replace the value below with the Telegram token you receive from @BotFather
const token \= 'YOUR\_TELEGRAM\_BOT\_TOKEN';

// Create a bot that uses 'polling' to fetch new updates
const bot \= new TelegramBot(token, {polling: true});

// Matches "/echo \[whatever\]"
bot.onText(/\\/echo (.+)/, (msg, match) \=> {
  // 'msg' is the received Message from Telegram
  // 'match' is the result of executing the regexp above on the text content
  // of the message

  const chatId \= msg.chat.id;
  const resp \= match\[1\]; // the captured "whatever"

  // send back the matched "whatever" to the chat
  bot.sendMessage(chatId, resp);
});

// Listen for any kind of message. There are different kinds of
// messages.
bot.on('message', (msg) \=> {
  const chatId \= msg.chat.id;

  // send a message to the chat acknowledging receipt of their message
  bot.sendMessage(chatId, 'Received your message');
});

📚 Documentation
----------------

-   Usage
-   Examples
-   Tutorials
-   Help Information
-   API Reference: (api-release / development / experimental)
-   Contributing to the Project
-   Experimental Features

_**Note**: Development is done against the **development** branch. Code for the latest release resides on the **master** branch. Experimental features reside on the **experimental** branch._

💭 Community
------------

We thank all the developers in the Open-Source community who continuously take their time and effort in advancing this project. See our list of contributors.

We have a Telegram channel where we post updates on the Project. Head over and subscribe!

We also have a Telegram group to discuss issues related to this library.

Some things built using this library that might interest you:

-   tgfancy: A fancy, higher-level wrapper for Telegram Bot API
-   node-telegram-bot-api-middleware: Middleware for node-telegram-bot-api
-   teleirc: A simple Telegram ↔ IRC gateway
-   bot-brother: Node.js library to help you easily create telegram bots
-   redbot: A Node-RED plugin to create telegram bots visually
-   node-telegram-keyboard-wrapper: A wrapper to improve keyboards structures creation through a more easy-to-see way (supports Inline Keyboards, Reply Keyboard, Remove Keyboard and Force Reply)
-   beetube-bot: A telegram bot for music, videos, movies, EDM tracks, torrent downloads, files and more.
-   telegram-inline-calendar: Date and time picker and inline calendar for Node.js telegram bots.
-   telegram-captcha: Telegram bot to protect Telegram groups from automatic bots.

👥 Contributors
---------------

License
-------

**The MIT License (MIT)**

Copyright © 2019 Yago
