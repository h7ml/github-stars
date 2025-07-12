---
project: ferron
stars: 1340
description: A fast, memory-safe web server written in Rust.
url: https://github.com/ferronweb/ferron
---

**Ferron** - a fast, memory-safe web server written in Rust

* * *

Features
--------

-   **High performance** - built with Rust’s async capabilities for optimal speed.
-   **Memory-safe** - built with Rust, which is a programming language offering memory safety.
-   **Extensibility** - modular architecture for easy customization.
-   **Secure** - focus on robust security practices and safe concurrency.

Components
----------

Ferron consists of multiple components:

-   **`ferron`**: The main web server.
-   **`ferron-passwd`**: A tool for generating user entries with hashed passwords, which can be copied into the web server's configuration file.

Building Ferron from source
---------------------------

You can clone the repository and explore the existing code:

git clone https://github.com/ferronweb/ferron.git
cd ferron

You can then build and run the web server using Cargo:

cargo build -r
cargo run -r --bin ferron

You can also use Ferron Forge to build the web server. Ferron Forge outputs a ZIP archive that can be used by the Ferron installer.

Server configuration
--------------------

You can check the Ferron documentation to see configuration properties used by Ferron.

Contributing
------------

See Ferron contribution page for details.

License
-------

Ferron is licensed under the MIT License. See `LICENSE` for details.
