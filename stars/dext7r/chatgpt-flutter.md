---
project: chatgpt-flutter
stars: 9
description: A Flutter real-time chat app based on the chatbot GPT-3.
url: https://github.com/dext7r/chatgpt-flutter
---

ChatGpt Flutter
---------------

A Flutter real-time chat app based on the chatbot GPT-3.

### Features

-   Users can input their own messages to interact with the chatbot.
-   Supports copying messages from chat logs to paste into other applications.

### Installation

1.  Clone the repository.
    
    git clone git@github.com:h7ml/chatgpt-flutter.git
    
2.  Getting Started
    

-   Install dependencies
    
    flutter pub get
    
-   Copy the `.env.example` file, then rename it to `.env`
    
    cp .env.example .env
    
-   Add your OpenAI API key to the `.env` file.
    
    API\_KEY=YOUR\_OPENAI\_API\_KEY
    

1.  Run the app.

-   To run the app on an Web Server:
    
     flutter run -d web-server --web-renderer html
    
-   To run the app on an iOS simulator:
    
    flutter run -d iPhone
    
-   To run the app on a specific Android emulator:
    
    flutter run -d emulator-5554
    
-   To run the app on a connected iOS device:
    
    flutter run -d device-name
    
-   To run the app on the web using the Chrome browser:
    
    flutter run -d chrome
    
-   To run the app on a macOS desktop:
    
    flutter run -d macos
    
-   To run the app on a Windows desktop:
    
    flutter run -d windows
    
-   To run the app on a Linux desktop:
    
    flutter run -d linux
    

You can customize the flutter run command with many options to run the app on different platforms and devices. For more information, check out the Flutter documentation.

### Author

-   Author: h7ml
-   Email: h7ml@qq.com
