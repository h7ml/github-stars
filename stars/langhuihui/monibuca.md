---
project: monibuca
stars: 2222
description: 🧩 Monibuca is a Modularized, Extensible framework for building Streaming Server
url: https://github.com/langhuihui/monibuca
---

  

Monibuca v5
===========

A highly scalable high-performance streaming server development framework developed purely in Go  
中文文档 · **Explore the docs »**  
  
Report Bug · Request Feature

Table of Contents

1.  About
2.  Getting Started
3.  Usage
4.  Build Tags
5.  Monitoring
6.  Plugin Development
7.  Architecture
8.  Third-party Plugins
9.  Contributing
10.  License
11.  Contact

About
-----

Monibuca is a powerful streaming server framework written entirely in Go. It's designed to be:

-   🚀 **High Performance** - Lock-free design, partial manual memory management, multi-core computing
    
-   ⚡ **Low Latency** - Zero-wait forwarding, sub-second latency across the entire chain
    
-   📦 **Modular** - Load on demand, unlimited extensibility
    
-   🔧 **Flexible** - Highly configurable to meet various streaming scenarios
    
-   💪 **Scalable** - Supports distributed deployment, easily handles large-scale scenarios
    
-   🔍 **Debug Friendly** - Built-in debug plugin, real-time performance monitoring and analysis
    
-   🎥 **Media Processing** - Supports screenshot, transcoding, SEI data processing
    
-   🔄 **Cluster Capability** - Built-in cascade and room management
    
-   🎮 **Preview Features** - Supports video preview, multi-screen preview, custom screen layouts
    
-   🔐 **Security** - Provides encrypted transmission and stream authentication
    
-   📊 **Performance Monitoring** - Supports stress testing and performance metrics collection (integrated in test plugin)
    
-   📝 **Log Management** - Log rotation, auto cleanup, custom extensions
    
-   🎬 **Recording & Playback** - Supports MP4, HLS, FLV formats, speed control, seeking, pause
    
-   ⏱️ **Dynamic Time-Shift** - Dynamic cache design, supports live time-shift playback
    
-   🌐 **Remote Call** - Supports gRPC interface for cross-language integration
    
-   🏷️ **Stream Alias** - Supports dynamic stream alias, flexible multi-stream management
    
-   🤖 **AI Capabilities** - Integrated inference engine, ONNX model support, custom pre/post processing
    
-   🪝 **WebHook** - Subscribe to stream lifecycle events for business system integration
    
-   🔒 **Private Protocol** - Supports custom private protocols for special business needs
    
-   🔄 **Supported Protocols**: RTMP, RTSP, HTTP-FLV, WS-FLV, HLS, WebRTC, GB28181, ONVIF, SRT
    

(back to top)

Getting Started
---------------

### Prerequisites

-   Go 1.23 or higher
-   Basic understanding of streaming protocols

### Run with Default Configuration

cd example/default
go run -tags sqlite main.go

### Web UI

Place the `admin.zip` file (do not unzip) in the same directory as your configuration file.

Then visit http://localhost:8080 to access the UI.

(back to top)

Examples
--------

For more examples, please check out the example documentation.

(back to top)

Build Tags
----------

The following build tags can be used to customize your build:

Build Tag

Description

disable\_rm

Disables the memory pool

sqlite

Enables the sqlite DB

sqliteCGO

Enables the sqlite cgo version DB

mysql

Enables the mysql DB

postgres

Enables the postgres DB

duckdb

Enables the duckdb DB

taskpanic

Throws panic, for testing

fasthttp

Enables the fasthttp server instead of net/http

enable\_buddy

Enables the buddy memory pre-allocation

(back to top)

Monitoring
----------

Monibuca supports Prometheus monitoring out of the box. Add the following to your Prometheus configuration:

scrape\_configs:
  - job\_name: "monibuca"
    metrics\_path: "/api/metrics"
    static\_configs:
      - targets: \["localhost:8080"\]

(back to top)

Plugin Development
------------------

Monibuca's functionality can be extended through plugins. For information on creating plugins, see the plugin guide.

(back to top)

Architecture
------------

For detailed architecture design documentation, please refer to the Architecture Documentation.

(back to top)

Third-party Plugins
-------------------

-   https://github.com/cuteLittleDevil/m7s-jt1078

(back to top)

Contributing
------------

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

(back to top)

License
-------

Distributed under the AGPL License. See `LICENSE` for more information.

(back to top)

Contact
-------

monibuca - @m7server - service@monibuca.com

Project Link: https://github.com/langhuihui/monibuca

(back to top)
