---
project: react-color
stars: 12210
description: :art: Color Pickers from Sketch, Photoshop, Chrome, Github, Twitter & more
url: https://github.com/casesandberg/react-color
---

React Color
===========

-   **13 Different Pickers** - Sketch, Photoshop, Chrome and many more
    
-   **Make Your Own** - Use the building block components to make your own
    

Demo
----

**Live Demo**

Installation & Usage
--------------------

npm install react-color --save

### Include the Component

import React from 'react'
import { SketchPicker } from 'react-color'

class Component extends React.Component {

  render() {
    return <SketchPicker />
  }
}

You can import `AlphaPicker` `BlockPicker` `ChromePicker` `CirclePicker` `CompactPicker` `GithubPicker` `HuePicker` `MaterialPicker` `PhotoshopPicker` `SketchPicker` `SliderPicker` `SwatchesPicker` `TwitterPicker` respectively.

> 100% inline styles via ReactCSS
