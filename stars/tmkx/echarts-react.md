---
project: echarts-react
stars: 2
description: [🚧 WIP] Using ECharts in React the Idiomatic Way, with Treeshaking Support! 🍃
url: https://github.com/tmkx/echarts-react
---

@fanciers/echarts-react
=======================

> Using ECharts in React the Idiomatic Way, with Treeshaking Support! 🍃

npm install @fanciers/echarts-react

import { CanvasRenderer, LineChart, echarts } from '@fanciers/echarts-react';

echarts.use(\[CanvasRenderer\]);

function Demo() {
  return (
    <LineChart
      style\={{ width: 480, height: 300 }}
      xAxis\={{
        type: 'category',
        data: \['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'\],
      }}
      yAxis\={{ type: 'value' }}
      series\={\[
        {
          type: 'line',
          data: \[150, 230, 224, 218, 135, 147, 260\],
        },
      \]}
    /\>
  );
}
