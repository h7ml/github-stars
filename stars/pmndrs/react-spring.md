---
project: react-spring
stars: 28858
description: ✌️ A spring physics based React animation library
url: https://github.com/pmndrs/react-spring
---

  

react-spring
============

### A spring-physics first animation library  
giving you flexible tools to confidently cast your ideas

  

  

`react-spring` is a cross-platform spring-physics first animation library.

It's as simple as:

const styles \= useSpring({
  from: {
    opacity: 0
  },
  to: {
    opacity: 1
  }
})

<animated.div style\={styles} /\>

Just a small bit about us:

-   **Cross-Platform**: We support `react-dom`, `react-native`, `react-three-fiber`, `react-konva` & `react-zdog`.
-   **Versatile**: Be declarative with your animations or if you prefer, imperative.
-   **Spring-Physics First**: By default animation use springs for fluid interactivity, but we support durations with easings as well.

There's a lot more to be had! Give it a try and find out.

Getting Started
---------------

### ⚡️ Jump Start

# Install the entire library
npm install react-spring
# or just install your specific target (recommended)
npm install @react-spring/web

import { animated, useSpring } from '@react-spring/web'

const FadeIn \= ({ isVisible, children }) \=> {
  const styles \= useSpring({
    opacity: isVisible ? 1 : 0,
    y: isVisible ? 0 : 24,
  })

  return <animated.div style\={styles}\>{children}</animated.div\>
}

It's as simple as that to create scroll-in animations when value of `isVisible` is toggled.

### 📖 Documentation and Examples

More documentation on the project can be found here.

Pages contain their own examples which you can check out there, or open in codesandbox for a more in-depth view!

* * *

📣 What others say
------------------

Used by
-------

And many others...

Backers
-------

Thank you to all our backers! 🙏 If you want to join them here, then consider contributing to our Opencollective.

Contributors
------------

This project exists thanks to all the people who contribute.
