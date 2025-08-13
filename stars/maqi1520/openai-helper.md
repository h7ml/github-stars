---
project: openai-helper
stars: 2
description: null
url: https://github.com/maqi1520/openai-helper
---

Tailwind CSS code generator
===========================

Tailwind CSS 代码生成器

How it works
------------

Inspired by TwtterBio and Danny Richman

Powerd by OpenAI, Next.js, Vercel and Tailwind CSS.

This project uses the OpenAI GPT-3 API (specifically, text-davinci-003) and Vercel Edge functions with streaming. It constructs a prompt based on the form and user input, sends it to the GPT-3 API via a Vercel Edge function, then streams the response back to the application.

Video and blog post coming soon on how to build apps with OpenAI and Vercel Edge functions!

Running Locally
---------------

After cloning the repo, go to OpenAI to make an account and put your API key in a file called `.env`.

Then, run the application in the command line and it will be available at `http://localhost:3000`.

npm run dev

One-Click Deploy
----------------

Deploy the example using Vercel:
