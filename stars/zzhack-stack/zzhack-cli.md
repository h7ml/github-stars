---
project: zzhack-cli
stars: 24
description: 💻 zzhack-cli is a Command Tool to help you quickly generate a WASM WebApp with simple configuration and zero code
url: https://github.com/zzhack-stack/zzhack-cli
---

English | 中文文档

`zzhack-cli` is a Command Tool that can help you quickly generate a WASM WebApp with simple configuration and zero code. It's worth mention that UI template is from zzhack, you can navigate to Live Demo for real experience.

Quick start
-----------

zzhack was written by Rust, thus you need to prepare the development environment for Rust for get some CLI which we need, such as `trunk`, `zzhack` etc. You can visit Rust Book or rust-lang.org for more detail about Rust installation.

After you have the Rust development environment, you'll also need some Command Tools to help you building. Copy the following commands in your terminal to install them.

rustup target add wasm32-unknown-unknown
cargo install trunk zzhack

Now, let's launch your first WASM WebApp!

# Create project workspace
mkdir my-first-wasm-project

cd my-first-wasm-project

zzhack init
zzhack serve

Docs
----

You can use the zzhack default config by `zzhack init` for more detail of docs.

License
-------

MIT.
