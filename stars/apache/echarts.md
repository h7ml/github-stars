---
project: echarts
stars: 64721
description: Apache ECharts is a powerful, interactive charting and data visualization library for browser
url: https://github.com/apache/echarts
---

Apache ECharts
==============

Apache ECharts is a free, powerful charting and visualization library offering easy ways to add intuitive, interactive, and highly customizable charts to your commercial products. It is written in pure JavaScript and based on zrender, which is a whole new lightweight canvas library.

**中文官网** | **ENGLISH HOMEPAGE**

Get Apache ECharts
------------------

You may choose one of the following methods:

-   Download from the official website
-   `npm install echarts --save`
-   CDN: jsDelivr CDN

Docs
----

-   Get Started
-   API
-   Option Manual
-   Examples

Get Help
--------

-   GitHub Issues for bug report and feature requests
-   Email dev@echarts.apache.org for general questions
-   Subscribe to the mailing list to get updated with the project

Build
-----

Build echarts source code:

Execute the instructions in the root directory of the echarts: (Node.js is required)

# Install the dependencies from NPM:
npm install

# Rebuild source code immediately in watch mode when changing the source code.
# It opens the \`./test\` directory, and you may open \`-cases.html\` to get the list
# of all test cases.
# If you wish to create a test case, run \`npm run mktest:help\` to learn more.
npm run dev

# Check the correctness of TypeScript code.
npm run checktype

# If intending to build and get all types of the "production" files:
npm run release

Then the "production" files are generated in the `dist` directory.

Contribution
------------

Please refer to the contributing document if you wish to debug locally or make pull requests.

Resources
---------

### Awesome ECharts

https://github.com/ecomfe/awesome-echarts

### Extensions

-   ECharts GL An extension pack of ECharts, which provides 3D plots, globe visualization, and WebGL acceleration.
    
-   Liquidfill 水球图
    
-   Wordcloud 字符云
    
-   Extension for Baidu Map 百度地图扩展 An extension provides a wrapper of Baidu Map Service SDK.
    
-   vue-echarts ECharts component for Vue.js
    
-   echarts-stat Statistics tool for ECharts
    

License
-------

ECharts is available under the Apache License V2.

Code of Conduct
---------------

Please refer to Apache Code of Conduct.

Paper
-----

Deqing Li, Honghui Mei, Yi Shen, Shuang Su, Wenli Zhang, Junting Wang, Ming Zu, Wei Chen. ECharts: A Declarative Framework for Rapid Construction of Web-based Visualization. Visual Informatics, 2018.
