---
project: gg
stars: 1793
description: 一个支持节点与订阅链接的 Linux 命令行代理工具 | A command-line tool for one-click proxy in your research and development without installing v2ray or anything else (only for linux)
url: https://github.com/mzz2017/gg
---

gg (go-graft)
=============

README | 中文文档

What is gg?
-----------

gg is a command-line tool for one-click proxy in your research and development.

You can just add `gg` before another command to redirect its traffic to your proxy without installing v2ray or anything else. Usage example: `gg python -m pip install torch`.

It was inspired by graftcp, is a pure golang implementation with more useful features.

**Why did I create go-graft?**

I am so tired of the poor network condition in my research and development. But I do not want to install v2ray in the working servers because it is too heavy.

Thus, I need a light and portable command-line tool to help me download and install dependencies and software on various servers.

**Advantages**

Compared to proxychains or graftcp, we have the following advantages:

1.  Use it independently without any other proxy utils.
2.  UDP support.
3.  Support golang programs. See applications built by Go can not be hook by proxychains-ng .

Installation
------------

1.  Run this command to download the latest release of go-graft:
    
    sudo sh -c "$(curl -L https://github.com/mzz2017/gg/raw/main/release/go.sh)"
    
    > Without `sudo`, gg will be installed to the user directory.
    > 
    > If the command gg `fails` after installation, check your `$PATH`.
    > 
    > You can also create a symbolic link to /usr/bin or any other directory in your path.
    > 
    > For example:
    > 
    > sudo ln -s /usr/local/bin/gg /usr/bin/gg
    
2.  Test the installation.
    
    $ gg --version
    gg version 0.1.1
    

Usage
-----

**Examples:**

Configure the subscription:

gg config -w subscription='https://example.com/path/to/sub'

Test with cloning linux repo:

gg git clone --depth=1 https://github.com/torvalds/linux.git

Output:

> ```
> Cloning into 'linux'...
> ...
> Receiving objects: 100% (78822/78822), 212.19 MiB | 7.04 MiB/s, done.
> Resolving deltas: 100% (7155/7155), done.
> ```

Or just redirect the traffic of whole shell session to your proxy:

gg bash

git clone --depth=1 https://github.com/torvalds/linux.git
curl ipv4.appspot.com

### Temporarily use

**Use share-link**

# if no configuration was written before, a share-link will be required to input.
gg wget -O frp.tar.gz https://github.com/fatedier/frp/releases/download/v0.38.0/frp\_0.38.0\_linux\_amd64.tar.gz

> ```
> Enter the share-link of your proxy: ********
> ...
> Saving to: ‘frp.tar.gz’
> frp.tar.gz 100%[=====================================================>] 8.44M 12.2MB/s in 0.7s    
> 2021-12-06 09:21:08 (12.2 MB/s) - ‘frp.tar.gz’ saved [8848900/8848900]
> ```

Or use `--node`:

gg --node ss://YWVzLTEyOC1nY206MQ@example.com:17247 speedtest

> ```
> Retrieving speedtest.net configuration...
> Testing from Microsoft (13.xx.xx.xx)...
> ...
> Hosted by xxx: 55.518 ms
> Testing download speed................................................................................
> Download: 104.83 Mbit/s
> Testing upload speed......................................................................................................
> Upload: 96.35 Mbit/s
> ```

**Use subscription**

By default, gg will automatically select the first available node from the subscription:

gg --subscription https://example.com/path/to/sub docker pull caddy

> ```
> Using default tag: latest
> latest: Pulling from library/caddy
> 97518928ae5f: Pull complete
> 23ccae726125: Pull complete
> 3de6a61c89ac: Pull complete
> 39ed957bdc00: Pull complete
> 0ae44c2d42dd: Pull complete
> Digest: sha256:46f11f4601ecb4c5a37d6014ad51f5cbfeb92b70f5c9ec6c2ac39c4c1a325588
> Status: Downloaded newer image for caddy:latest
> docker.io/library/caddy:latest
> ```

Select the node manually:

gg --subscription https://example.com/path/to/sub --select curl ipv4.appspot.com

> ```
> WARN[0000] Test nodes...
> Use the arrow keys to navigate: ↓ ↑ → ←  and / toggles search
> Select Node
>   🛪 [200Mbps] LoadBalance (323 ms)
>     [200Mbps] LoadBalance Trojan (448 ms)
>     [30M] CN2-US Cera (560 ms)
>     [1Gbps] 4837-US (781 ms)
>     [10Gbps] CN2-DE (811 ms)
>     [300Mbps] Macau (1023 ms)
>     [300Mbps] IPv6 LoadBalance (-1 ms)
> ↓   [1Gbps] RackNerd (-1 ms)
> 
> --------- Detail ----------
> Name:               [200Mbps] LoadBalance
> Protocol:           shadowsocks
> Support UDP:        true
> Latency:            323 ms
> 
> ```

### Long-term use

Write a config variable with `-w`:

Set subscription:

gg config -w subscription=https://example.com/path/to/sub
gg curl ipv4.appspot.com

> ```
> 13.141.150.163
> ```

Set node:

gg config -w node=vmess://MY\_VMESS\_SERVER\_SHARE\_LINK
gg curl ipv4.appspot.com

> ```
> 53.141.112.10
> ```

List config variables:

gg config

> ```
> node=
> subscription.link=https://example.com/path/to/sub
> subscription.select=first
> subscription.cache_last_node=true
> cache.subscription.last_node=trojan-go://MY_TROJAN_GO_SERVER_SHARE_LINK
> no_udp=false
> test_node_before_use=true
> ```

Unset or reset specific config variable:

gg config -u node

> ```
> node=
> ```

Read specific config variable:

gg config node

> ```
> vmess://MY_VMESS_SERVER_SHARE_LINK
> ```

Q&A
---

1.  Q: When I use `sudo gg xxx`, it remains to ask me for share-link even though config has been set. How to solve it?
    
    A: Use `sudo -E gg xxx` to solve it.
    
2.  Q: Can I use it on my IPv6-only machine?
    
    A: Of course, as long as your proxy server has an IPv6 entry.
    
3.  Q: When I use `gg sudo xxx`, I get `sudo: effective uid is not 0, ...`, how can I fix it?
    
    A: You should run `sudo gg xxx` instead, because `setuid` and `ptrace` can not work together. See stackoverflow.
    
4.  Q: When I use `oh-my-zsh`, it reports `git: 'gui' is not a git command. See 'git --help'.`, ho can I fix it?
    
    A: It is a problem of `oh-my-zsh`, it added an alias from gg to `git gui`. Append following content to `~/.zshrc`:
    
    unalias gg
    

Shell autocompletion
--------------------

If you want to complete other commands while using gg, please follow the method below:

### bash

Add this line to `~/.bashrc`:

complete -F \_command gg

### zsh

Add this line to `~/.zshrc`:

compdef \_precommand gg

If you get an error like `complete:13: command not found: compdef`, add following content in the beginning of the `.zshrc` file.

autoload -Uz compinit
compinit

### fish

Write following content in `~/.config/fish/completions/gg.fish`:

# fish completion for gg

function \_\_fish\_gg\_print\_remaining\_args
    set -l tokens (commandline -opc) (commandline -ct)
    set -e tokens\[1\]
    if test -n "$argv"
        and not string match -qr '^-' $argv\[1\]
        string join0 -- $argv
        return 0
    else
        return 1
    end
end

function \_\_fish\_complete\_gg\_subcommand
    set -l args (\_\_fish\_gg\_print\_remaining\_args | string split0)
    \_\_fish\_complete\_subcommand --commandline $args
end

# Complete the command we are executed under gg
complete -c gg -x -a "(\_\_fish\_complete\_gg\_subcommand)"

Support List
------------

### OS/Arch

-   Linux/amd64
-   Linux/arm
-   Linux/arm64
-   Linux/386

### Protocol

-   HTTP(S)
-   Socks
    -   Socks4
    -   Socks4a
    -   Socks5
-   VMess(AEAD, alterID=0) / VLESS
    -   TCP
    -   WS
    -   TLS
    -   GRPC
-   Shadowsocks
    -   AEAD Ciphers
    -   simple-obfs (not tested)
    -   Stream Ciphers
    -   v2ray-plugin
-   ShadowsocksR
-   Trojan
    -   Trojan-gfw
    -   Trojan-go

### Subscription

-   Base64 (v2rayN, etc.)
-   Clash
-   SIP008
-   Surge
-   Quantumult
-   Quantumult X
