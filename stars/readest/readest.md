---
project: readest
stars: 11686
description: Readest is a modern, feature-rich ebook reader designed for avid readers offering seamless cross-platform access, powerful tools, and an intuitive interface to elevate your reading experience.
url: https://github.com/readest/readest
---

Readest
=======

  

Readest is an open-source ebook reader designed for immersive and deep reading experiences. Built as a modern rewrite of Foliate, it leverages Next.js 15 and Tauri v2 to deliver a smooth, cross-platform experience across macOS, Windows, Linux, Android, iOS, and the Web.

  
  

Features • Planned Features • Screenshots • Downloads • Getting Started • Troubleshooting • Support • License

Features
--------

✅ Implemented

**Feature**

**Description**

**Status**

**Multi-Format Support**

Support EPUB, MOBI, KF8 (AZW3), FB2, CBZ, TXT, PDF (experimental)

✅

**Scroll/Page View Modes**

Switch between scrolling or paginated reading modes.

✅

**Full-Text Search**

Search across the entire book to find relevant sections.

✅

**Annotations and Highlighting**

Add highlights, bookmarks, and notes to enhance your reading experience.

✅

**Excerpt Text for Note-Taking**

Easily excerpt text from books for detailed notes and analysis.

✅

**Dictionary/Wikipedia Lookup**

Instantly look up words and terms when reading.

✅

**Parallel Read**

Read two books or documents simultaneously in a split-screen view.

✅

**Customize Font and Layout**

Adjust font, layout, theme mode, and theme colors for a personalized experience.

✅

**File Association and Open With**

Quickly open files in Readest in your file browser with one-click.

✅

**Sync across Platforms**

Synchronize book files, reading progress, notes, and bookmarks across all supported platforms.

✅

**Translate with DeepL**

From a single sentence to the entire book—translate instantly with DeepL.

✅

**Translate with Yandex**

Instantly translate text or books using Yandex Translate.

✅

**Text-to-Speech (TTS) Support**

Enjoy smooth, multilingual narration—even within a single book.

✅

**Library Management**

Organize, sort, and manage your entire ebook library.

✅

**Code Syntax Highlighting**

Read software manuals with rich coloring of code examples.

✅

Planned Features
----------------

🛠 Building

🔄 Planned

**Feature**

**Description**

**Priority**

**Sync with Koreader**

Synchronize reading progress, notes, and bookmarks with Koreader devices.

🛠

**AI-Powered Summarization**

Generate summaries of books or chapters using AI for quick insights.

🛠

**Keyboard Navigation**

Implement vimium-style keybindings for book navigation.

🔄

**Support OPDS/Calibre**

Integrate OPDS/Calibre to access online libraries and catalogs.

🔄

**Audiobook Support**

Extend functionality to play and manage audiobooks.

🔄

**Handwriting Annotations**

Add support for handwriting annotations using a pen on compatible devices.

🔄

**Advanced Reading Stats**

Track reading time, pages read, and more for detailed insights.

🔄

**In-Library Full-Text Search**

Search across your entire ebook library to find topics and quotes.

🔄

Stay tuned for continuous improvements and updates! Contributions and suggestions are always welcome—let's build the ultimate reading experience together. 😊

Screenshots
-----------

* * *

Downloads
---------

### Mobile Apps

    

### Platform-Specific Downloads

-   macOS / iOS / iPadOS : Search for "Readest" on the App Store, also available on TestFlight for beta test (send your Apple ID to readestapp@gmail.com to request access).
-   Windows / Linux / Android: Visit https://readest.com or the Releases on GitHub.
-   Web: Visit https://web.readest.com.

Requirements
------------

-   **Node.js** and **pnpm** for Next.js development
-   **Rust** and **Cargo** for Tauri development

For the best experience to build Readest for yourself, use a recent version of Node.js and Rust. Refer to the Tauri documentation for details on setting up the development environment prerequisites on different platforms.

nvm install v22
nvm use v22
npm install -g pnpm
rustup update

Getting Started
---------------

To get started with Readest, follow these steps to clone and build the project.

### 1\. Clone the Repository

git clone https://github.com/readest/readest.git
cd readest

### 2\. Install Dependencies

# might need to rerun this when code is updated
git submodule update --init --recursive
pnpm install
# copy pdfjs-dist to Next.js public directory
pnpm --filter @readest/readest-app setup-pdfjs

### 3\. Verify Dependencies Installation

To confirm that all dependencies are correctly installed, run the following command:

pnpm tauri info

This command will display information about the installed Tauri dependencies and configuration on your platform. Note that the output may vary depending on the operating system and environment setup. Please review the output specific to your platform for any potential issues.

For Windows targets, “Build Tools for Visual Studio 2022” (or a higher edition of Visual Studio) and the “Desktop development with C++” workflow must be installed. For Windows ARM64 targets, the “VS 2022 C++ ARM64 build tools” and "C++ Clang Compiler for Windows" components must be installed. And make sure `clang` can be found in the path by adding `C:\Program Files (x86)\Microsoft Visual Studio\2022\BuildTools\VC\Tools\Llvm\x64\bin` for example in the environment variable `Path`.

### 4\. Build for Development

# Start development for the Tauri app
pnpm tauri dev
# or start development for the Web app
pnpm dev-web
# preview with OpenNext build for the Web app
pnpm preview

For Android:

# Initialize the Android environment (run once)
pnpm tauri android init

pnpm tauri android dev
# or if you want to dev on a real device
pnpm tauri android dev --host

For iOS:

# Set up the iOS environment (run once)
pnpm tauri ios init

pnpm tauri ios dev
# or if you want to dev on a real device
pnpm tauri ios dev --host

### 5\. Build for Production

pnpm tauri build
pnpm tauri android build
pnpm tauri ios build

### 6\. Setup dev environment with Nix

If you have Nix installed, you can leverage flake to enter a development shell with all the necessary dependencies:

nix develop ./ops  # enter a dev shell for the web app
nix develop ./ops#ios # enter a dev shell for the ios app
nix develop ./ops#android # enter a dev shell for the android app

### 7\. More information

Please check the wiki of this project for more information on development.

Troubleshooting
---------------

### 1\. Readest Won’t Launch on Windows (Missing Edge WebView2 Runtime)

**Symptom**

-   When you double-click readest.exe, nothing happens. No window appears, and Task Manager does not show the process.
-   This can affect both the standard installer and the portable version.

**Cause**

-   Microsoft Edge WebView2 Runtime is either missing, outdated, or improperly installed on your system. Readest depends on WebView2 to render the interface on Windows.

**How to Fix**

1.  Check if WebView2 is installed
    -   Open “Add or Remove Programs” (a.k.a. Apps & features) on Windows. Look for “Microsoft Edge WebView2 Runtime.”
2.  Install or Update WebView2
    -   Download the WebView2 Runtime directly from Microsoft: link.
    -   If you prefer an offline installer, download the offline package and run it as an Administrator.
3.  Re-run Readest
    -   After installing/updating WebView2, launch readest.exe again.
    -   If you still encounter problems, reboot your PC and try again.

**Additional Tips**

-   If reinstalling once doesn’t work, uninstall Edge WebView2 completely, then reinstall it with Administrator privileges.
-   Verify your Windows installation has the latest updates from Microsoft.

**Still Stuck?**

-   See Issue readest/readest#358 for further details, or head over to our Discord server and open a support discussion with detailed logs of your environment and the steps you’ve taken.

Contributors
------------

Readest is open-source, and contributions are welcome! Feel free to open issues, suggest features, or submit pull requests. Please **review our contributing guidelines before you start**. We also welcome you to join our Discord community for either support or contributing guidance.

Support
-------

If Readest has been useful to you, consider supporting its development. Your contribution helps us squash bugs faster, improve performance, and keep building great features.

### How to Donate

1.  **GitHub Sponsors**  
    Back the project directly on GitHub:  
    👉 https://github.com/sponsors/readest
    
2.  **Crypto Donations**  
    Prefer crypto? You can donate here:  
    👉 https://donate.readest.com/
    

License
-------

Readest is free software: you can redistribute it and/or modify it under the terms of the GNU Affero General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version. See the LICENSE file for details.

The following libraries and frameworks are used in this software:

-   foliate-js, which is MIT licensed.
-   zip.js, which is licensed under the BSD-3-Clause license.
-   fflate, which is MIT licensed.
-   PDF.js, which is licensed under Apache License 2.0.
-   daisyUI, which is MIT licensed.
-   marked, which is MIT licensed.
-   next.js, which is MIT licensed.
-   react-icons, which has various open-source licenses.
-   react, which is MIT licensed.
-   tauri, which is MIT licensed.

The following fonts are utilized in this software, either bundled within the application or provided through web fonts:

Bitter, Fira Code, Literata, Merriweather, Noto Sans, Roboto, LXGW WenKai, MiSans, Source Han, WenQuanYi Micro Hei

* * *

Happy reading with Readest!
