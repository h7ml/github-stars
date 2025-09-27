---
project: njs
stars: 1477
description: A subset of JavaScript language to use in nginx
url: https://github.com/nginx/njs
---

NGINX JavaScript
================

NGINX JavaScript, also known as NJS, is a dynamic module for NGINX that enables the extension of built-in functionality using familiar JavaScript syntax. The NJS language is a subset of JavaScript, compliant with ES5 (ECMAScript 5.1 Strict Variant) with some ES6 (ECMAScript 6) and newer extensions. See compatibility for more details.

Table of Contents
=================

-   How it works
-   Downloading and installing
    -   Provisioning the NGINX package repository
    -   Installing the NGINX JavaScript modules
    -   Installed files and locations
-   Getting started with NGINX JavaScript
    -   Verify NGINX is running
    -   Enabling the NGINX JavaScript modules
    -   Basics of writing .js script files
    -   Reference of custom objects, methods, and properties
    -   Example: Hello World
    -   The NJS command line interface (CLI)
-   Building from source
    -   Installing dependencies
    -   Cloning the NGINX JavaScript GitHub repository
    -   Building standalone command line interface utility (optional)
    -   Cloning the NGINX GitHub repository
    -   Building NGINX JavaScript as a module of NGINX
-   NGINX JavaScript technical specifications
    -   Supported distributions
    -   Supported deployment environments
    -   Supported NGINX versions
    -   Sizing recommendations
-   Asking questions, reporting issues, and contributing
-   Change log
-   License

How it works
============

NGINX JavaScript is provided as two dynamic modules for NGINX (ngx\_http\_js\_module and ngx\_stream\_js\_module) and can be added to any supported NGINX Open Source or NGINX Plus installation without recompilation.

The NJS module allows NGINX administrators to:

-   Add complex access control and security checks before requests reach upstream servers
-   Manipulate response headers
-   Write flexible, asynchronous content handlers, filters, and more!

See examples and our various projects developed with NJS:

#### https://github.com/nginxinc/nginx-openid-connect

Extends NGINX Plus functionality to communicate directly with OIDC-compatible Identity Providers, authenticating users and authorizing content delivered by NGINX Plus.

#### https://github.com/nginxinc/nginx-saml

Reference implementation of NGINX Plus as a service provider for SAML authentication.

#### https://github.com/nginxinc/njs-prometheus-module

Exposes Prometheus metrics endpoint directly from NGINX Plus.

Tip

NJS can also be used with the NGINX Unit application server. Learn more about NGINX Unit's Control API and how to define function calls with NJS.

Downloading and installing
==========================

Follow these steps to download and install precompiled NGINX and NGINX JavaScript Linux binaries. You may also choose to build the module locally from source code.

Provisioning the NGINX package repository
-----------------------------------------

Follow this guide to add the official NGINX package repository to your system and install NGINX Open Source. If you already have NGINX Open Source or NGINX Plus installed, skip the NGINX installation portion in the last step.

Installing the NGINX JavaScript modules
---------------------------------------

Once the repository has been provisioned, you may install NJS by issuing the following command:

### Ubuntu or Debian based systems

sudo apt install nginx-module-njs

### RHEL, RedHat and its derivatives

sudo yum install nginx-module-njs

### Alpine or similar systems

sudo apk add nginx-module-njs@nginx

### SuSE, SLES or similar systems

sudo zypper install nginx-module-njs

Tip

The package repository includes an alternate module that enables debug symbols. Although not recommended for production environments, this module may be helpful when developing NJS-based configurations. To download and install the debug version of the module, replace the module name in the previous command with `nginx-module-njs-dbg`.

Installed files and locations
-----------------------------

The package installation scripts install two modules, supporting NGINX `http` and `stream` contexts.

-   ngx\_http\_js\_module
    
    This NJS module enables manipulation of data transmitted over HTTP.
    
-   ngx\_stream\_js\_module
    
    This NJS module enables manipulation of data transmitted via stream protocols such as TCP and UDP.
    

By default, both modules are installed into the `/etc/nginx/modules` directory.

Getting started with NGINX JavaScript
=====================================

Usage of NJS involves enabling the module, adding JavaScript files with defined functions, and invoking exported functions in NGINX configuration files.

Verify NGINX is running
-----------------------

NGINX JavaScript is a module for NGINX Open Source or NGINX Plus. If you haven't done so already, follow these steps to install NGINX Open Source or NGINX Plus. Once installed, ensure the NGINX instance is running and able to respond to HTTP requests.

### Starting NGINX

Issue the following command to start NGINX:

sudo nginx

### Verify NGINX is responding to HTTP requests

curl -I 127.0.0.1

You should see the following response:

HTTP/1.1 200 OK
Server: nginx/1.25.5

Enabling the NGINX JavaScript modules
-------------------------------------

Once installed, either (or both) NJS module(s) must be included in the NGINX configuration file. On most systems, the NGINX configuration file is located at `/etc/nginx/nginx.conf` by default.

### Edit the NGINX configuration file

sudo vi /etc/nginx/nginx.conf

### Enable dynamic loading of NJS modules

Use the load\_module directive in the top-level (“main”) context to enable either (or both) module(s).

load\_module modules/ngx\_http\_js\_module.so;
load\_module modules/ngx\_stream\_js\_module.so;

Basics of writing .js script files
----------------------------------

NJS script files are typically named with a .js extension and placed in the `/etc/nginx/njs/` directory. They are usually comprised of functions that are then exported, making them available in NGINX configuration files.

Reference of custom objects, methods, and properties
----------------------------------------------------

NJS provides a collection of objects with associated methods and properties that are not part of ECMAScript definitions. See the complete reference to these objects and how they can be used to further extend and customize NGINX.

Example: Hello World
--------------------

Here's a basic "Hello World" example.

### example.js

The `hello` function in this file returns an HTTP 200 OK status response code along with the string "Hello World!", followed by a line feed. The function is then exported for use in an NGINX configuration file.

Add this file to the `/etc/nginx/njs` directory:

function hello(r) {
  r.return(200, "Hello world!\\n");
}

export default {hello}

### nginx.conf

We modify our NGINX configuration (`/etc/nginx/nginx.conf`) to import the JavaScript file and execute the function under specific circumstances.

\# Load the ngx\_http\_js\_module module
load\_module modules/ngx\_http\_js\_module.so;

events {}

http {
  # Set the path to our njs JavaScript files
  js\_path "/etc/nginx/njs/";

  # Import our JavaScript file into the variable "main"
  js\_import main from http/hello.js;

  server {
    listen 80;

    location / {
      # Execute the "hello" function defined in our JavaScript file on all HTTP requests
      # and respond with the contents of our function.
      js\_content main.hello;
    }
  }
}

For a full list of njs directives, see the ngx\_http\_js\_module and ngx\_stream\_js\_module module documentation pages.

Tip

A more detailed version of this and other examples can be found in the official njs-examples repository.

The NJS command line interface (CLI)
------------------------------------

NGINX JavaScript installs with a command line interface utility. The interface can be opened as an interactive shell or used to process JavaScript syntax from predefined files or standard input. Since the utility runs independently, NGINX-specific objects such as HTTP and Stream are not available within its runtime.

### Example usage of the interactive CLI

$ njs
\>> globalThis
global {
  njs: njs {
    version: '0.8.4'
  },
  global: \[Circular\],
  process: process {
    argv: \['/usr/bin/njs'\],
    env: {
      PATH: '/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin',
      HOSTNAME: 'f777c149d4f8',
      TERM: 'xterm',
      NGINX\_VERSION: '1.25.5',
      NJS\_VERSION: '0.8.4',
      PKG\_RELEASE: '1~buster',
      HOME: '/root'
    }
  },
  console: {
    log: \[Function: native\],
    dump: \[Function: native\],
    time: \[Function: native\],
    timeEnd: \[Function: native\]
  },
  print: \[Function: native\]
}
\>>

### Example usage of the non-interactive CLI

$ echo "2\*\*3" | njs -q
8

Building from source
====================

The following steps can be used to build NGINX JavaScript as a dynamic module to be integrated into NGINX or a standalone binary for use as a command line interface utility.

Important

To build the module for use with NGINX, you will also need to clone, configure and build NGINX by following the steps outlined in this document.

Installing dependencies
-----------------------

Most Linux distributions will require several dependencies to be installed in order to build NGINX and NGINX JavaScript. The following instructions are specific to the `apt` package manager, widely available on most Ubuntu/Debian distributions and their derivatives.

### Installing compiler and make utility

sudo apt install gcc make

### Installing dependency libraries

sudo apt install libpcre3-dev zlib1g-dev libssl-dev libxml2-dev libxslt-dev

For building with QuickJS, you will also need to build the QuickJS library:

git clone https://github.com/bellard/quickjs
cd quickjs
CFLAGS='\-fPIC' make libquickjs.a

Warning

This is the minimal set of dependency libraries needed to build NGINX and NJS. Other dependencies may be required if you choose to build NGINX with additional modules. Monitor the output of the `configure` command discussed in the following sections for information on which modules may be missing.

Cloning the NGINX JavaScript GitHub repository
----------------------------------------------

Using your preferred method, clone the NGINX JavaScript repository into your development directory. See Cloning a GitHub Repository for additional help.

https://github.com/nginx/njs.git

Building the standalone command line interface utility (Optional)
-----------------------------------------------------------------

The following steps are optional and only needed if you choose to build NJS as a standalone utility.

### Install dependencies

To use the NJS interactive shell, you will need to install the libedit-dev library

sudo apt install libedit-dev

### Configure and build

Run the following commands from the root directory of your cloned repository:

./configure

Build NGINX JavaScript:

make

The utility should now be available at `<NJS_SRC_ROOT_DIR>/build/njs`. See The NJS Command Line Interface (CLI) for information on usage.

Cloning the NGINX GitHub repository
-----------------------------------

Clone the NGINX source code repository in a directory outside of the previously cloned NJS source repository.

https://github.com/nginx/nginx.git

Building NGINX JavaScript as a module of NGINX
----------------------------------------------

To build NGINX JavaScript as a dynamic module, execute the following commands from the NGINX source code repository's root directory:

Note

Replace `<NJS_SRC_ROOT_DIR>` with the actual path to your NJS source directory.

auto/configure --add-dynamic-module=<NJS\_SRC\_ROOT\_DIR\>/nginx

To build with QuickJS support, provide include and library path using `--with-cc-opt=` and `--with-ld-opt=` options:

Note

Replace `<NJS_SRC_ROOT_DIR>` with the actual path to your NJS source directory and `<QUICKJS_SRC_ROOT_DIR>` with the actual path to your QuickJS source directory.

auto/configure --add-dynamic-module=<NJS\_SRC\_ROOT\_DIR\>/nginx \\
    --with-cc-opt="\-I<QUICKJS\_SRC\_ROOT\_DIR>" \\
    --with-ld-opt="\-L<QUICKJS\_SRC\_ROOT\_DIR>"

Warning

By default, this method will only build the `ngx_http_js_module` module. To use NJS with the NGINX Stream module, you'll need to enable it during the `configure` step so it builds with the NGINX binary. Doing so will automatically compile the `ngx_stream_js_module` module when NJS is added to the build. One way of accomplishing this is to alter the `configure` step to:

auto/configure --with-stream \\
    --add-dynamic-module=<NJS\_SRC\_ROOT\_DIR\>/nginx

Compile the module

make

Tip

To build NGINX with NGINX JavaScript embedded into a single binary, alter the `configure` step to the following:

auto/configure --add-module=<NJS\_SRC\_ROOT\_DIR\>/nginx

### Install module

If built as a dynamic module(s), the NGINX JavaScript module(s) will be available in the `<NGINX_SRC_ROOT_DIR>/objs/` directory. The module(s) can then be copied to an existing NGINX installation and enabled. See Enabling the NGINX JavaScript Modules for details.

### Install compiled NGINX and NGINX JavaScript binaries

Alternatively, you may choose to install the built NGINX and NGINX JavaScript binaries by issuing the following command:

Important

If built into the NGINX binary as a standard (not dynamic) module, this will be the easiest method of installation

make install

By default, the NGINX binary will be installed into `/usr/local/nginx/sbin/nginx`. The NGINX JavaScript module(s) will be copied to `/usr/local/nginx/modules/`.

NGINX JavaScript technical specifications
=========================================

Technical specifications for NJS are identical to those of NGINX.

Supported distributions
-----------------------

See Tested Operating Systems and Platforms for a complete list of supported distributions.

Supported deployment environments
---------------------------------

-   Container
-   Public cloud (AWS, Google Cloud Platform, Microsoft Azure)
-   Virtual machine

Supported NGINX versions
------------------------

NGINX JavaScript is supported by all NGINX Open Source versions starting with nginx-1.14 and all NGINX Plus versions starting with NGINX Plus R15.

Asking questions, reporting issues, and contributing
====================================================

We encourage you to engage with us. Please see the Contributing guide for information on how to ask questions, report issues and contribute code.

Change log
==========

See our release page to keep track of updates.

License
=======

2-clause BSD-like license

* * *

Additional documentation available at: https://nginx.org/en/docs/njs/

©2024 F5, Inc. All rights reserved. https://www.f5.com/products/nginx
