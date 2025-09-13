---
project: react-use-chinese
stars: 1042
description: 中文文档@react-use
url: https://github.com/zenghongtu/react-use-chinese
---

  
  
👍  
react-use  
  
  
  

================================

  
  
  
必不可少的 React Hooks集合. _移植_ `libreact`.  
原仓库: react-use 版本: v8.1.3  
  
  
  

npm i react-use

  
  
  
  
  

-   **传感器**
    -   `useBattery` — 跟踪设备电池状态。
    -   `useGeolocation` — 跟踪用户设备的地理位置状态。
    -   `useHover` and `useHoverDirty` — 跟踪鼠标悬停某个元素的状态。
    -   `useIdle` — 跟踪用户是否处于非活动状态。
    -   `useKey`, `useKeyPress`, `useKeyboardJs`, 和 `useKeyPressEvent` — 追踪按键。
    -   `useLocation` — 跟踪页面导航栏的位置状态。
    -   `useMedia` — 跟踪CSS媒体查询的状态。
    -   `useMediaDevices` — 跟踪连接的硬件设备的状态。
    -   `useMotion` — 跟踪设备的运动传感器的状态。
    -   `useMouse` and `useMouseHovered` — 跟踪鼠标位置的状态。
    -   `useNetwork` — 跟踪用户的互联网连接状态。
    -   `useOrientation` — 跟踪设备屏幕方向的状态。
    -   `usePageLeave` — 当鼠标离开页面边界时触发。
    -   `useScroll` — 跟踪HTML元素的滚动位置。
    -   `useSize` — 跟踪HTML元素的维度。
    -   `useStartTyping` — 检测用户何时开始输入。
    -   `useWindowScroll` — 跟踪 `窗口` 滚动位置。
    -   `useWindowSize` — 跟踪 `窗口` 尺寸。  
          
        
-   **用户界面**
    -   `useAudio` — 播放音频并公开其控件。
    -   `useClickAway` — 当用户点击目标区域外时触发回调。
    -   `useCss` — 动态调整CSS。
    -   `useDrop` and `useDropArea` — 跟踪文件，链接和复制粘贴。
    -   `useFullscreen` — 全屏显示元素或视频。
    -   `useSpeech` — 从文本字符串合成语音。
    -   `useVideo` — 播放视频，跟踪其状态，以及公开播放控件。
    -   `useWait` — UI的复杂等待管理。  
          
        
-   **动画效果**
    -   `useRaf` — 在每个 `requestAnimationFrame` 上重新呈现组件。
    -   `useSpring` — 根据弹簧动力学随时间插入数字。
    -   `useTimeout` — 超时后返回true。
    -   `useTween` — 重新渲染组件，同时补间0到1之间的数字。
    -   `useUpdate` — 返回一个回调，在调用时重新呈现组件。  
          
        
-   **副作用**
    -   `useAsync` — 解析一个 `async` 函数。
    -   `useAsyncFn` — 异步函数的状态管理。
    -   `useAsyncRetry` — `useAsync` 带有 `retry()`方法。
    -   `useBeforeUnload` — 当用户尝试重新加载或关闭页面时显示浏览器警报。
    -   `useCopyToClipboard` — 将文本复制到剪贴板。
    -   `useDebounce` — 防抖函数。
    -   `useFavicon` — 设置页面的favicon。
    -   `useLocalStorage` — 管理`localStorage`中的值。
    -   `useLockBodyScroll` — 锁定body元素的滚动。
    -   `useSessionStorage` — 管理`sessionStorage`中的值。
    -   `useThrottle` and `useThrottleFn` — 节流一个函数。
    -   `useTitle` — 设置页面标题。  
          
        
-   **生命周期**
    -   `useEffectOnce` — 仅运行一次的修改后的`useEffect`。
    -   `useEvent` — 订阅事件。
    -   `useLifecycles` — 调用`mount`和`unmount`回调。
    -   `useRefMounted` — 跟踪组件是否已挂载。
    -   `usePromise` — 仅在安装组件时解析promise。
    -   `useLogger` — 在组件经历生命周期时登录控制台。
    -   `useMount` — 调用`mount`回调。
    -   `useUnmount` — 调用`unmount`回调。
    -   `useUpdateEffect` — 仅在更新时运行一个`effect`。
    -   `useDeepCompareEffect` — 运行一个`effect`通过深度比较其依赖项。  
          
        
-   **状态**
    -   `createMemo` — memoized hooks的工厂钩子。
    -   `useGetSet` — 返回状态 getter `get()` 而不是原始状态。
    -   `useGetSetState` — 就像 `useGetSet` 和 `useSetState` 有个孩子。
    -   `useObservable` — 跟踪`Observable`的最新值。
    -   `useSetState` — 创建类似`this.setState`的`setState`方法。
    -   `useToggle` and `useBoolean` — 跟踪布尔值的状态。
    -   `useCounter` and `useNumber` — 跟踪数字的状态。
    -   `useList` — 跟踪数组的状态。
    -   `useMap` — 跟踪对象的状态。

Usage
-----

你需要安装React `16.8.0`或更高版本才能使用Hooks API。你可以分别导入每个钩子

import useToggle from 'react-use/lib/useToggle'

或使用 ES6 命名导入

import {useToggle} from 'react-use'

根据绑定器的不同，你可能会在ES6命名导入语句中遇到缺少依赖项的错误。有些钩子要求安装对等依赖项，因此我们建议单独导入。如果你希望同时使用这两种方法，你可以通过将以下配置添加到`.babelrc`文件中，将命名的导入语句转换为使用`babel-plugin-import`的单个导入语句。

\[
  "import", {
    "libraryName": "react-use",
    "libraryDirectory": "lib",
    "camel2DashComponentName": false
  }
\]

许可证
---

Unlicense — 公有领域
