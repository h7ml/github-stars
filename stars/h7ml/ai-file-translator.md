---
project: ai-file-translator
stars: 29
description: CLI tool to translate Markdown files using OpenAI's language models while preserving the original formatting. || CLI 工具使用 OpenAI 的语言模型翻译文件，同时保留原始格式。
url: https://github.com/h7ml/ai-file-translator
---

ai-markdown-translator
======================

English | 中文 | 한국어

`ai-markdown-translator` is a command-line tool that translates Markdown files from one language to another using OpenAI's language models. It preserves the Markdown syntax while translating the content.

Features
--------

-   Translate Markdown files to any language supported by OpenAI's models
-   Preserve Markdown syntax during translation
-   Support for recursive directory translation
-   Automatic retry mechanism for failed translations
-   Comprehensive logging system
-   Directory structure visualization
-   File failure tracking and recovery

Prerequisites
-------------

-   Node.js (v14 or later)
-   npm (usually comes with Node.js)
-   An OpenAI API key

Installation
------------

1.  Clone this repository or download the source code.
2.  Navigate to the project directory in your terminal.
3.  Install the dependencies:

npm install

1.  Build the project:

npm run build

Scripts
-------

-   `build`: Compiles TypeScript files to JavaScript.
-   `start`: Runs the compiled JavaScript using Node.js.
-   `lint`: Runs ESLint to check for code quality issues in TypeScript files.
-   `lint:fix`: Automatically fixes linting issues in TypeScript files.
-   `format`: Formats code using Prettier for various file types in the `src` directory.
-   `format:check`: Checks code formatting without making changes for various file types in the `src` directory.
-   `postbuild`: Makes the compiled `index.js` file executable.
-   `changelog`: Generates a changelog based on conventional commits.
-   `version`: Updates the changelog and stages it for commit when versioning.
-   `test`: Builds the project and runs the test.

Usage
-----

You can run the CLI tool using Node.js, `npx`, or as a standalone executable (if you've packaged it).

### Using Node.js

node dist/index.js --input <input-file\> --output <output-file\> --language <target-language\> \[options\]

### Using npx

npx ai-markdown-translator -i <input-file\> -o <output-file\> -l <target-language\> \[options\]

For example:

npx ai-markdown-translator -u https://gitee.com/h7ml/ai-markdown-translator/raw/main/README.md -o output.md -l "Italian"

### Using the standalone executable

./ai-markdown-translator --input <input-file\> --output <output-file\> --language <target-language\> \[options\]

Options
-------

-   `--input`, `-i`: Input Markdown file or directory (alternative to `--url`). This option allows you to specify the path to the Markdown file or directory you want to translate.
-   `--url`, `-u`: URL of a Markdown file to translate (alternative to `--input`). Use this option to provide a direct link to a Markdown file that you want to translate.
-   `--extension`, `-e`: Specify the file extension to translate (e.g., `md`). If not provided, all files will be processed. This option allows you to filter which files to translate based on their extension.
-   `--rename`: Whether to modify the file name. If true, the output file will be named `<original-filename>-translated.<extension>`. This option allows you to specify if you want to append a suffix to the translated file name.
-   `--output`, `-o`: Output Markdown file (if not provided, defaults to the input file name). This option allows you to specify the name of the output file where the translated content will be saved.
-   `--language`, `-l`: Target language for translation (required). This option specifies the language into which you want the Markdown content to be translated.
-   `--openai-url`: OpenAI API URL (default: uses `OPENAI_URL` environment variable). This option allows you to specify a custom URL for the OpenAI API if needed.
-   `--api-key`: OpenAI API Key (default: uses `API_KEY` environment variable). This option is used to provide your OpenAI API key for authentication.
-   `--model`: OpenAI Model to use (default: uses `MODEL` environment variable or `gpt-3.5-turbo`). This option allows you to specify which OpenAI model to use for translation.
-   `--help`, `-h`: Show help. This option displays the help information for the command-line tool.
-   `--show-version`, `-v`: Show version. This option displays the current version of the tool.
-   `--log`: Enable logging (default: false). Enables detailed logging of the translation process, including success and failure information.
-   `--log-file`: Specify the log file path (default: `<project_root>/log/translator-err.log`). The file where translation errors and failures will be logged.
-   `--log-dir`: Specify the log directory (default: `<project_root>/log`). The directory where all log files will be stored.
-   `--locale`: Log message language setting (default: 'zh'). This option allows you to specify the language for log messages (choices: 'en', 'zh', 'ko').
-   `--retry-count`: Number of retry attempts for failed translations (default: 3). How many times the translator should attempt to retry failed translations.
-   `--retry-delay`: Delay in seconds between retry attempts (default: 10). How long to wait between retry attempts.
-   `--path`, `-p`: Display directory structure (default: current script directory). Shows a tree view of the specified directory structure.

> Note: `--input` and `--url` are mutually exclusive; you must provide one or the other.

Environment Variables
---------------------

You can set the following environment variables instead of passing them as command-line arguments:

-   `OPENAI_URL`: The URL for the OpenAI API.
-   `API_KEY`: Your OpenAI API key.
-   `MODEL`: The OpenAI model to use (e.g., `'gpt-3.5-turbo'`).

You can set these in a `.env` file in the project root or export them in your shell.

Examples
--------

1.  **Translate a Markdown file from English to Spanish:**

npx ai-markdown-translator -i english.md -o spanish.md -l "Spanish"

1.  **Translate using a specific OpenAI model:**

npx ai-markdown-translator -i input.md -o output.md -l "French" --model "gpt-4"

1.  **Translate with custom OpenAI URL and API key:**

npx ai-markdown-translator -i input.md -o output.md -l "German" --openai-url "https://api.302.ai/v1/chat/completions" --api-key "sk-302-api-key"

1.  **Translate the Markdown content of a URL:**

npx ai-markdown-translator -u https://gitee.com/h7ml/ai-markdown-translator/raw/main/README.md -o output.md -l "Italian"

1.  **Translate all Markdown files in a directory and rename them:**

npx ai-markdown-translator -i ./markdown-files -l "Chinese" --rename

1.  **Translate a Markdown file and specify the output file name:**

npx ai-markdown-translator -i example.md -o translated\_example.md -l "Japanese"

1.  **Translate with logging and retry options:**

npx ai-markdown-translator -i ./docs -o ./translated -l "Chinese" --log --retry-count 5 --retry-delay 15

1.  **Translate with custom log directory:**

npx ai-markdown-translator -i input.md -o output.md -l "Japanese" --log --log-dir "./custom-logs"

1.  **Translate with all logging and retry options:**

npx ai-markdown-translator -i ./markdown-files -l "French" \\
  --log \\
  --log-dir "./logs" \\
  --log-file "./logs/translation.log" \\
  --retry-count 3 \\
  --retry-delay 5

1.  **Display directory structure:**

npx ai-markdown-translator -p ./src

Output example:

```
📂 Directory structure: /path/to/src
.
├── 📁 components
│   ├── 📄 Button.tsx
│   └── 📄 Input.tsx
├── 📁 utils
│   ├── 📄 logger.ts
│   └── 📄 translator.ts
└── 📄 index.ts
```

1.  **Translate with automatic retry and logging:**

npx ai-markdown-translator -i ./docs -o ./translated -l "Chinese" \\
  --log \\
  --retry-count 5 \\
  --retry-delay 15 \\
  --log-file "./logs/translation.log"

1.  **Translate directory with failure tracking:**

npx ai-markdown-translator -i ./markdown-files -o ./output -l "Japanese" \\
  --log \\
  --log-dir "./logs" \\
  --retry-count 3 \\
  --retry-delay 10

License
-------

MIT License

Git Information
---------------

-   **Repository**: h7ml/ai-markdown-translator
-   **Issues**: Report Issues

Version Information
-------------------

-   **Current Version**:
-   **NPM Package**: ai-markdown-translator

CI Information
--------------

This project uses GitHub Actions for continuous integration. The CI workflow includes:

-   Linting the code with ESLint
-   Running tests (if applicable)
-   Building the project
-   Caching dependencies for faster builds

Contributing
------------

Contributions are welcome! Please feel free to submit a Pull Request.

Support
-------

If you encounter any problems or have any questions, please open an issue in this repository.
