---
project: AionUi
stars: 1340
description: Free, local, open-source GUI app for Gemini CLI — Enhance Chat Experience, Multi-tasking, Code Diff View, File & Project Management, and more | 🌟 Star if you like it!
url: https://github.com/office-sec/AionUi
---

       

* * *

**Transform your command-line experience into a modern, efficient AI Chat interface.**

**English** | 简体中文 | Official Site | Twitter

📋 Table of Contents
--------------------

-   🤔 Why does AionUi exist?
-   ✨ Key Features
    -   💬 Enhanced Chat Experience
    -   🗂️ File & Project Management
    -   ⚡ Developer Workflow
-   🚀 Quick Start
    -   📥 Download
    -   📋 Requirements
    -   🔧 Installation
    -   🏗️ Build Application
-   🛠️ Tech Stack
-   📁 Project Structure
-   🎯 Use Cases
-   🔧 Configuration
    -   🔑 API Configuration
    -   🌐 Proxy Configuration
-   🚀 What's Next?
    -   📍 Where We Are
    -   🎯 Where We're Going
-   📄 License
-   🤝 Contributing

* * *

🤔 Why does AionUi exist?
-------------------------

While the official Gemini CLI is powerful, its command-line interface has limitations for daily use. AionUi provides a GUI alternative that addresses these key pain points:

-   **File Management:** Managing code context with the `@` command can be cumbersome
-   **Chat History:** Conversations are lost when closing the CLI window
-   **Chat Experience:** Command-line interface lacks natural chat interactions
-   **Multi-tasking:** Single conversation model limits parallel workflows

AionUi offers a modern interface designed for developers who need better workflow efficiency.

✨ Key Features
--------------

### 💬 **Enhanced Chat Experience**

-   **Multi-Conversation** - Manage multiple independent chat sessions
-   **Persistent History** - All conversations saved locally, never lose your work
-   **Modern Interface** - Natural chat UI with familiar messaging controls

### 🗂️ **File & Project Management**

-   **Visual File Tree** - Browse and select files with one-click chat integration
-   **File Upload** - Drag & drop files for AI processing with secure temporary storage
-   **Code Diff View** - Side-by-side comparison of file changes

### ⚡ **Developer Workflow**

-   **Function Calling** - Full Gemini API integration for advanced features
-   **Rich Markdown** - Beautiful rendering of code blocks and formatted content
-   **Easy Setup** - Configure API keys directly in the interface

🚀 Quick Start
--------------

### 📥 Download

Ready to try AionUi? Download the latest version for your platform from our releases page:

### 📋 Requirements

-   Node.js >= 16.0.0
-   npm >= 8.0.0
-   Google Gemini API Key (Get your API key here)

### 🔧 Installation

1.  **Clone the repository**
    
    git clone https://github.com/office-sec/AionUi.git
    

cd AionUi

````

2. **Install dependencies**

```bash
npm install
````

1.  **Configure API Key**
    
    -   Open the application and go to Settings
    -   Enter your Google Gemini API Key
    -   Supports multiple authentication methods: Gemini API Key, Vertex AI, Personal Authentication
2.  **Start the application**
    
    npm start
    

### 🏗️ Build Application

# Build macOS version
npm run build-mac --arch=arm64  # Apple Silicon
npm run build-mac --arch=x64    # Intel

# Build Windows version
npm run build-win

# Build all platforms
npm run build

🛠️ Tech Stack
--------------

-   **Desktop App**: Electron 37.2.0
-   **Frontend Framework**: React 19.1.0
-   **UI Component Library**: Arco Design Web React
-   **AI Engine**: Google Gemini CLI Core
-   **Styling Framework**: UnoCSS
-   **Build Tools**: Webpack + TypeScript
-   **Icon Library**: IconPark React

📁 Project Structure
--------------------

```
AionUI/
├── src/
│   ├── adapter/          # Adapter layer
│   ├── agent/           # AI agents
│   │   └── gemini/      # Gemini AI integration
│   ├── common/          # Common modules
│   ├── process/         # Main process
│   ├── renderer/        # Renderer process
│   │   ├── components/  # UI components
│   │   ├── conversation/# Conversation related
│   │   └── messages/    # Message handling
│   └── worker/          # Worker process
├── config/              # Configuration files
├── public/              # Static resources
└── package.json
```

🎯 Use Cases
------------

-   **Code Development**: Code review, refactoring suggestions, bug fixes
-   **Document Writing**: Automatic document generation, report summaries
-   **Data Analysis**: Data visualization, analysis reports
-   **Project Management**: Task planning, progress tracking
-   **Learning Assistant**: Knowledge Q&A, concept explanation

🔧 Configuration
----------------

### 🔑 API Configuration

Supports three authentication methods:

1.  **Gemini API Key**: Direct use of Gemini API
2.  **Vertex AI**: Use Google Cloud Vertex AI
3.  **Personal Authentication**: OAuth personal authentication

### 🌐 Proxy Configuration

Supports HTTP proxy configuration for network-restricted environments.

🚀 What's Next?
---------------

### 📍 Where We Are

AionUi currently provides a powerful GUI for Gemini CLI, offering enhanced chat experience, file management, and developer workflow optimization.

### 🎯 Where We're Going

We envision AionUi evolving into a **Universal AI Agent Platform** that democratizes powerful AI agents for everyday users:

#### 🤖 **Multi-Agent Ecosystem**

-   **Terminal Agents**: Starting with Gemini CLI, expanding to other terminal-based agents
-   **Browser Agents**: Integrating open-source browser automation agents for web tasks
-   **Unified Experience**: Simple chat interface that works across all agent types
-   **Agent Discovery**: Easy access to new agents as they become available

#### 🔄 **Flexible LLM Binding**

-   **Multi-LLM Support**: Bind different language models (Gemini, Claude, GPT, etc.) to any agent
-   **Model Switching**: Easily switch between different LLMs without changing your workflow
-   **Custom Configurations**: Configure API keys and settings for each model independently

#### 🎯 **Making AI Agents Accessible**

Our goal is to make powerful AI agents accessible to everyone, not just developers. We believe that:

-   **Complex tasks should feel simple**: Users shouldn't need to learn different interfaces for different agents
-   **AI should adapt to users**: Not the other way around
-   **Open source matters**: We prioritize integrating open-source agents to ensure transparency and community control
-   **Chat is universal**: A simple conversation interface can handle complex workflows

AionUi aims to bridge the gap between powerful AI capabilities and everyday usability, making sophisticated AI agents as easy to use as chatting with a friend.

* * *

📄 License
----------

This project is licensed under the Apache-2.0 License.

🤝 Contributing
---------------

Issues and Pull Requests are welcome!

1.  Fork this project
2.  Create a feature branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

* * *

📊 Star History
---------------

**⭐ Star the repo if you like it**

Report Bug · Request Feature
