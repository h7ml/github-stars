---
project: nodemcu-firmware
stars: 7823
description: Lua based interactive firmware for ESP8266, ESP8285 and ESP32
url: https://github.com/nodemcu/nodemcu-firmware
---

NodeMCU 3.0.0
=============

> Lua-based firmware for ESP8266 WiFi SOC

NodeMCU is an open source Lua based firmware for the ESP8266 WiFi SOC from Espressif and uses an on-module flash-based SPIFFS file system. NodeMCU is implemented in C and is layered on the Espressif NON-OS SDK.

The firmware was initially developed as is a companion project to the popular ESP8266-based NodeMCU development modules, but the project is now community-supported, and the firmware can now be run on _any_ ESP module.

**The NodeMCU `release` and `dev` branches target the ESP8266. The `dev-esp32` branch targets the ESP32.**

Summary
-------

-   Easy to program wireless node and/or access point
-   Based on Lua 5.1.4 or Lua 5.3 but without `debug`, `io`, `os` and (most of the) `math` modules
-   Asynchronous event-driven programming model
-   More than **70 built-in C modules** and **close to 20 Lua modules**
-   Firmware available with or without floating point support (integer-only uses less memory)
-   Up-to-date documentation at https://nodemcu.readthedocs.io

### LFS support

In July 2018 support for a Lua Flash Store (LFS) was introduced. LFS allows Lua code and its associated constant data to be executed directly out of flash-memory; just as the firmware itself is executed. This now enables NodeMCU developers to create **Lua applications with up to 256Kb** Lua code and read-only constants executing out of flash. All of the RAM is available for read-write data!

Programming Model
-----------------

The NodeMCU programming model is similar to that of Node.js, only in Lua. It is asynchronous and event-driven. Many functions, therefore, have parameters for callback functions. To give you an idea what a NodeMCU program looks like study the short snippets below. For more extensive examples have a look at the `/lua_examples` folder in the repository on GitHub.

\-- a simple HTTP server
srv \= net.createServer(net.TCP)
srv:listen(80, function(conn)
	conn:on("receive", function(sck, payload)
		print(payload)
		sck:send("HTTP/1.0 200 OK\\r\\nContent-Type: text/html\\r\\n\\r\\n<h1> Hello, NodeMCU.</h1>")
	end)
	conn:on("sent", function(sck) sck:close() end)
end)

\-- connect to WiFi access point
wifi.setmode(wifi.STATION)
wifi.sta.config{ssid\="SSID", pwd\="password"}

Documentation
-------------

The entire NodeMCU documentation is maintained right in this repository at /docs. The fact that the API documentation is maintained in the same repository as the code that _provides_ the API ensures consistency between the two. With every commit the documentation is rebuilt by Read the Docs and thus transformed from terse Markdown into a nicely browsable HTML site at https://nodemcu.readthedocs.io.

Pages:

-   How to build the firmware
-   How to flash the firmware
-   How to upload code and NodeMCU IDEs
-   API documentation for every module

Releases
--------

Due to the ever-growing number of modules available within NodeMCU, pre-built binaries are no longer made available. Use the automated custom firmware build service to get the specific firmware configuration you need, or consult the documentation for other options to build your own firmware.

This project uses two main branches, `release` and `dev`. `dev` is actively worked on and it's also where PRs should be created against. `release` thus can be considered "stable" even though there are no automated regression tests. The goal is to merge back to `release` roughly every 2 months. Depending on the current "heat" (issues, PRs) we accept changes to `dev` for 5-6 weeks and then hold back for 2-3 weeks before the next snap is completed.

A new tag is created every time the `dev` branch is merged back to `release`. They are listed in this repo's releases.

Tag names follow the `<SDK-version>-release_yyyymmdd` pattern.

Support
-------

See https://nodemcu.readthedocs.io/en/release/support/.

License
-------

MIT © zeroday/nodemcu.com
