---
project: glicol
stars: 2774
description: Graph-oriented live coding language and music/audio DSP library written in Rust
url: https://github.com/chaosprint/glicol
---

  

Glicol (an acronym for "graph-oriented live coding language") is a computer music language with both its language and audio engine written in Rust programming language, a modern alternative to C/C++. Given this low-level nature, Glicol can run on many different platforms such as browsers, VST plugins and Bela board. Glicol's synth-like syntax and powerful audio engine also make it possible to combine high-level synth or sequencer control with low-level sample-accurate audio synthesis, all in real-time.

Get started
-----------

### 🚀 The Web App

The easiest way to try Glicol:

https://glicol.org

> There you can find guides, demos, docs, and apps for collaboration.

Features

-   Near-native, garbage-collection-free and memory-safe real-time audio in web browsers
    
-   Quick reference in consoles with `alt-d`
    
-   The web app automatically loads samples; you can also drag and drop local samples in the browser editor
    
-   Robust error handling: error reported in console, but previous music will continue!
    
-   Mix JavaScript code to create visuals with Hydra synth made by @ojack
    
-   What you see is what you get, i.e. declarative programmering for both code writing and executing: no need to select anything, just change the code and update, Glicol engine will use `LCS` algorithm to handle adding, updating and removing
    
-   Decentralised collaboration using `yjs` and a unique `be-ready` mechanism
    

### 🎁 For Audio Dev

Description

NPM Docs

Safe, performant, light-weight and ergonomic audio lib for web apps

Rust Audio Lib

Write VST like this Dattorro reverb plugin

Run on Bela

Run Glicol DSL on Bela board for quick audio prototyping.

### 🍿 YouTube Channel

Find Glicol demo videos in this playlist.

Philosophy of Glicol
--------------------

The motivation of Glicol is:

-   to help people with zero knowledge of coding and music production to get started with live coding
    
-   to offer experienced music coders a tool for quick prototyping and hacking
    

In NIME community, it is known as:

> low entry fee and high ceilings

This is Glicol's philosophy to approach these goals:

-   design the language from a new instrument design perspective
    
-   embrace the spirit of the internet for a better experience
    

Reflected in the implementation:

-   Glicol adopts a graph-oriented paradigm
    
-   Glicol can be used in browsers with zero-installation
    

### Graph-oriented

The basic idea of Glicol is to connect different nodes like synth modules.

All you need to know is the audio input/output behaviour of each node.

Two ways for connecting: `>>` and `~reference`:

```
// amplitude modulation and lazy evaluation example
// chain with ~ is a ref chain and will not be sent to the DAC

o: sin 440 >> mul ~amp
~amp: sin 1.0 >> mul 0.3 >> add 0.5
```

It also applies to sequencer and sampler:

```
// sequencer pattern
// first divide one bar with space
// then further divide each part based on midi number and rest(_)

o: speed 2.0 >> seq 60 _~a _ 48__67
>> sp \blip

// quantity alters probability
~a: choose 60 60 0 0 72 72
```

As mentioned above, you can try these examples on:

https://glicol.org

If you want, you can even hear how a `seq` node work:

```
o: speed 2.0 >> seq 60 _72 _ 48__67 >> mul 0.5
```

This is actually analogous to how hardware module pass signals.

It is very easy to remember and to get started.

When Glicol is used in education, we can let students see and hear each node, even including 'envelope'.

Just leave the introduction of data types, `Object` or `Function` later when we mix JavaScript with Glicol.

### Zero-installation

For the audio engine, instead of mapping it to existing audio lib like `SuperCollider`, I decide to do it the hard way:

-   write the parser in Rust
    
-   write the audio engine in Rust that works seamlessly with the AST processing
    
-   port it to browsers using `WebAssembly`, `AudioWorklet` and `SharedArrayBuffer`
    

The main reason is to explore performant audio in browsers for easy access and live coding collaboration.

The reward is that we now have an Rust audio lib called `glicol_synth`:

It can run on Web, Desktop, DAW, Bela board, etc.

And one more thing.

To write everything from low-level also opens the door for `meta` node.

Now I can explain to students, the `hello world` tone can also be written in this way:

```
o: meta `
    output.pad(128, 0.0);
    for i in 0..128 {
        output[i] = sin(2*PI()*phase) ;
        phase += 440.0 / sr;
    };
    while phase > 1.0 { phase -= 1.0 };
    output
`
```

Roadmap
-------

-   `0.1.0` hello world from `dasp_graph` and `pest.rs`, pass code from js to wasm, and lazy evaluation
-   `0.2.0` pass samples from js to wasm, support error handling, bpm control in console
-   `0.3.0` build complex node `plate` reverb using basic node from glicol, using macro in Rust
-   `0.4.0` use `LCS` algorithm and preprocessor for smooth and efficient whole graph updating
-   `0.5.0` build `const_generics` to `dasp_graph` and use it in glicol, use `SharedArrayBuffer`, support local sample loading
-   `0.6.0` refactor the code to modules:
    -   `glicol-main` = `glicol-synth` + `glicol-parser` + `glicol-ext`
    -   `glicol-ext` = `glicol-synth` + `glicol-parser` + `glicol-macro`
    -   `glicol-js` = `glicol-main` + `glicol-wasm`
-   `0.7.0` support mixing js with glicol in `glicol-js` using Regex; add visualisation
-   `0.8.0` embed `Rhai` in glicol 🎉
-   `0.9.0` redesigned architecture; see the release note
-   `0.10.0` run as a VST plugin
-   `0.11.0` run on Bela
-   `0.12.0` distribute as a `npm` package
-   better music expressions, more variation for `seq` nodes
-   exploring new forms of musical interactions

> Note that Glicol is still highly experimental, so it can be risky for live performances. The API may also change before version 1.0.0.

Please let me know in issues or discussions:

-   your thoughts on the experience of glicol
-   new feature suggestion
-   bug report, especially the code that causes a `panic` in browser console
-   missing and confusion in guides and reference on the website
