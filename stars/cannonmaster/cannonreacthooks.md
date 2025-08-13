---
project: cannonreacthooks
stars: 8
description: null
url: https://github.com/cannonmaster/cannonreacthooks
---

Cannon React Hooks
==================

#### The project is currently in active development, and we are actively working to improve and refine it further

Cannon React Hooks is a collection of useful custom hooks for React applications. It provides a set of reusable hooks that solve common problems and enhance the functionality of your React components.

Features
--------

-   **Easy to learn and use**
-   **Contains a comprehensive collection of basic Hooks**
-   **Contains a large number of advanced Hooks that are refined from business scenarios**
-   **Written in TypeScript with predictable static types**

Installation
------------

Install the package using npm:

npm install --save @cannonui/reacthooks

Online Docs
-----------

Visit Doc's website

Example Usage
-------------

Here's an example how you can use the hook from this library:

import { useState } from "react";
import { useDebounce } from "@cannonui/reacthooks";

const TestUseDebounce \= () \=> {
  const \[inputValue, setInputValue\] \= useState("");

  const debouncedValue \= useDebounce(inputValue, 1000);

  const handleChange \= (e: any) \=> {
    setInputValue(e.target.value);
  };

  return (
    <div\>
      <input type\="text" value\={inputValue} onChange\={handleChange} /\>
      <p\>Debounced value: {debouncedValue}</p\>
    </div\>
  );
};

export default TestUseDebounce;

Contributing
------------

Contributions are welcome! If you have any bug reports, feature requests, or suggestions, please open an issue or submit a pull request.

License
-------

This project is licensed under the MIT License.
