---
project: gcoord
stars: 3213
description: 地理坐标系转换工具
url: https://github.com/hujiulong/gcoord
---

Gcoord
======

**gcoord**(**g**eographic **coord**inates)是一个处理地理坐标系的JS库，用来修正百度地图、高德地图及其它互联网地图坐标系不统一的问题。

支持转换坐标数组和 GeoJSON 数据，无外部依赖，能在 nodejs、所有现代浏览器（IE8+）和 React Native 等环境中运行，gzip后仅3kb。

更多信息可以阅读地理坐标系

🚨 注意
-----

在发布、展示、传播数据时，请务必遵守相关法律规定

> （禁止）未经批准，在测绘活动中擅自采用国际坐标系统  
> — 中华人民共和国测绘法，40 (1)

> 导航电子地图在公开出版、销售、传播、展示和使用前，必须进行空间位置技术处理。  
> — GB 20263―2006《导航电子地图安全处理技术基本要求》，4.1

安装
--

通过npm安装:

npm install gcoord --save

或者直接在页面中通过 script 标签引入:

<script src\="https://unpkg.com/gcoord/dist/gcoord.global.prod.js"\></script\>

注意：通过 script 标签引入时请务必指定版本号

引入
--

CommonJS:

const gcoord \= require('gcoord');

ES Module:

import gcoord from 'gcoord';

通过 script 标签引入可以直接使用全局变量 `gcoord` 或 `window.gcoord`

使用
--

例如从手机的GPS得到一个经纬度坐标，需要将其展示在百度地图上，则应该将当前坐标从WGS-84坐标系转换为BD-09坐标系

var result \= gcoord.transform(
  \[116.403988, 39.914266\],    // 经纬度坐标
  gcoord.WGS84,               // 当前坐标系
  gcoord.BD09                 // 目标坐标系
);

console.log(result);  // \[116.41661560068297, 39.92196580126834\]

同时gcoord还可以转换GeoJSON对象的坐标系，详细使用方式可以参考API

API
---

### transform(input, from, to)

进行坐标转换

**参数**

-   `input` **GeoJSON | string | Array<number\>** GeoJSON对象，或GeoJSON字符串，或经纬度数组
-   `from` **CRS** 当前坐标系
-   `to` **CRS** 目标坐标系

**返回值**

**GeoJSON | Array<number\>**

**示例**

// 将GCJ02坐标转换为WGS84坐标
var result \= gcoord.transform(\[123, 45\], gcoord.GCJ02, gcoord.WGS84);
console.log(result);  // \[122.99395597, 44.99804071\]

// 转换GeoJSON坐标
var geojson \= {
  "type": "Point",
  "coordinates": \[123, 45\]
}
gcoord.transform(geojson, gcoord.GCJ02, gcoord.WGS84);
console.log(geojson.coordinates); // \[122.99395597, 44.99804071\]

返回数组或GeoJSON对象（由输入决定），**注意：当输入为GeoJSON时，transform会改变输入对象**

### CRS

CRS为坐标系，目标支持以下几种坐标系

CRS            

坐标格式

说明  

gcoord.WGS84

\[lng,lat\]

WGS-84坐标系，GPS设备获取的经纬度坐标

gcoord.GCJ02

\[lng,lat\]

GCJ-02坐标系，google中国地图、soso地图、aliyun地图、mapabc地图和高德地图所用的经纬度坐标

gcoord.BD09

\[lng,lat\]

BD-09坐标系，百度地图采用的经纬度坐标

gcoord.BD09LL

\[lng,lat\]

同BD09

gcoord.BD09MC

\[x,y\]

BD-09米制坐标，百度地图采用的米制坐标，单位：米

gcoord.BD09Meter

\[x,y\]

同BD09MC

gcoord.Baidu

\[lng,lat\]

百度坐标系，BD-09坐标系别名，同BD-09

gcoord.BMap

\[lng,lat\]

百度地图，BD-09坐标系别名，同BD-09

gcoord.AMap

\[lng,lat\]

高德地图，同GCJ-02

gcoord.WebMercator

\[x,y\]

Web Mercator投影，墨卡托投影，同EPSG3857，单位：米

gcoord.WGS1984

\[lng,lat\]

WGS-84坐标系别名，同WGS-84

gcoord.EPSG4326

\[lng,lat\]

WGS-84坐标系别名，同WGS-84

gcoord.EPSG3857

\[x,y\]

Web Mercator投影，同WebMercator，单位：米

gcoord.EPSG900913

\[x,y\]

Web Mercator投影，同WebMercator，单位：米

**支持更多坐标系？** gcoord的目标是处理web地图中的坐标，目前支持的坐标系已经能满足绝大部分要求了，同时gcoord也能保持轻量。如果需要更专业的坐标系处理工具，可以使用proj4js等开源库

LICENSE
-------

MIT
