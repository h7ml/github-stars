---
project: leafer-x-ruler
stars: 28
description: leafer-ui的标尺线插件
url: https://github.com/LvHuaiSheng/leafer-x-ruler
---

leafer-x-ruler
==============

标尺线插件

支持不同单位px、cm、in、pt、pc、mm转换， 以及自定义单位

show
----

### 1.X版本文档请查看：V1.x文档

#### 如何从1.x升级到2.x

> 1.  只需将1.x中自定义的config和options配置项合并即可，如无自定义配置项 那么可直接升级，参考下方配置
> 2.  2.x版本调整了`themes`初始化配置项，将Map对象改为普通对象，初始化速度更快，自定义主题更便捷

// -- 1.x版本 --
const config\={
  enabled: true,
}
const options\={
  ruleSize: 20,
}
const ruler \= new Ruler(app,config,options)

// -- 2.x版本，只需将config和options合并即可 --
const config\={
  enabled: true,
  ruleSize: 20,
}
const ruler \= new Ruler(app,config)

### use

#### 基本使用

import { App } from 'leafer-ui'
import { Ruler } from 'leafer-x-ruler'

const app \= new App({
  view: window,
  tree: {},
  editor: {},
})

// 实例化标尺插件
const ruler \= new Ruler(app)

// 启用、禁用  
ruler.enabled \= false

#### 自定义配置示例

import { App } from 'leafer-ui'
import { Ruler } from 'leafer-x-ruler'

const app \= new App({
  view: window,
  tree: {},
  editor: {},
})

// 实例化标尺插件，传入自定义配置
const ruler \= new Ruler(app,{
  // 使用自定义的单位
  unit:'cs',
  // 添加自定义单位
  conversionFactors: {
    // 自定义单位cs
    cs: {
      px: 2,
      gaps: \[5000, 2500, 1000, 500, 200, 100, 50, 20, 10\],
      defaultGap: 1000
    }
  }
})

// 添加自定义主题  
ruler.addTheme('custom1', {
  backgroundColor: '#6cb0ab',
  textColor: '#a45454',
  borderColor: '#6f4593',
  highlightColor: 'rgba(22,93,255,0.75)'
})

// 切换主题  
ruler.changeTheme('custom1')

// 切换字体
ruler.changeUnit('px')

// 启用、禁用  
ruler.enabled \= false

### QA

// 如果使用侧边栏的伸缩时标尺宽高并未同步更新，或许是因为画布的大小并未改变无法触发resize事件；如果想改变画布的大小并使标尺同步，需要自行监听窗口大小变化，并触发leafer-ui的resize事件，以下是在vue3中使用的示例： 
<template\>
  <div ref\="divRef"\></div\>
</template\>
<script lang\="ts" setup\>
  import {useResizeObserver} from "@vueuse/core";

  const divRef \= ref()

  onMounted(() \=> {
      useResizeObserver(divRef, (entries) \=> {
        const \[entry\] \= entries
        const { width, height } \= entry.contentRect
        // 这步是为了触发leafer-ui的resize事件，标尺在监听到resize事件后会重新渲染
        leafer.app.resize({ width, height })
      })
  })
</script\>

内置属性
----

属性

说明

操作方式

类型

示例值

默认

enabled

启用、禁用

get / set

boolean

true

true

theme

使用主题名称

get / set

string

dark

light

rulerLeafer

标尺线层Leafer

get

Leafer

\-

\-

config

标尺设置

set

RulerConfig

\-

\-

内置方法
----

方法

说明

参数类型

示例值

changeEnabled

启用、禁用

(boolean)

true

addTheme

添加自定义主题

(string,ThemeOption)

\-

removeTheme

移除自定义主题

(string)

\-

changeTheme

切换主题

(string)

\-

addUnit

添加自定义单位

(string,ConversionFactor)

\-

removeUnit

移除自定义单位

(string)

\-

changeUnit

切换单位

(string)

cm

forceRender

强制渲染

\-

#### RulerConfig

type RulerConfig \= {
  /\*\*
   \* 是否启用标尺线
   \*/
  enabled?: boolean
  /\*\*
   \* 标尺线主题，默认light，可选（light：明亮，dark：暗黑）
   \*/
  theme?: string,
  /\*\*
   \* 单位 默认px，内置了px、cm、in、pt、pc、mm
   \*/
  unit?: string,
  /\*\*
   \* 标尺宽高
   \*/
  ruleSize?: number; 
  /\*\*
   \* 字体大小
   \*/
  fontSize?: number;
  /\*\*
   \* 主题，默认存在明亮、暗黑主图
   \*/
  themes?: {\[key: string\]: ThemeOption}
  /\*\*
   \* 定义单位转换因子 (每单位对应的像素数)，（可从源码内查看预设定义）
   \*/
  conversionFactors?: {\[key: string\]: ConversionFactor}; 
}

#### ThemeOption

type ThemeOption \= {
  /\*\*
   \* 背景色
   \*/
  backgroundColor: string,
  /\*\*
   \* 文字颜色
   \*/
  textColor: string,
  /\*\*
   \* 边框颜色
   \*/
  borderColor: string,
  /\*\*
   \* 高亮颜色
   \*/
  highlightColor: string
}

#### ConversionFactor

export interface ConversionFactor {
  /\*\*
   \* 自定义单位对应的像素数，比如英寸单位：1英寸对应96px，那这里就是96
   \*/
  px: number

  /\*\*
   \* 缩放倍率，对应缩放比例：\[0.02, 0.03, 0.05, 0.1, 0.2, 0.5, 1, 2, 5\]
   \*/
  gaps: number\[\]

  /\*\*
   \* 默认缩放倍率（如果没有匹配到缩放比例对应的倍率，则使用默认值defaultGap）
   \*/
  defaultGap: number
}

运行源码
----

npm run start # 开始运行项目

npm run build # 打包插件代码，同时会创建types

npm run test # 自动化测试

usage
-----

### install

npm i leafer-x-ruler
