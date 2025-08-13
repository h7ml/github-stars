---
project: dlight
stars: 660
description: DX-first UI Rendering Library
url: https://github.com/dlight-js/dlight
---

dlight.dev
==========

DX-first UI rendering library.

-   🥳 **Delightful**
    -   With an API designed to be intuitive and user-friendly, web development becomes effortless with DLight, whether you're building a simple website or a complex web application.
-   🚀 **Performant**
    -   With a minuscule file size of just 5KB, DLight is lightning-fast and ultra-lightweight, delivering optimal performance without the need for manual optimization.
-   ✨ **DX-first**
    -   DLight uses the syntax of function calls and dot notation to make development more enjoyable, without the need to write outdated and hard-to-read XML code.
-   🪶 **Intuitively Simple**
    -   DLight is born reactive and is designed to be intuitively simple, with a minimalistic API that requires no memorization of complex functions or libraries.

Preview
=======

import { View } from "@dlightjs/dlight"

@View
class MyComp {
  night \= false
  fruits \= \["🍎", "🍊", "🥑"\]

  Body() {
    h1("hello, dlight js")

    for (const fruit of this.fruits) {
      div(fruit)
    }

    button("toggle")
      .class("toggle")
      .onClick(() \=> {
        this.night \= !this.night
      })

    if (this.night) {
      "🌙"
      "✨"
      "🌟"
    } else {
      "🔆"
    }
  }
}

Credits
=======

Thanks all existing frameworks for the inspiration and the great work they've done. DLight is standing on the shoulders of giants.

-   SwiftUI
-   React
-   Vue
-   Svelte
-   Solid
-   Angular
-   Preact
-   Qwik
-   Ember
-   Marko
-   VanJs
-   ef.js
-   Lit

Thanks js-framework-benchmark for the benchmarking tooling that pulls my hair out.

Thanks component party for the syntax level comparison between different frameworks.

Contributors
============

  
**Duan Yihan**  
🚇 ⚠️ 💻

  
**orange04**  
💻 🎨

  
**Guo-lab**  
🖋

  
**Gor**  
💻 🐛 💡

  
**Haibo Zheng**  
🐛 🖋

  
**Duane Johnson**  
💻 🤔 📖 🚧
