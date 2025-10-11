---
project: trzsz-ssh
stars: 2266
description: trzsz-ssh ( tssh ) is an ssh client designed as a drop-in replacement for the openssh client. It aims to provide complete compatibility with openssh, mirroring all its features, while also offering additional useful features. Such as login prompt, batch login, remember password, automated interaction, trzsz, zmodem(rz/sz), udp mode like mosh, etc.
url: https://github.com/trzsz/trzsz-ssh
---

trzsz-ssh ( tssh ) - an openssh client alternative
==================================================

trzsz-ssh ( tssh ) is an ssh client designed as a drop-in replacement for the openssh client. It aims to provide complete compatibility with openssh, mirroring all its features, while also offering additional useful features not found in the openssh client.

Basic Features
--------------

trzsz-ssh ( tssh ) works exactly like the openssh client. The following common features have been implemented:

Features

Support Options

Cipher

`-c` `Ciphers`

Pseudo TTY

`-t` `-T` `RequestTTY`

Network

`-4` `-6` `AddressFamily`

SSH Proxy

`-J` `-W` `ProxyJump` `ProxyCommand`

Multiplexing

`ControlMaster` `ControlPath` `ControlPersist`

Command

`RemoteCommand`, `LocalCommand`, `PermitLocalCommand`

SSH Agent

`-a` `-A` `ForwardAgent` `IdentityAgent` `SSH_AUTH_SOCK`

X11 Forward

`-x` `-X` `-Y` `ForwardX11` `ForwardX11Trusted` `ForwardX11Timeout`

Known Hosts

`UserKnownHostsFile` `GlobalKnownHostsFile` `StrictHostKeyChecking`

Basic Login

`-l` `-p` `-i` `-F` `HostName` `Port` `User` `IdentityFile` `SendEnv` `SetEnv`

Authentication

`PubkeyAuthentication` `PasswordAuthentication` `KbdInteractiveAuthentication`

Port Forward

`-g` `-f` `-N` `-L` `-R` `-D` `LocalForward` `RemoteForward` `DynamicForward` `GatewayPorts` `ClearAllForwardings`

Extra Features
--------------

trzsz-ssh ( tssh ) offers additional useful features:

English

中文

Login Prompt

登录界面

Custom Theme

主题风格

trzsz ( trz / tsz )

trzsz ( trz / tsz )

zmodem ( rz / sz )

zmodem ( rz / sz )

Batch Login

批量登录

Group Labels

分组标签

Automated Interaction

自动交互

Remember Password

记住密码

Custom Configuration

个性配置

Comments of Config

配置注释

Clipboard Integration

剪贴板集成

Other Features

其他功能

UDP Mode

UDP 模式

Installation
------------

-   Install with scoop / winget / choco on Windows
    
    `scoop install tssh` / `winget install tssh` / `choco install tssh`
    
    scoop install tssh
    
    winget install tssh
    
    choco install tssh
    
-   Install with homebrew on MacOS
    
    `brew install trzsz-ssh`
    
    brew update
    brew install trzsz-ssh
    
-   Install with apt on Ubuntu
    
    `sudo apt install tssh`
    
    sudo apt update && sudo apt install software-properties-common
    sudo add-apt-repository ppa:trzsz/ppa && sudo apt update
    
    sudo apt install tssh
    
-   Install with apt on Debian
    
    `sudo apt install tssh`
    
    sudo apt install curl gpg
    curl -s 'https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x7074ce75da7cc691c1ae1a7c7e51d1ad956055ca' \\
      | gpg --dearmor -o /usr/share/keyrings/trzsz.gpg
    echo 'deb \[signed-by=/usr/share/keyrings/trzsz.gpg\] https://ppa.launchpadcontent.net/trzsz/ppa/ubuntu jammy main' \\
      | sudo tee /etc/apt/sources.list.d/trzsz.list
    sudo apt update
    
    sudo apt install tssh
    
-   Install with yum on Linux
    
    `sudo yum install tssh`
    
    -   Install with gemfury repository.
        
        echo '\[trzsz\]
        name=Trzsz Repo
        baseurl=https://yum.fury.io/trzsz/
        enabled=1
        gpgcheck=0' | sudo tee /etc/yum.repos.d/trzsz.repo
        
        sudo yum install tssh
        
    -   Install with wlnmp repository. It's not necessary to configure the epel repository for tssh.
        
        curl -fsSL "https://sh.wlnmp.com/wlnmp.sh" | bash
        
        sudo yum install tssh
        
    
-   Install with yay on ArchLinux
    
    `yay -S tssh`
    
    yay -Syu
    yay -S tssh
    
-   Install with Go ( Requires go 1.21 or later )
    
    `go install github.com/trzsz/trzsz-ssh/cmd/tssh@latest`
    
    go install github.com/trzsz/trzsz-ssh/cmd/tssh@latest
    
    The binaries are usually located in ~/go/bin/ ( C:\\Users\\your\_name\\go\\bin\\ on Windows ).
    
-   Build from source ( Requires go 1.21 or later )
    
    `sudo make install`
    
    git clone --depth 1 https://github.com/trzsz/trzsz-ssh.git
    cd trzsz-ssh
    make
    sudo make install
    
-   Download from the GitHub Releases, unzip and add to `PATH` environment.
    

Development
-----------

The `github.com/trzsz/trzsz-ssh/tssh` can be used as a library, for example:

package main

import (
	"log"
	"os"

	"github.com/trzsz/trzsz-ssh/tssh"
)

func main() {
	// Example 1: execute command on remote server
	client, err := tssh.SshLogin(&tssh.SshArgs{Destination: "root@192.168.0.1"})
	if err != nil {
		log.Fatal(err)
	}
	defer client.Close()
	session, err := client.NewSession()
	if err != nil {
		log.Fatal(err)
	}
	defer session.Close()
	output, err := session.CombinedOutput("whoami")
	if err != nil {
		log.Fatal(err)
	}
	log.Printf("I'm %s", string(output))

	// Example 2: run the tssh program
	code := tssh.TsshMain(\[\]string{"-t", "root@192.168.0.1", "bash -l"})
	os.Exit(code)
}

Contributing
------------

Welcome and thank you for considering contributing. We appreciate all forms of support, from coding and testing to documentation and CI/CD improvements.

-   Fork and clone the repository `https://github.com/trzsz/trzsz-ssh.git`.
    
-   Make your changes just ensure that the unit tests `go test ./tssh` pass.
    
-   Build the binary `go build -o ./bin/ ./cmd/tssh` and test it `./bin/tssh`.
    
-   Once you are happy with your changes, please submit a pull request.
    

Screenshot
----------

Contact
-------

Feel free to email the author lonnywong@qq.com, or create an issue. Welcome to join the QQ group: 318578930.

Sponsor
-------

❤️ Sponsor trzsz ❤️, buy the author a drink 🍺 ? Thank you for your support!
