---
project: open-lovable
stars: 13308
description: 🔥 Clone and recreate any website as a modern React app in seconds
url: https://github.com/mendableai/open-lovable
---

Open Lovable
============

Chat with AI to build React apps instantly. An example app made by the Firecrawl team. For a complete cloud solution, check out Lovable.dev ❤️.

Setup
-----

1.  **Clone & Install**

git clone https://github.com/mendableai/open-lovable.git
cd open-lovable
npm install

1.  **Add `.env.local`**

# Required
E2B\_API\_KEY\=your\_e2b\_api\_key  # Get from https://e2b.dev (Sandboxes)
FIRECRAWL\_API\_KEY\=your\_firecrawl\_api\_key  # Get from https://firecrawl.dev (Web scraping)

# Optional (need at least one AI provider)
ANTHROPIC\_API\_KEY\=your\_anthropic\_api\_key  # Get from https://console.anthropic.com
OPENAI\_API\_KEY\=your\_openai\_api\_key  # Get from https://platform.openai.com (GPT-5)
GEMINI\_API\_KEY\=your\_gemini\_api\_key  # Get from https://aistudio.google.com/app/apikey
GROQ\_API\_KEY\=your\_groq\_api\_key  # Get from https://console.groq.com (Fast inference - Kimi K2 recommended)

1.  **Run**

npm run dev

Open http://localhost:3000

License
-------

MIT
