---
project: stock-api
stars: 992
description: 股票接口 | 韭菜小猪 | A股 | 美股 | 港股 | 股票 | 基金 | JavaScript
url: https://github.com/zhangxiangliang/stock-api
---

股票数据小助手
=======

简介
--

一款聚焦在 `股票实时数据` 和 `周边相关服务` 的接口小助手。

股票数据
----

### 已实现

名称

接口名

搜索股票代码

获取股票实时数据

获取股票组实时数据

官网

网易财经

netease

已实现

已实现

已实现

传送门

腾讯股票

tencent

已实现

已实现

已实现

传送门

### 待实现

名称

接口名

搜索股票代码

获取股票实时数据

获取股票组实时数据

官网

雪球

xueqiu

已实现

待实现

待实现

传送门

新浪股票

sina

已实现

待实现

待实现

传送门

安装
--

npm install stock-api

使用
--

### 接口概览

-   选择数据源
-   搜索股票代码
-   获取股票实时数据
-   获取股票组实时数据

### 股票代码

由于每个交易所数据规则不一样，为了能统一规范对代码定义了规则 `交易所+股票代码`。

交易所

代号

实例

上海交易所

SH

SH000001

深圳交易所

SZ

SZ399001

香港交易所

HK

HKHSI

美国交易所

US

USDJI

### 选择数据源

##### 可选导入

import { stocks } from "stock-api";

// 数据源
const netease \= stocks.netease;
const tencent \= stocks.tencent;

### 搜索股票代码

##### 示例

import { stocks } from "stock-api";

// 获取股票组实时数据
stocks.netease.searchStocks(\["510500"\]).then(console.log);

##### 输出

\[
  {
    code: "SH510500",
    name: "500ETF",
    percent: 0.028383,
    now: 7.174,
    low: 6.93,
    high: 7.184,
    yesterday: 6.976,
  },
\];

### 获取股票实时数据

##### 示例

import { stocks } from "stock-api";

// 获取股票实时数据
stocks.netease.getStock("SH510500").then(console.log);

##### 输出

{
  code: 'SH510500',
  name: '500ETF',
  percent: 0.028383,
  now: 7.174,
  low: 6.93,
  high: 7.184,
  yesterday: 6.976
}

### 获取股票组实时数据

##### 示例

import { stocks } from "stock-api";

// 获取股票组实时数据
stocks.netease.getStocks(\["SH510500"\]).then(console.log);

##### 输出

\[
  {
    code: "SH510500",
    name: "500ETF",
    percent: 0.028383,
    now: 7.174,
    low: 6.93,
    high: 7.184,
    yesterday: 6.976,
  },
\];

一起成长
----

-   在困惑的城市里总少不了并肩同行的 伙伴 让我们一起成长。
-   如果您想激励小二可以到 Github 给个 小星星。
