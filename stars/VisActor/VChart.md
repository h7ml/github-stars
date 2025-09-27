---
project: VChart
stars: 1667
description: VChart, more than just a cross-platform charting library, but also an expressive data storyteller.
url: https://github.com/VisActor/VChart
---

VChart
======

VChart, more than just a cross-platform charting library, but also an expressive data storyteller.

Introduction • Demo • Tutorial • API• Cross-Platform

English | 简体中文 | 日本語

（video）

Introduction
------------

VChart is a charting component library in VisActor visualization system. It wraps the charting logic based on visual grammar library VGrammar and the component encapsulation based on visual rendering engine VRender. The core capabilities are as follows:

1.  **Cross-platform**: Automatically adapt to desktop, H5, and multiple small program environments
2.  **Storytelling**: Comprehensive annotation, animation, flow control, narrative templates, and other enhanced features for visual storytelling
3.  **Scenes**: Deliver visual storytelling capabilities to end-users, unlock developer productivity

### Repository Introduction

This repository includes the following packages:

1.  `vchart`: The core code repository of VChart
2.  `react-vchart`: The VChart component encapsulated based on React
3.  `taro-vchart`: The VChart component encapsulated based on Taro
4.  `lark-vchart`: The VChart component encapsulated based on Lark miniAPP
5.  `block-vchart`: The VChart component encapsulated based on Lark Block
6.  `wx-vchart`：The VChart component encapsulated based on Wx miniAPP
7.  `docs`: VChart site source code, and also contains all Chinese and English documents, chart sample codes, etc. of the site.

🔨 Usage
--------

### 📦 Installation

# npm
$ npm install @visactor/vchart

# yarn
$ yarn add @visactor/vchart

### 📊 A Chart Example

import VChart from '@visactor/vchart';

const spec \= {
  type: 'bar',
  data: \[
    {
      id: 'barData',
      values: \[
        { month: 'Monday', sales: 22 },
        { month: 'Tuesday', sales: 13 },
        { month: 'Wednesday', sales: 25 },
        { month: 'Thursday', sales: 29 },
        { month: 'Friday', sales: 38 }
      \]
    }
  \],
  xField: 'month',
  yField: 'sales',
  crosshair: {
    xField: { visible: true }
  }
};

// 'chart' is the id of your dom container, such as <div id="chart"></chart>
const vchart \= new VChart(spec, { dom: 'chart' });
vchart.renderAsync();

⌨️ Development
--------------

First of all, please install @microsoft/rush

$ npm i --global @microsoft/rush

Then clone locally:

# clone
$ git clone git@github.com:VisActor/VChart.git
$ cd VChart
# install dependencies
$ rush update
# start vchart development server
$ rush start
# start react-vchart development server
$ rush react
# start site development server
$ rush docs

📖 Documents
============

After installation & clone & update, run docs to preview VTable documents locally.

# start vtable document server. execute in file path: ./
$ rush update
$ rush build
$ rush docs

If you meet dependency problems
===============================

$ rush purge
$ rush update

🔗 Related Links
----------------

-   Homepage
-   VCharts Gallery
-   VChart Tutorials
-   VChart Options
-   VChart API
-   VGrammar
-   VRender
-   FAQ
-   CodeSandbox Template for bug reports

💫 Ecosystem
------------

Project

Description

React-VChart

React interface for @VisActor/VChart

OpenInula-VChart

OpenInula VChart Components

OMI

Web Components Framework

A vercel template built with vchart and Next.js

A modern dashboard template built with vchart and Next.js, featuring a beautiful UI and rich data visualization components.

💖 Thanks
---------

Thanks to Semi for providing the theme visualization customization solution.

🤝 Contribution
---------------

If you would like to contribute, please read the Code of Conduct and our contributing guide first。

Small streams converge to make great rivers and seas!
