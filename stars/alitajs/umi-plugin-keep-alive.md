---
project: umi-plugin-keep-alive
stars: 297
description: <KeepAlive> for umijs base on react-activation
url: https://github.com/alitajs/umi-plugin-keep-alive
---

umi-plugin-keep-alive
=====================

中文说明 | English

此 `<KeepAlive>` 功能基于 react-activation

在线示例
----

umi 多 tabs 示例：https://codesandbox.io/s/umi-keep-alive-tabs-demo-knfxy

使用方法
----

1.  安装
    
    npm install umi-plugin-keep-alive --save
    # or
    yarn add umi-plugin-keep-alive
    
2.  从 `umi` 中导出 `KeepAlive`，包裹在需要被缓存的组件上
    
    import { useState } from 'react'
    import { KeepAlive } from 'umi'
    
    function Counter() {
      const \[count, setCount\] \= useState(0)
    
      return (
        <div\>
          <p\>count: {count}</p\>
          <button onClick\={() \=> setCount(count \=> count + 1)}\>add</button\>
        </div\>
      )
    }
    
    export default function() {
      const \[show, setShow\] \= useState(true)
    
      return (
        <div\>
          <h1\>Page index</h1\>
          {show && (
            <KeepAlive\>
              <Counter />
            </KeepAlive\>
          )}
          <button onClick\={() \=> setShow(show \=> !show)}\>toggle</button\>
        </div\>
      )
    }
    

文档
--

所有来自 react-activation 都可以由 `umi` 导出

import {
  KeepAlive,
  useActivate, 
  useUnactivate, 
  withActivation,
  withAliveScope, 
  useAliveController
} from 'umi'

访问 react-activation 查阅完整的文档

LICENSE
-------

MIT
