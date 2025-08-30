---
project: x
stars: 3662
description: Craft AI-driven interface effortlessly🤖
url: https://github.com/ant-design/x
---

Ant Design X
============

Craft AI-driven interfaces effortlessly.

Changelog · Report Bug · Request Feature · English · 中文

✨ Features
----------

-   🌈 **Derived from Best Practices of Enterprise-Level AI Products**: Built on the RICH interaction paradigm, delivering an exceptional AI interaction experience.
-   🧩 **Flexible and Diverse Atomic Components**: Covers most AI dialogue scenarios, empowering you to quickly build personalized AI interaction interfaces.
-   ⚡ **Out-of-the-Box Model Integration**: Easily connect with inference services compatible with OpenAI standards.
-   🔄 **Efficient Management of Conversation Data Flows**: Provides powerful tools for managing data flows, enhancing development efficiency.
-   📦 **Rich Template Support**: Offers multiple templates for quickly starting LUI application development.
-   🛡 **Complete TypeScript Support**: Developed with TypeScript, ensuring robust type coverage to improve the development experience and reliability.
-   🎨 **Advanced Theme Customization**: Supports fine-grained style adjustments to meet diverse use cases and personalization needs.

📦 Installation
---------------

npm install @ant-design/x --save

yarn add @ant-design/x

pnpm add @ant-design/x

### 🖥️ Import in Browser

Add `script` and `link` tags in your browser and use the global variable `antd`.

We provide `antdx.js`, `antdx.min.js`, and `antdx.min.js.map` in the dist directory of the npm package.

> **We do not recommend using the built files** because they cannot be tree-shaken and will not receive bug fixes for underlying dependencies.

> Note: `antdx.js` and `antdx.min.js` depend on `react`, `react-dom`, `dayjs`, `antd`, `@ant-design/cssinjs`, `@ant-design/icons`, please ensure these files are loaded before using them.

🧩 Atomic Components
--------------------

Based on the RICH interaction paradigm, we provide numerous atomic components for various stages of interaction to help you flexibly build your AI dialogue applications:

-   Components Overview
-   Playground

Below is an example of using atomic components to create a simple chatbot interface:

import React from 'react';
import {
  // Message bubble
  Bubble,
  // Input box
  Sender,
} from '@ant-design/x';

const messages \= \[
  {
    content: 'Hello, Ant Design X!',
    role: 'user',
  },
\];

const App \= () \=> (
  <\>
    <Bubble.List items\={messages} />
    <Sender />
  </\>
);

export default App;

⚡️ Integrating Model Inference Service
--------------------------------------

We help you integrate standard model inference services out of the box by providing runtime tools like `useXAgent`, `XRequest`, etc.

Here is an example of integrating Qwen:

> Note: 🔥 `dangerouslyApiKey` has security risks, more details can be found in the documentation.

import { useXAgent, Sender, XRequest } from '@ant-design/x';
import React from 'react';

const { create } \= XRequest({
  baseURL: 'https://dashscope.aliyuncs.com/compatible-mode/v1',
  dangerouslyApiKey: process.env\['DASHSCOPE\_API\_KEY'\],
  model: 'qwen-plus',
});

const Component: React.FC \= () \=> {
  const \[agent\] \= useXAgent({
    request: async (info, callbacks) \=> {
      const { messages, message } \= info;
      const { onUpdate } \= callbacks;

      // current message
      console.log('message', message);
      // messages list
      console.log('messages', messages);

      let content: string \= '';

      try {
        create(
          {
            messages: \[{ role: 'user', content: message }\],
            stream: true,
          },
          {
            onSuccess: (chunks) \=> {
              console.log('sse chunk list', chunks);
            },
            onError: (error) \=> {
              console.log('error', error);
            },
            onUpdate: (chunk) \=> {
              console.log('sse object', chunk);
              const data \= JSON.parse(chunk.data);
              content += data?.choices\[0\].delta.content;
              onUpdate(content);
            },
          },
        );
      } catch (error) {
        // handle error
      }
    },
  });

  const onSubmit \= (message: string) \=> {
    agent.request(
      { message },
      {
        onUpdate: () \=> {},
        onSuccess: () \=> {},
        onError: () \=> {},
      },
    );
  };

  return <Sender onSubmit\={onSubmit} />;
};

🔄 Efficient Data Flow Management
---------------------------------

We help you efficiently manage the data flow of AI chat applications out of the box by providing the `useXChat` runtime tool:

Here is an example of integrating OpenAI:

import { useXAgent, useXChat, Sender, Bubble } from '@ant-design/x';
import OpenAI from 'openai';
import React from 'react';

const client \= new OpenAI({
  apiKey: process.env\['OPENAI\_API\_KEY'\],
  dangerouslyAllowBrowser: true,
});

const Demo: React.FC \= () \=> {
  const \[agent\] \= useXAgent({
    request: async (info, callbacks) \=> {
      const { messages, message } \= info;

      const { onSuccess, onUpdate, onError } \= callbacks;

      // current message
      console.log('message', message);

      // history messages
      console.log('messages', messages);

      let content: string \= '';

      try {
        const stream \= await client.chat.completions.create({
          model: 'gpt-4o',
          // if chat context is needed, modify the array
          messages: \[{ role: 'user', content: message }\],
          // stream mode
          stream: true,
        });

        for await (const chunk of stream) {
          content += chunk.choices\[0\]?.delta?.content || '';
          onUpdate(content);
        }

        onSuccess(content);
      } catch (error) {
        // handle error
        // onError();
      }
    },
  });

  const {
    // use to send message
    onRequest,
    // use to render messages
    messages,
  } \= useXChat({ agent });

  const items \= messages.map(({ message, id }) \=> ({
    // key is required, used to identify the message
    key: id,
    content: message,
  }));

  return (
    <\>
      <Bubble.List items\={items} />
      <Sender onSubmit\={onRequest} />
    </\>
  );
};

export default Demo;

Use modularized antd
--------------------

`@ant-design/x` supports ES modules tree shaking by default.

TypeScript
----------

`@ant-design/x` provides a built-in ts definition.

Non-React Implementations
-------------------------

Welcome to contribute!

Companies using antdx
---------------------

Ant Design X is widely used in AI-driven user interfaces within Ant Group. If your company and products use Ant Design X, feel free to leave a comment here.

Contributing
------------

Please read our CONTRIBUTING.md first.

If you'd like to help us improve antd, just create a Pull Request. Feel free to report bugs and issues here.

> If you're new to posting issues, we ask that you read _How To Ask Questions The Smart Way_ and How to Ask a Question in Open Source Community and How to Report Bugs Effectively prior to posting. Well written bug reports help us help you!

Need Help?
----------

If you encounter any issues while using Ant Design X, you can seek help through the following channels. We also encourage experienced users to assist newcomers via these platforms.

When asking questions on GitHub Discussions, it's recommended to use the `Q&A` tag.

1.  GitHub Discussions
2.  GitHub Issues
