---
project: croc
stars: 28426
description: Easily and securely send things from one computer to another :crocodile: :package:
url: https://github.com/schollz/croc
---

  

This project is supported by Github sponsors.

`croc` is a tool that allows any two computers to simply and securely transfer files and folders. AFAIK, _croc_ is the only CLI file-transfer tool that does **all** of the following:

-   allows **any two computers** to transfer data (using a relay)
-   provides **end-to-end encryption** (using PAKE)
-   enables easy **cross-platform** transfers (Windows, Linux, Mac)
-   allows **multiple file** transfers
-   allows **resuming transfers** that are interrupted
-   local server or port-forwarding **not needed**
-   **ipv6-first** with ipv4 fallback
-   can **use proxy**, like tor

For more information about `croc`, see my blog post or read a recent interview I did.

Install
-------

Download the latest release for your system, or install a release from the command-line:

```
curl https://getcroc.schollz.com | bash
```

On macOS you can install the latest release with Homebrew:

```
brew install croc
```

On macOS you can also install the latest release with MacPorts:

```
sudo port selfupdate
sudo port install croc
```

On Windows you can install the latest release with Scoop, Chocolatey, or Winget:

```
scoop install croc
```

```
choco install croc
```

```
winget install schollz.croc
```

On Unix you can install the latest release with Nix:

```
nix-env -i croc
```

On Alpine Linux you have to install dependencies first:

```
apk add bash coreutils
wget -qO- https://getcroc.schollz.com | bash
```

On Arch Linux you can install the latest release with `pacman`:

```
pacman -S croc
```

On Fedora you can install with `dnf`:

```
dnf install croc
```

On Gentoo you can install with `portage`:

```
emerge net-misc/croc
```

On Termux you can install with `pkg`:

```
pkg install croc
```

On FreeBSD you can install with `pkg`:

```
pkg install croc
```

On Linux, macOS, and Windows you can install from conda-forge globally with `pixi`:

```
pixi global install croc
```

or into a particular environment with `conda`:

```
conda install --channel conda-forge croc
```

Or, you can install Go and build from source (requires Go 1.17+):

```
go install github.com/schollz/croc/v10@latest
```

On Android there is a 3rd party F-Droid app available to download.

Usage
-----

To send a file, simply do:

```
$ croc send [file(s)-or-folder]
Sending 'file-or-folder' (X MB)
Code is: code-phrase
```

Then to receive the file (or folder) on another computer, you can just do

```
croc code-phrase
```

The code phrase is used to establish password-authenticated key agreement (PAKE) which generates a secret key for the sender and recipient to use for end-to-end encryption.

There are a number of configurable options (see `--help`). A set of options (like custom relay, ports, and code phrase) can be set using `--remember`.

### Using `croc` on Linux or Mac OS

On Linux and Mac OS, the sending & receiving is slightly different to avoid leaking the secret via the process name. On these systems you will need to run `croc` with the secret as an environment variable. For example, to receive with the secret `***`:

```
CROC_SECRET=*** croc
```

This will show only `croc` in the process list of a multi-user system and not leak the secret.

For a single-user system the default behavior can be permanently enabled by running

```
croc --classic
```

and confirming. Run this command again to disable classic mode.

### Custom code phrase

You can send with your own code phrase (must be more than 6 characters).

```
croc send --code [code-phrase] [file(s)-or-folder]
```

### Allow overwriting without prompt

By default, croc will prompt whether to overwrite a file. You can automatically overwrite files by using the `--overwrite` flag (recipient only). For example, receive a file to automatically overwrite:

```
croc --yes --overwrite <code>
```

### Use pipes - stdin and stdout

You can pipe to `croc`:

```
cat [filename] | croc send
```

In this case `croc` will automatically use the stdin data and send and assign a filename like "croc-stdin-123456789". To receive to `stdout` at you can always just use the `--yes` will automatically approve the transfer and pipe it out to `stdout`.

```
croc --yes [code-phrase] > out
```

All of the other text printed to the console is going to `stderr` so it will not interfere with the message going to `stdout`.

### Send text

Sometimes you want to send URLs or short text. In addition to piping, you can easily send text with `croc`:

```
croc send --text "hello world"
```

This will automatically tell the receiver to use `stdout` when they receive the text so it will be displayed.

### Use a proxy

You can use a proxy as your connection to the relay by adding a proxy address with `--socks5`. For example, you can send via a tor relay:

```
croc --socks5 "127.0.0.1:9050" send SOMEFILE
```

### Change encryption curve

You can choose from several different elliptic curves to use for encryption by using the `--curve` flag. Only the recipient can choose the curve. For example, receive a file using the P-521 curve:

```
croc --curve p521 <codephrase>
```

Available curves are P-256, P-348, P-521 and SIEC. P-256 is the default curve.

### Change hash algorithm

You can choose from several different hash algorithms. The default is the `xxhash` algorithm which is fast and thorough. If you want to optimize for speed you can use the `imohash` algorithm which is even faster, but since it samples files (versus reading the whole file) it can mistakenly determine that a file is the same on the two computers transferring - though this is only a problem if you are syncing files versus sending a new file to a computer.

```
croc send --hash imohash SOMEFILE
```

### Self-host relay

The relay is needed to staple the parallel incoming and outgoing connections. By default, `croc` uses a public relay but you can also run your own relay:

```
croc relay
```

By default it uses TCP ports 9009-9013. Make sure to open those up. You can customize the ports (e.g. `croc relay --ports 1111,1112`), but you must have a minimum of **2** ports for the relay. The first port is for communication and the subsequent ports are used for the multiplexed data transfer.

You can send files using your relay by entering `--relay` to change the relay that you are using if you want to custom host your own.

```
croc --relay "myrelay.example.com:9009" send [filename]
```

Note, when sending, you only need to include the first port (the communication port). The subsequent ports for data transfer will be transmitted back to the user from the relay.

#### Self-host relay (docker)

If it's easier you can also run a relay with Docker:

```
docker run -d -p 9009-9013:9009-9013 -e CROC_PASS='YOURPASSWORD' schollz/croc
```

Be sure to include the password for the relay otherwise any requests will be rejected.

```
croc --pass YOURPASSWORD --relay "myreal.example.com:9009" send [filename]
```

Note: when including `--pass YOURPASSWORD` you can instead pass a file with the password, e.g. `--pass FILEWITHPASSWORD`.

License
-------

MIT

Acknowledgements
----------------

`croc` has gone through many iterations, and I am awed by all the great contributions! If you feel like contributing, in any way, by all means you can send an Issue, a PR, or ask a question.

Thanks @warner for the idea, @tscholl2 for the encryption gists, @skorokithakis for code on proxying two connections. Finally thanks for making pull requests @maximbaz, @meyermarcel, @Girbons, @techtide, @heymatthew, @Lunsford94, @lummie, @jesuiscamille, @threefjord, @marcossegovia, @csleong98, @afotescu, @callmefever, @El-JojA, @anatolyyyyyy, @goggle, @smileboywtu, @nicolashardy, @fbartels, @rkuprov, @hreese, @xenrox and Ipar!
