---
project: ai
stars: 18052
description: The AI Toolkit for TypeScript. From the creators of Next.js, the AI SDK is a free open-source library for building AI-powered applications and agents 
url: https://github.com/vercel/ai
---

AI SDK
======

The AI SDK is a TypeScript toolkit designed to help you build AI-powered applications using popular frameworks like Next.js, React, Svelte, Vue and runtimes like Node.js.

To learn more about how to use the AI SDK, check out our API Reference and Documentation.

Installation
------------

You will need Node.js 18+ and pnpm installed on your local development machine.

npm install ai

Usage
-----

### AI SDK Core

The AI SDK Core module provides a unified API to interact with model providers like OpenAI, Anthropic, Google, and more.

You will then install the model provider of your choice.

npm install @ai-sdk/openai

###### @/index.ts (Node.js Runtime)

import { generateText } from 'ai';
import { openai } from '@ai-sdk/openai'; // Ensure OPENAI\_API\_KEY environment variable is set

const { text } \= await generateText({
  model: openai('gpt-4o'),
  system: 'You are a friendly assistant!',
  prompt: 'Why is the sky blue?',
});

console.log(text);

### AI SDK UI

The AI SDK UI module provides a set of hooks that help you build chatbots and generative user interfaces. These hooks are framework agnostic, so they can be used in Next.js, React, Svelte, and Vue.

You need to install the package for your framework:

npm install @ai-sdk/react

###### @/app/page.tsx (Next.js App Router)

'use client';

import { useState } from 'react';
import { useChat } from '@ai-sdk/react';

export default function Page() {
  const { messages, status, sendMessage } \= useChat();
  const \[input, setInput\] \= useState('');
  const handleSubmit \= e \=> {
    e.preventDefault();
    sendMessage({ text: input });
    setInput('');
  };

  return (
    <div\>
      {messages.map(message \=> (
        <div key\={message.id}\>
          <strong\>{\`${message.role}: \`}</strong\>
          {message.parts.map((part, index) \=> {
            switch (part.type) {
              case 'text':
                return <span key\={index}\>{part.text}</span\>;

              // other cases can handle images, tool calls, etc
            }
          })}
        </div\>
      ))}

      <form onSubmit\={handleSubmit}\>
        <input
          value\={input}
          placeholder\="Send a message..."
          onChange\={e \=> setInput(e.target.value)}
          disabled\={status !== 'ready'}
        />
      </form\>
    </div\>
  );
}

###### @/app/api/chat/route.ts (Next.js App Router)

import { streamText } from 'ai';
import { openai } from '@ai-sdk/openai';

export async function POST(req: Request) {
  const { messages } \= await req.json();

  const result \= streamText({
    model: openai('gpt-4o'),
    system: 'You are a helpful assistant.',
    messages,
  });

  return result.toUIMessageStreamResponse();
}

Templates
---------

We've built templates that include AI SDK integrations for different use cases, providers, and frameworks. You can use these templates to get started with your AI-powered application.

Community
---------

The AI SDK community can be found on GitHub Discussions where you can ask questions, voice ideas, and share your projects with other people.

Contributing
------------

Contributions to the AI SDK are welcome and highly appreciated. However, before you jump right into it, we would like you to review our Contribution Guidelines to make sure you have smooth experience contributing to AI SDK.

Authors
-------

This library is created by Vercel and Next.js team members, with contributions from the Open Source Community.
