---
project: rc-charts
stars: 21
description: 一个基于BizCharts的图表库
url: https://github.com/alitajs/rc-charts
---

rc-charts
=========

该项目归档，推荐使用 ant-design-charts

> 封装BizCharts库

**项目由来: BizCharts 使用起来相对比较繁琐，比较难于在项目在推广，故封装下常见的图表，简化使用方式，减少学习成本。**

特性
==

-   💡 TypeScript: 使用TypeScript编写
-   🎉 基于BizCharts: 阿里出品
-   🌴 简单易用: 针对常见图表二次封装，可傻瓜式使用
-   🍁 示例丰富: 尽可能多的提供图表示例

使用
--

-   安装

```
yarn add rc-charts
```

-   使用

```
import { Bar } form 'rc-charts';

const Example: React.FC = () => {
  return (
    <Bar
      data={
        [
          { x: '1951', y1: 20 },
          { x: '1952', y1: 10 },
          { x: '1953', y1: 20 },
          { x: '1954', y1: 100 },
          { x: '1955', y1: 10 },
          { x: '1956', y1: 50 }
        ]
      }
      titleMap={{
        y1: '销售额'
      }}
    />
  )
}

export default Example;
```
