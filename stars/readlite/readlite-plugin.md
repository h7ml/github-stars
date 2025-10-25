---
project: readlite-plugin
stars: 506
description: Transform cluttered web pages into clean, distraction-free reading experiences with customizable themes, fonts and multilingual support.
url: https://github.com/readlite/readlite-plugin
---

ReadLite - Simple Reading Mode
==============================

A browser extension that provides a clean, distraction-free reading experience with AI summarization capabilities.

Features
--------

-   **Clean Reader Interface**: Transform cluttered web pages into a beautiful, distraction-free reading experience
-   **AI Article Summarization**: Get instant summaries and insights about what you're reading
-   **Multiple Themes**: Choose from Light, Dark, Sepia, and Paper themes to suit your preference
-   **Adjustable Typography**: Customize font size, line spacing, and width for optimal reading comfort
-   **Article Saving**: Save articles as markdown for offline reading
-   **Text Highlighting & Notes**: Mark important passages and attach notes for later reference
-   **Inline Translation**: Translate selected text or the entire article without leaving the page

Installation
------------

### From Source

# Clone the repository
git clone https://github.com/yourusername/read-lite.git
cd read-lite

# Install dependencies
yarn install

# Build the extension
yarn build

Then open your browser's extension page (e.g., `chrome://extensions`), enable **Developer mode**, and load the `build/chrome-mv3-prod` folder.

Usage
-----

1.  Install the extension from the Chrome Web Store (coming soon)
2.  Navigate to any article or blog post
3.  Click the ReadLite icon in your browser toolbar
4.  Enjoy a clean reading experience
5.  Use the AI button to get summaries and ask questions about the article

Development
-----------

### Prerequisites

-   Node.js (v16+)
-   Yarn or npm

### Setup

# Clone the repository
git clone https://github.com/yourusername/read-lite.git
cd read-lite

# Install dependencies
yarn install

# Start development server
yarn dev

### Testing & Linting

# Run tests
yarn test

# Check code style
yarn lint

### Build for production

yarn build

Contributing
------------

Pull requests and issues are welcome. Please run tests and linting before submitting.

Technical Details
-----------------

This extension is built with:

-   Plasmo Framework - Browser extension framework
-   React - UI library
-   Mozilla Readability - Content extraction
-   Marked - Markdown parsing

License
-------

MIT

Translation
-----------

-   中文说明
