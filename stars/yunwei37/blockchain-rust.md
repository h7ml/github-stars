---
project: blockchain-rust
stars: 163
description: blockchain_go in rust: A simplified blockchain implementation in rust for leaning / 用 rust 从零开始构建区块链(Bitcoin)
url: https://github.com/yunwei37/blockchain-rust
---

blockchain-rust - 用 rust 从零开始构建区块链(Bitcoin)系列
=============================================

reimplement `blockchain_go` in rust, and not only blockchain\_go;

a simple blockchain demo for learning

the code for each article
-------------------------

1.  part1: Basic Prototype `基本原型` commit bd0efe7
2.  part2: Proof-of-Work `工作量证明` commit 9d9370a
3.  part3: Persistence and CLI `持久化、命令行、日志` commit e2094c0
4.  part4: Transactions 1 `交易（1）` commit bdbdcec
5.  part5: Addresses `地址和签名` commit 440cba2
6.  part6: Transactions 2 `交易（2）` commit 4912743
7.  part7: Network `网络和分布式一致性算法` master

Chinese Documents
-----------------

-   基本原型和工作量证明算法: part1.md

usage
-----

-   Create wallet:
    
    cargo run createwallet
    
-   Create blockchain:
    
    ```
    cargo run createblockchain <address>
    ```
    
-   send coins (if `-m` is specified, the block will be mined immediately in the same node):
    
    ```
    cargo run send <from> <to> <amount> -m 
    ```
    
-   start server:
    
    ```
    cargo run startnode <port>
    ```
    
    or start miner node:
    
    ```
    cargo run startminer <port> <address>
    ```
    
-   get balance:
    
    ```
    cargo run getbalance <address>
    ```
    

You can use the `RUST_LOG=info` to print the log.

reference
---------

-   `blockchain_go` code: https://github.com/Jeiwan/blockchain\_go
-   Build a cryptocurrency! - Blockchain in Rust: https://github.com/GeekLaunch/blockchain-rust
-   中文版文档：https://liuchengxu.gitbook.io/blockchain/
