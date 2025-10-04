---
project: visx
stars: 20286
description: 🐯 visx | visualization components
url: https://github.com/airbnb/visx
---

### visx

visx is a collection of reusable low-level visualization components. visx combines the power of d3 to generate your visualization with the benefits of react for updating the DOM.

  

**Docs** • **Gallery** • **Blog** • **Discussions** • **Changelog** • **Getting started tutorial**

Usage
-----

Let's make a simple bar graph.

First we'll install the relevant packages:

npm install --save @visx/mock-data @visx/group @visx/shape @visx/scale

import React from 'react';
import { letterFrequency } from '@visx/mock-data';
import { Group } from '@visx/group';
import { Bar } from '@visx/shape';
import { scaleLinear, scaleBand } from '@visx/scale';

// We'll use some mock data from \`@visx/mock-data\` for this.
const data \= letterFrequency;

// Define the graph dimensions and margins
const width \= 500;
const height \= 500;
const margin \= { top: 20, bottom: 20, left: 20, right: 20 };

// Then we'll create some bounds
const xMax \= width \- margin.left \- margin.right;
const yMax \= height \- margin.top \- margin.bottom;

// We'll make some helpers to get at the data we want
const x \= d \=> d.letter;
const y \= d \=> +d.frequency \* 100;

// And then scale the graph by our data
const xScale \= scaleBand({
  range: \[0, xMax\],
  round: true,
  domain: data.map(x),
  padding: 0.4,
});
const yScale \= scaleLinear({
  range: \[yMax, 0\],
  round: true,
  domain: \[0, Math.max(...data.map(y))\],
});

// Compose together the scale and accessor functions to get point functions
const compose \= (scale, accessor) \=> data \=> scale(accessor(data));
const xPoint \= compose(xScale, x);
const yPoint \= compose(yScale, y);

// Finally we'll embed it all in an SVG
function BarGraph(props) {
  return (
    <svg width\={width} height\={height}\>
      {data.map((d, i) \=> {
        const barHeight \= yMax \- yPoint(d);
        return (
          <Group key\={\`bar-${i}\`}\>
            <Bar
              x\={xPoint(d)}
              y\={yMax \- barHeight}
              height\={barHeight}
              width\={xScale.bandwidth()}
              fill\="#fc2e1c"
            />
          </Group\>
        );
      })}
    </svg\>
  );
}

// ... somewhere else, render it ...
// <BarGraph />

For more examples using `visx`, check out the gallery.

Motivation
----------

**Goal**

The goal is to create a library of components you can use to make both your own reusable chart library or your slick custom one-off chart. visx is largely unopinionated and is meant to be built upon. Keep your bundle sizes down and use only the packages you need.

**How?**

Under the hood, visx is using d3 for the calculations and math. If you're creating your own awesome chart library on top of visx, it's easy to create a component api that hides d3 entirely. Meaning your team could create charts as easily as using reusable react components.

**But why?**

Mixing two mental models for updating the DOM is never a good time. Copy and pasting d3 code into `componentDidMount()` is just that. This collection of components lets you easily build your own reusable visualization charts or library without having to learn d3. No more selections or `enter()`/`exit()`/`update()`.

In the wild
-----------

-   williaster/data-ui (Demo)
-   dylanmoz/trello (Demo) (How to Make Beautiful Graphs With vx and React-Motion)
-   gkunthara/Crypto-Chart (Tutorial)
-   Collapsible tree with `react-move` by @techniq (Demo) (Radial demo) (More info)
-   Bitcoin 30-day price by @hshoff (Github) (YouTube)
-   Ethereum candlestick chart by @hshoff (Github)
-   Song data visualization through spotify by @bother7 (Github)
-   Investment Calculator (website)
-   Animation with `react-spring` by @drcmda (Demo)
-   Code Coverage Dashboard by @ezy (Github)
-   Ethereum Portfolio Toolkit by @JayWelsh (Demo) (Github)
-   Family tree by @vkallore (Github)
-   South African Coronavirus Data Visuals by @JayWelsh (Demo) (Github)
-   CNN: Tracking America's Recovery
-   Wall Street Journal: Americans Familiarize Themselves with the Word ‘Forbearance’ by @rayshan (Demo)
-   Dollar to food emoji caculator by @gmlwo530 (Demo) (Github)
-   \[zh-TW\] Taiwan Real-time Air Quality Index by @ArvinH(Demo)(Tutorial)
-   tokenized BTC on ethereum stacked chart with brush by @sakulstra
-   Escape From Tarkov Ammo Chart by @codenomial
-   Pry Finance for Founders (dashboard by @valtism)
-   Data 2 the People Donation Efficacy Analysis for Downballot Races (Demo) (Github)
-   Augora Display information of french deputies (Demo)(Github)
-   WHO Coronavirus (COVID-19) Dashboard is built on top of `vx`, earlier version of `visx`. (Demo)
-   Fig Stats - Figma community plugin & widget analytics
-   Physician.FYI - Explore physicians' disciplinary history
-   Index by Superstardle, Salaries by Superstardle, & Pack'Em by Superstardle - Explore professional sports teams and superstars in the world of underdogs, salaries, and playoff performances.
-   Ridgeline chart visualizing shuffling probabilities by @jmssnr (Demo) (Github)
-   UCSF Data Library - Landing page for disease research tools (Github)

Have a project that's using `visx`? Open a pull request and we'll add it to the list.

FAQ
---

1.  What does `visx` stand for?
    
    > visx stands for visualization components.
    
2.  Do you plan on supporting animation/transitions?
    
    > A common criticism of visx is it doesn't have animation baked in, but this was a conscious choice. It's a powerful feature to not bake it in.
    > 
    > Imagine your app already bundles `react-motion`, adding a hypothetical `@visx/animation` is bloat. Since visx is react, it already supports all react animation libs.
    > 
    > Charting libraries are like style guides. Each org or app will eventually want full control over their own implementation.
    > 
    > visx makes this easier for everyone. No need to reinvent the wheel each time.
    > 
    > more info: #6
    > 
    > examples:
    > 
    > -   Collapsible tree with `react-move` by @techniq (Demo) (Radial demo)
    > -   Animation with `react-spring` by @drcmda (Demo)
    
3.  Do I have to use every package to make a chart?
    
    > nope! pick and choose the packages you need.
    
4.  Can I use this to create my own library of charts for my team?
    
    > Please do.
    
5.  Does visx work with preact?
    
    > yup! need to alias `react` + `react-dom` and use `preact-compat`.
    
6.  I like using d3.
    
    > Me too.
    

Development
-----------

Please see CONTRIBUTING.md

✌️

MIT
