---
project: chat-simplifier
stars: 518
description: Simplify your chat content in seconds (by OpenAI)
url: https://github.com/zhengbangbo/chat-simplifier
---

Chat Simplifier
===============

English | 中文

This project simplify chat content for you using AI.

How it works
------------

This project uses the Chat GPT API (gpt-3.5-turbo) and Vercel Edge functions with streaming. It constructs a prompt based on the form and user input, sends it to the GPT-3 API via a Vercel Edge function, then streams the response back to the application.

Running Locally
---------------

After cloning the repository, go to OpenAI to create an account and refer to the environment variable instructions to put your API key into a file named `.env`.

Then, run the application in the command line and it will be available at `http://localhost:3000`.

npm run dev

Environment variable description
--------------------------------

Environment variable

Description

Required

Optional value

OPENAI\_API\_KEY

OpenAI API Key，separate with `,` when there are multiple

No

(Get)

NEXT\_PUBLIC\_USE\_USER\_KEY

Whether to use the API key entered by the user

No, default value is `true`

`true` or `false`

NEXT\_PUBLIC\_SECRET

Secret string for the project. Use for generating signatures for API calls

No

`null`

One-Click Deploy
----------------

Deploy the example using Vercel:

Credits
-------

Inspired by TwtterBio and Jimmy Lv.
