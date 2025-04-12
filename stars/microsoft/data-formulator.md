---
project: data-formulator
stars: 11246
description: 🪄 Create rich visualizations with AI 
url: https://github.com/microsoft/data-formulator
---

**Data Formulator: Create Rich Visualizations with AI**
=======================================================

     

Transform data and create rich visualizations iteratively with AI 🪄. Try Data Formulator now!

News 🔥🔥🔥
-----------

-   \[03-20-2025\] Data Formulator 0.1.7: Anchoring ⚓︎
    
    -   Anchor an intermediate dataset, so that followup data analysis are built on top of the anchored data, not the original one.
    -   Clean a data and work with only the cleaned data; create a subset from the original data or join multiple data, and then focus your analysis from there. The AI agent will be less likely to get confused and work faster. ⚡️⚡️
    -   Check out the demos at \[https://github.com/microsoft/data-formulator/releases/tag/0.1.7\]
    -   Don't forget to update Data Formulator to test it out!
-   \[02-20-2025\] Data Formulator 0.1.6 released!
    
    -   Now supports working with multiple datasets at once! Tell Data Formulator which data tables you would like to use in the encoding shelf, and it will figure out how to join the tables to create a visualization to answer your question. 🪄
    -   Checkout the demo at \[https://github.com/microsoft/data-formulator/releases/tag/0.1.6\].
    -   Update your Data Formulator to the latest version to play with the new features.
-   \[02-12-2025\] More models supported now!
    
    -   Now supports OpenAI, Azure, Ollama, and Anthropic models (and more powered by LiteLLM);
    -   Models with strong code generation and instruction following capabilities are recommended (gpt-4o, claude-3-5-sonnet etc.);
    -   You can store API keys in `api-keys.env` to avoid typing them every time (see template `api-keys.env.template`).
    -   Let us know which models you have good/bad experiences with, and what models you would like to see supported! \[comment here\]
-   \[11-07-2024\] Minor fun update: data visualization challenges!
    
    -   We added a few visualization challenges with the sample datasets. Can you complete them all? \[try them out!\]
    -   Comment in the issue when you did, or share your results/questions with others! \[comment here\]
-   \[10-11-2024\] Data Formulator python package released!
    
    -   You can now install Data Formulator using Python and run it locally, easily. \[check it out\].
    -   Our Codespaces configuration is also updated for fast start up ⚡️. \[try it now!\]
    -   New experimental feature: load an image or a messy text, and ask AI to parse and clean it for you(!). \[demo\]
-   \[10-01-2024\] Initial release of Data Formulator, check out our \[blog\] and \[video\]!
    

Overview
--------

**Data Formulator** is an application from Microsoft Research that uses large language models to transform data, expediting the practice of data visualization.

Data Formulator is an AI-powered tool for analysts to iteratively create rich visualizations. Unlike most chat-based AI tools where users need to describe everything in natural language, Data Formulator combines _user interface interactions (UI)_ and _natural language (NL) inputs_ for easier interaction. This blended approach makes it easier for users to describe their chart designs while delegating data transformation to AI.

Get Started
-----------

Play with Data Formulator with one of the following options:

-   **Option 1: Install via Python PIP**
    
    Use Python PIP for an easy setup experience, running locally (recommend: install it in a virtual environment).
    
    # install data\_formulator
    pip install data\_formulator
    
    # start data\_formulator
    data\_formulator 
    
    # alternatively, you can run data formulator with this command
    python -m data\_formulator
    
    Data Formulator will be automatically opened in the browser at http://localhost:5000.
    
    _Update: you can specify the port number (e.g., 8080) by `python -m data_formulator --port 8080` if the default port is occupied._
    
-   **Option 2: Codespaces (5 minutes)**
    
    You can also run Data Formulator in Codespaces; we have everything pre-configured. For more details, see CODESPACES.md.
    
-   **Option 3: Working in the developer mode**
    
    You can build Data Formulator locally if you prefer full control over your development environment and the ability to customize the setup to your specific needs. For detailed instructions, refer to DEVELOPMENT.md.
    

Using Data Formulator
---------------------

Once you've completed the setup using either option, follow these steps to start using Data Formulator:

### The basics of data visualization

-   Provide OpenAI keys and select a model (GPT-4o suggested) and choose a dataset.
-   Choose a chart type, and then drag-and-drop data fields to chart properties (x, y, color, ...) to specify visual encodings.

renewable.mp4

### Create visualization beyond the initial dataset (powered by 🤖)

-   You can type names of **fields that do not exist in current data** in the encoding shelf:
    -   this tells Data Formulator that you want to create visualizations that require computation or transformation from existing data,
    -   you can optionally provide a natural language prompt to explain and clarify your intent (not necessary when field names are self-explanatory).
-   Click the **Formulate** button.
    -   Data Formulator will transform data and instantiate the visualization based on the encoding and prompt.
-   Inspect the data, chart and code.
-   To create a new chart based on existing ones, follow up in natural language:
    -   provide a follow up prompt (e.g., _\`\`show only top 5!''_),
    -   you may also update visual encodings for the new chart.

renewable-pct.mp4 renewable-rank.mp4

Repeat this process as needed to explore and understand your data. Your explorations are trackable in the **Data Threads** panel.

Developers' Guide
-----------------

Follow the developers' instructions to build your new data analysis tools on top of Data Formulator.

Research Papers
---------------

-   Data Formulator 2: Iteratively Creating Rich Visualizations with AI

```
@article{wang2024dataformulator2iteratively,
      title={Data Formulator 2: Iteratively Creating Rich Visualizations with AI}, 
      author={Chenglong Wang and Bongshin Lee and Steven Drucker and Dan Marshall and Jianfeng Gao},
      year={2024},
      booktitle={ArXiv preprint arXiv:2408.16119},
}
```

-   Data Formulator: AI-powered Concept-driven Visualization Authoring

```
@article{wang2023data,
  title={Data Formulator: AI-powered Concept-driven Visualization Authoring},
  author={Wang, Chenglong and Thompson, John and Lee, Bongshin},
  journal={IEEE Transactions on Visualization and Computer Graphics},
  year={2023},
  publisher={IEEE}
}
```

Contributing
------------

This project welcomes contributions and suggestions. Most contributions require you to agree to a Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions provided by the bot. You will only need to do this once across all repositories using our CLA.

This project has adopted the Microsoft Open Source Code of Conduct. For more information see the Code of Conduct FAQ or contact opencode@microsoft.com with any additional questions or comments.

Trademarks
----------

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft trademarks or logos is subject to and must follow Microsoft's Trademark & Brand Guidelines. Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship. Any use of third-party trademarks or logos are subject to those third-party's policies.
