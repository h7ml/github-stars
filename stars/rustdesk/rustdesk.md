---
project: rustdesk
stars: 92059
description: An open-source remote desktop application designed for self-hosting, as an alternative to TeamViewer.
url: https://github.com/rustdesk/rustdesk
---

  
Build • Docker • Structure • Snapshot  
\[Українська\] | \[česky\] | \[中文\] | \[Magyar\] | \[Español\] | \[فارسی\] | \[Français\] | \[Deutsch\] | \[Polski\] | \[Indonesian\] | \[Suomi\] | \[മലയാളം\] | \[日本語\] | \[Nederlands\] | \[Italiano\] | \[Русский\] | \[Português (Brasil)\] | \[Esperanto\] | \[한국어\] | \[العربي\] | \[Tiếng Việt\] | \[Dansk\] | \[Ελληνικά\] | \[Türkçe\] | \[Norsk\]  
**We need your help to translate this README, RustDesk UI and RustDesk Doc to your native language**

Caution

**Misuse Disclaimer:**  
The developers of RustDesk do not condone or support any unethical or illegal use of this software. Misuse, such as unauthorized access, control or invasion of privacy, is strictly against our guidelines. The authors are not responsible for any misuse of the application.

Chat with us: Discord | Twitter | Reddit | YouTube

Yet another remote desktop solution, written in Rust. Works out of the box with no configuration required. You have full control of your data, with no concerns about security. You can use our rendezvous/relay server, set up your own, or write your own rendezvous/relay server.

RustDesk welcomes contribution from everyone. See CONTRIBUTING.md for help getting started.

**FAQ**

**BINARY DOWNLOAD**

**NIGHTLY BUILD**

Dependencies
------------

Desktop versions use Flutter or Sciter (deprecated) for GUI, this tutorial is for Sciter only, since it is easier and more friendly to start. Check out our CI for building Flutter version.

Please download Sciter dynamic library yourself.

Windows | Linux | macOS

Raw Steps to build
------------------

-   Prepare your Rust development env and C++ build env
    
-   Install vcpkg, and set `VCPKG_ROOT` env variable correctly
    
    -   Windows: vcpkg install libvpx:x64-windows-static libyuv:x64-windows-static opus:x64-windows-static aom:x64-windows-static
    -   Linux/macOS: vcpkg install libvpx libyuv opus aom
-   run `cargo run`
    

Build
-----

How to Build on Linux
---------------------

### Ubuntu 18 (Debian 10)

sudo apt install -y zip g++ gcc git curl wget nasm yasm libgtk-3-dev clang libxcb-randr0-dev libxdo-dev \\
        libxfixes-dev libxcb-shape0-dev libxcb-xfixes0-dev libasound2-dev libpulse-dev cmake make \\
        libclang-dev ninja-build libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev libpam0g-dev

### openSUSE Tumbleweed

sudo zypper install gcc-c++ git curl wget nasm yasm gcc gtk3-devel clang libxcb-devel libXfixes-devel cmake alsa-lib-devel gstreamer-devel gstreamer-plugins-base-devel xdotool-devel pam-devel

### Fedora 28 (CentOS 8)

sudo yum -y install gcc-c++ git curl wget nasm yasm gcc gtk3-devel clang libxcb-devel libxdo-devel libXfixes-devel pulseaudio-libs-devel cmake alsa-lib-devel gstreamer1-devel gstreamer1-plugins-base-devel pam-devel

### Arch (Manjaro)

sudo pacman -Syu --needed unzip git cmake gcc curl wget yasm nasm zip make pkg-config clang gtk3 xdotool libxcb libxfixes alsa-lib pipewire

### Install vcpkg

git clone https://github.com/microsoft/vcpkg
cd vcpkg
git checkout 2023.04.15
cd ..
vcpkg/bootstrap-vcpkg.sh
export VCPKG\_ROOT=$HOME/vcpkg
vcpkg/vcpkg install libvpx libyuv opus aom

### Fix libvpx (For Fedora)

cd vcpkg/buildtrees/libvpx/src
cd \*
./configure
sed -i 's/CFLAGS+=-I/CFLAGS+=-fPIC -I/g' Makefile
sed -i 's/CXXFLAGS+=-I/CXXFLAGS+=-fPIC -I/g' Makefile
make
cp libvpx.a $HOME/vcpkg/installed/x64-linux/lib/
cd

### Build

curl --proto '\=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
git clone --recurse-submodules https://github.com/rustdesk/rustdesk
cd rustdesk
mkdir -p target/debug
wget https://raw.githubusercontent.com/c-smile/sciter-sdk/master/bin.lnx/x64/libsciter-gtk.so
mv libsciter-gtk.so target/debug
VCPKG\_ROOT=$HOME/vcpkg cargo run

How to build with Docker
------------------------

Begin by cloning the repository and building the Docker container:

git clone https://github.com/rustdesk/rustdesk
cd rustdesk
git submodule update --init --recursive
docker build -t "rustdesk-builder" .

Then, each time you need to build the application, run the following command:

docker run --rm -it -v $PWD:/home/user/rustdesk -v rustdesk-git-cache:/home/user/.cargo/git -v rustdesk-registry-cache:/home/user/.cargo/registry -e PUID="$(id -u)" -e PGID="$(id -g)" rustdesk-builder

Note that the first build may take longer before dependencies are cached, subsequent builds will be faster. Additionally, if you need to specify different arguments to the build command, you may do so at the end of the command in the `<OPTIONAL-ARGS>` position. For instance, if you wanted to build an optimized release version, you would run the command above followed by `--release`. The resulting executable will be available in the target folder on your system, and can be run with:

target/debug/rustdesk

Or, if you're running a release executable:

target/release/rustdesk

Please ensure that you run these commands from the root of the RustDesk repository, or the application may not find the required resources. Also note that other cargo subcommands such as `install` or `run` are not currently supported via this method as they would install or run the program inside the container instead of the host.

File Structure
--------------

-   **libs/hbb\_common**: video codec, config, tcp/udp wrapper, protobuf, fs functions for file transfer, and some other utility functions
-   **libs/scrap**: screen capture
-   **libs/enigo**: platform specific keyboard/mouse control
-   **libs/clipboard**: file copy and paste implementation for Windows, Linux, macOS.
-   **src/ui**: obsolete Sciter UI (deprecated)
-   **src/server**: audio/clipboard/input/video services, and network connections
-   **src/client.rs**: start a peer connection
-   **src/rendezvous\_mediator.rs**: Communicate with rustdesk-server, wait for remote direct (TCP hole punching) or relayed connection
-   **src/platform**: platform specific code
-   **flutter**: Flutter code for desktop and mobile
-   **flutter/web/js**: JavaScript for Flutter web client

Screenshots
-----------
