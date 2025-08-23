---
project: BizCharts
stars: 6194
description: Powerful data visualization library based on G2 and React.
url: https://github.com/alibaba/BizCharts
---

通知
==

亲爱的用户朋友们：  
由于组织架构调整，BizCharts 将不再维护 官网站点数据库将于 6 月后下线。  
所有文档资料现已完整迁移至本仓库的 docs 目录，欢迎查阅和使用。  
感谢大家多年来的支持与陪伴！后续如需继续使用图表组件，推荐迁移至 AntV 生态。AntV API 与 BizCharts 同源，迁移成本低，且社区活跃。  
如需迁移协助，DeepSeek 可为您提供智能迁移和答疑服务。如果您的项目仅需维护，无需新功能开发，也可直接通过 DeepSeek 获得技术支持。  
再次感谢大家一路以来的信任与支持！

BizCharts
=========

New charting and visualization library has been released: https://bizcharts.taobao.com/products/bizCharts.

Features
--------

-   React ES6 grammar
-   Easy to use
-   Strong expansion capability
-   Support most data visualization charts

See more demos.

Releases
--------

-   v3.5.x: https://bizcharts.taobao.com/product/bizcharts/gallery
-   V4.0.0: https://bizcharts.taobao.com/product/BizCharts4/gallery

Upgrade document: https://bizcharts.taobao.com/product/BizCharts4/category/61/page/104

Installation
------------

### npm

$ npm install bizcharts

### umd

 <script src\="https://unpkg.com/bizcharts@${version}/umd/BizCharts.min.js"\></script\>

### Dev build

$ git clone https://github.com/alibaba/BizCharts.git
$ cd BizCharts
$ npm install
$ npm start
$ npm run build

### Test snapshot

Does not support external network testing right now.

```
tnpm run uitest
```

Usage
-----

Try it out

import {Chart, Axis, Tooltip, Line, Point} from "bizcharts";

const data \= \[...\];

<Chart height\={400} data\={data} forceFit\>
  <Axis name\="temperature" label\={{formatter: val \=> \`${val}°C\`}} />
  <Line position\="month\*temperature" size\={2} color\={'city'} />
  <Point position\="month\*temperature" size\={4} color\={'city'} />
</Chart\>

### FAQ

### How to Contribute

We welcome all contributions. You could submit any ideas as pull requests. Thank you for your interest and have a good time. Please let us know how can we help. Do check out issues for bug reports or suggestions first.

#### Update

G2 decided to terminate the "Experience Improvement Program". In version `@antv/g2@3.4.7`（released at 2018.12.26）and above, all tracking code is removed, no unexpected remote request will be sent while you are using G2. And Bizcharts Upgrade the dependent version the first time at 2018.12.26 24:00.

### License

BizCharts is available under the License MIT.
