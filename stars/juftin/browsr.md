---
project: browsr
stars: 356
description: 🗂️ a pleasant file explorer in your terminal supporting all filesystems
url: https://github.com/juftin/browsr
---

a pleasant **file explorer** in your terminal supporting **all filesystems**

**`browsr`** 🗂️ is a pleasant **file explorer** in your terminal. It's a command line **TUI** (text-based user interface) application that empowers you to browse the contents of local and remote filesystems with your keyboard or mouse.

You can quickly navigate through directories and peek at files whether they're hosted **locally**, in **GitHub**, over **SSH**, in **AWS S3**, **Google Cloud Storage**, or **Azure Blob Storage**. View code files with syntax highlighting, format JSON files, render images, convert data files to navigable datatables, and more.

Screenshots

Screen Recording browsr.mp4

Installation
------------

It's recommended to use pipx instead of pip. `pipx` installs the package in an isolated environment and makes it available everywhere. If you'd like to use `pip` instead, just replace `pipx` with `pip` in the below command.

pipx install browsr

### Extra Installation

If you're looking to use **`browsr`** on remote file systems, like GitHub or AWS S3, you'll need to install the `remote` extra. If you'd like to browse parquet / feather files, you'll need to install the `data` extra. Or, even simpler, you can install the `all` extra to get all the extras.

pipx install "browsr\[all\]"

Usage
-----

Simply give **`browsr`** a path to a local or remote file / directory. Check out the Documentation for more information about the file systems supported.

### Local

browsr ~/Downloads/

### GitHub

```
browsr github://juftin:browsr
```

```
export GITHUB_TOKEN="ghp_1234567890"
browsr github://juftin:browsr-private@main
```

### Cloud

browsr s3://my-bucket

\*\* _Currently AWS S3, Google Cloud Storage, and Azure Blob Storage / Data Lake are supported._

### SSH / SFTP

browsr ssh://username@example.com:22

License
-------

**`browsr`** is distributed under the terms of the MIT license.
