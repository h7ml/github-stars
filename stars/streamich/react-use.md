---
project: react-use
stars: 43584
description: React Hooks — 👍
url: https://github.com/streamich/react-use
---

  
  
👍  
react-use  
  
  
  

================================

  
  
  
Collection of essential React Hooks. _Port of_ `libreact`.  
Translations: 🇨🇳 汉语  
  
  
  

npm i react-use

  
  
  
  
  

-   **Sensors**
    -   `useBattery` — tracks device battery state.
    -   `useGeolocation` — tracks geo location state of user's device.
    -   `useHover` and `useHoverDirty` — tracks mouse hover state of some element.
    -   `useHash` — tracks location hash value.
    -   `useIdle` — tracks whether user is being inactive.
    -   `useIntersection` — tracks an HTML element's intersection.
    -   `useKey`, `useKeyPress`, `useKeyboardJs`, and `useKeyPressEvent` — track keys.
    -   `useLocation` and `useSearchParam` — tracks page navigation bar location state.
    -   `useLongPress` — tracks long press gesture of some element.
    -   `useMedia` — tracks state of a CSS media query.
    -   `useMediaDevices` — tracks state of connected hardware devices.
    -   `useMotion` — tracks state of device's motion sensor.
    -   `useMouse` and `useMouseHovered` — tracks state of mouse position.
    -   `useMouseWheel` — tracks deltaY of scrolled mouse wheel.
    -   `useNetworkState` — tracks the state of browser's network connection.
    -   `useOrientation` — tracks state of device's screen orientation.
    -   `usePageLeave` — triggers when mouse leaves page boundaries.
    -   `useScratch` — tracks mouse click-and-scrub state.
    -   `useScroll` — tracks an HTML element's scroll position.
    -   `useScrolling` — tracks whether HTML element is scrolling.
    -   `useStartTyping` — detects when user starts typing.
    -   `useWindowScroll` — tracks `Window` scroll position.
    -   `useWindowSize` — tracks `Window` dimensions.
    -   `useMeasure` and `useSize` — tracks an HTML element's dimensions.
    -   `createBreakpoint` — tracks `innerWidth`
    -   `useScrollbarWidth` — detects browser's native scrollbars width.
    -   `usePinchZoom` — tracks pointer events to detect pinch zoom in and out status.  
          
        
-   **UI**
    -   `useAudio` — plays audio and exposes its controls.
    -   `useClickAway` — triggers callback when user clicks outside target area.
    -   `useCss` — dynamically adjusts CSS.
    -   `useDrop` and `useDropArea` — tracks file, link and copy-paste drops.
    -   `useFullscreen` — display an element or video full-screen.
    -   `useSlider` — provides slide behavior over any HTML element.
    -   `useSpeech` — synthesizes speech from a text string.
    -   `useVibrate` — provide physical feedback using the Vibration API.
    -   `useVideo` — plays video, tracks its state, and exposes playback controls.  
          
        
-   **Animations**
    -   `useRaf` — re-renders component on each `requestAnimationFrame`.
    -   `useInterval` and `useHarmonicIntervalFn` — re-renders component on a set interval using `setInterval`.
    -   `useSpring` — interpolates number over time according to spring dynamics.
    -   `useTimeout` — re-renders component after a timeout.
    -   `useTimeoutFn` — calls given function after a timeout.
    -   `useTween` — re-renders component, while tweening a number from 0 to 1.
    -   `useUpdate` — returns a callback, which re-renders component when called.  
          
        
-   **Side-effects**
    -   `useAsync`, `useAsyncFn`, and `useAsyncRetry` — resolves an `async` function.
    -   `useBeforeUnload` — shows browser alert when user try to reload or close the page.
    -   `useCookie` — provides way to read, update and delete a cookie.
    -   `useCopyToClipboard` — copies text to clipboard.
    -   `useDebounce` — debounces a function.
    -   `useError` — error dispatcher.
    -   `useFavicon` — sets favicon of the page.
    -   `useLocalStorage` — manages a value in `localStorage`.
    -   `useLockBodyScroll` — lock scrolling of the body element.
    -   `useRafLoop` — calls given function inside the RAF loop.
    -   `useSessionStorage` — manages a value in `sessionStorage`.
    -   `useThrottle` and `useThrottleFn` — throttles a function.
    -   `useTitle` — sets title of the page.
    -   `usePermission` — query permission status for browser APIs.  
          
        
-   **Lifecycles**
    -   `useEffectOnce` — a modified `useEffect` hook that only runs once.
    -   `useEvent` — subscribe to events.
    -   `useLifecycles` — calls `mount` and `unmount` callbacks.
    -   `useMountedState` and `useUnmountPromise` — track if component is mounted.
    -   `usePromise` — resolves promise only while component is mounted.
    -   `useLogger` — logs in console as component goes through life-cycles.
    -   `useMount` — calls `mount` callbacks.
    -   `useUnmount` — calls `unmount` callbacks.
    -   `useUpdateEffect` — run an `effect` only on updates.
    -   `useIsomorphicLayoutEffect` — `useLayoutEffect` that that works on server.
    -   `useDeepCompareEffect`, `useShallowCompareEffect`, and `useCustomCompareEffect`  
          
        
-   **State**
    -   `createMemo` — factory of memoized hooks.
    -   `createReducer` — factory of reducer hooks with custom middleware.
    -   `createReducerContext` and `createStateContext` — factory of hooks for a sharing state between components.
    -   `useDefault` — returns the default value when state is `null` or `undefined`.
    -   `useGetSet` — returns state getter `get()` instead of raw state.
    -   `useGetSetState` — as if `useGetSet` and `useSetState` had a baby.
    -   `useLatest` — returns the latest state or props
    -   `usePrevious` — returns the previous state or props.
    -   `usePreviousDistinct` — like `usePrevious` but with a predicate to determine if `previous` should update.
    -   `useObservable` — tracks latest value of an `Observable`.
    -   `useRafState` — creates `setState` method which only updates after `requestAnimationFrame`.
    -   `useSetState` — creates `setState` method which works like `this.setState`.
    -   `useStateList` — circularly iterates over an array.
    -   `useToggle` and `useBoolean` — tracks state of a boolean.
    -   `useCounter` and `useNumber` — tracks state of a number.
    -   `useList` and `useUpsert` — tracks state of an array.
    -   `useMap` — tracks state of an object.
    -   `useSet` — tracks state of a Set.
    -   `useQueue` — implements simple queue.
    -   `useStateValidator` — tracks state of an object.
    -   `useStateWithHistory` — stores previous state values and provides handles to travel through them.
    -   `useMultiStateValidator` — alike the `useStateValidator`, but tracks multiple states at a time.
    -   `useMediatedState` — like the regular `useState` but with mediation by custom function.
    -   `useFirstMountState` — check if current render is first.
    -   `useRendersCount` — count component renders.
    -   `createGlobalState` — cross component shared state.
    -   `useMethods` — neat alternative to `useReducer`.  
          
        
-   **Miscellaneous**
    -   `useEnsuredForwardedRef` and `ensuredForwardRef` — use a React.forwardedRef safely.

  
  
  
  
  
  
  

**Usage** — how to import.  
**Unlicense** — public domain.  
**Support** — add yourself to backer list below.

  
  
  
  
  

Contributors
============
