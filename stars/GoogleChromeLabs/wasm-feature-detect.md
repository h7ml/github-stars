---
project: wasm-feature-detect
stars: 617
description: A small library to detect which features of WebAssembly are supported.
url: https://github.com/GoogleChromeLabs/wasm-feature-detect
---

WebAssembly Feature Detection
=============================

A small library to detect which features of WebAssembly are supported.

-   ✅ Runs in browsers, Node and Deno
-   ✅ Tree-shakable (only bundle the detectors you use)
-   ✅ Provided as an ES6, CommonJS and UMD module.
-   ✅ CSP compatible
-   ✅ All detectors add up to only ~980B gzipped

Installation
------------

```
npm install -g wasm-feature-detect
```

Usage
-----

<script type\="module"\>
	import { simd } from "wasm-feature-detect";

	if (await simd()) {
		/\* SIMD support \*/
	} else {
		/\* No SIMD support \*/
	}
</script\>

### Hotlinking from Unpkg

<script type\="module"\>
	import { simd } from "https://unpkg.com/wasm-feature-detect?module";
	// ...
</script\>

If required, there’s also a UMD version

<script src\="https://unpkg.com/wasm-feature-detect/dist/umd/index.js"\></script\>
<script\>
	if (await wasmFeatureDetect.simd()) {
	  // ...
	}
</script\>

Detectors
---------

All detectors return a `Promise<bool>`.

Function

Proposal

`bigInt()`

BigInt integration

`bulkMemory()`

Bulk memory operations

`exceptions()`

Legacy Exception Handling

`exceptionsFinal()`

Exception Handling with exnref

`extendedConst()`

Extented Const Expressesions

`gc()`

Garbage Collection

`jsStringBuiltins()`

JS String Builtins Proposal for WebAssembly

`jspi()`

JavaScript Promise Integration

`memory64()`

Memory64

`multiMemory()`

Multiple Memories

`multiValue()`

Multi-value

`mutableGlobals()`

Importable/Exportable mutable globals

`referenceTypes()`

Reference Types

`relaxedSimd()`

Relaxed SIMD

`saturatedFloatToInt()`

Non-trapping float-to-int conversions

`signExtensions()`

Sign-extension operators

`simd()`

Fixed-Width SIMD

`streamingCompilation()`

Streaming Compilation

`tailCall()`

Tail call

`threads()`

Threads

`typeReflection()`

Type Reflection

`typedFunctionReferences()`

Typed function references

Why are all the tests async?
----------------------------

The _technical_ reason is that some tests might have to be augmented to be asynchronous in the future. For example, Firefox is planning to make a change that would require a `postMessage` call to detect SABs, which are required for threads.

The _other_ reason is that you _should_ be using `WebAssembly.compile`, `WebAssembly.instantiate`, or their streaming versions `WebAssembly.compileStreaming` and `WebAssembly.instantiateStreaming`, which are all asynchronous. You should already be prepared for asynchronous code when using WebAssembly!

Contributing
------------

If you want to contribute a new feature test, all you need to do is create a new folder in `src/detectors` and it will be automatically picked up. The folder may contain a `module.wat` file, which will be compiled using `wabt.js`.

;; Name: <Name of the feature for the README>
;; Proposal: <Link to the proposal’s explainer/repo>
;; Features: <Space-separated list of WasmFeatures from wabt.js>

(module
  ;; More WAT code here
)

The folder can also contain an optional `index.js` file, whose default export must be an async function. This function can do additional testing in JavaScript and must return a boolean. See the “threads” detector as an example. It must contain at least one of `module.wat` or `index.js`.

* * *

License Apache-2.0
