---
project: echo
stars: 30011
description: High performance, minimalist Go web framework
url: https://github.com/labstack/echo
---

Echo
----

High performance, extensible, minimalist Go web framework.

-   Official website
-   Quick start
-   Middlewares

Help and questions: Github Discussions

### Feature Overview

-   Optimized HTTP router which smartly prioritize routes
-   Build robust and scalable RESTful APIs
-   Group APIs
-   Extensible middleware framework
-   Define middleware at root, group or route level
-   Data binding for JSON, XML and form payload
-   Handy functions to send variety of HTTP responses
-   Centralized HTTP error handling
-   Template rendering with any template engine
-   Define your format for the logger
-   Highly customizable
-   Automatic TLS via Let’s Encrypt
-   HTTP/2 support

Sponsors
--------

**Encore – the platform for building Go-based cloud backends**

  

Click here for more information on sponsorship.

Benchmarks
----------

Date: 2020/11/11  
Source: https://github.com/vishr/web-framework-benchmark  
Lower is better!

The benchmarks above were run on an Intel(R) Core(TM) i7-6820HQ CPU @ 2.70GHz

Guide
-----

### Installation

// go get github.com/labstack/echo/{version}
go get github.com/labstack/echo/v4

Latest version of Echo supports last four Go major releases and might work with older versions.

### Example

package main

import (
  "github.com/labstack/echo/v4"
  "github.com/labstack/echo/v4/middleware"
  "log/slog"
  "net/http"
)

func main() {
  // Echo instance
  e := echo.New()

  // Middleware
  e.Use(middleware.Logger())
  e.Use(middleware.Recover())

  // Routes
  e.GET("/", hello)

  // Start server
  if err := e.Start(":8080"); err != nil && !errors.Is(err, http.ErrServerClosed) {
    slog.Error("failed to start server", "error", err)
  }
}

// Handler
func hello(c echo.Context) error {
  return c.String(http.StatusOK, "Hello, World!")
}

Official middleware repositories
================================

Following list of middleware is maintained by Echo team.

Repository

Description

github.com/labstack/echo-jwt

JWT middleware

github.com/labstack/echo-contrib

casbin, gorilla/sessions, jaegertracing, prometheus, pprof, zipkin middlewares

Third-party middleware repositories
===================================

Be careful when adding 3rd party middleware. Echo teams does not have time or manpower to guarantee safety and quality of middlewares in this list.

Repository

Description

deepmap/oapi-codegen

Automatically generate RESTful API documentation with OpenAPI Client and Server Code Generator

github.com/swaggo/echo-swagger

Automatically generate RESTful API documentation with Swagger 2.0.

github.com/ziflex/lecho

Zerolog logging library wrapper for Echo logger interface.

github.com/brpaz/echozap

Uber´s Zap logging library wrapper for Echo logger interface.

github.com/samber/slog-echo

Go slog logging library wrapper for Echo logger interface.

github.com/darkweak/souin/plugins/echo

HTTP cache system based on Souin to automatically get your endpoints cached. It supports some distributed and non-distributed storage systems depending your needs.

github.com/mikestefanello/pagoda

Rapid, easy full-stack web development starter kit built with Echo.

github.com/go-woo/protoc-gen-echo

ProtoBuf generate Echo server side code

Please send a PR to add your own library here.

Contribute
----------

**Use issues for everything**

-   For a small change, just send a PR.
-   For bigger changes open an issue for discussion before sending a PR.
-   PR should have:
    -   Test case
    -   Documentation
    -   Example (If it makes sense)
-   You can also contribute by:
    -   Reporting issues
    -   Suggesting new features or enhancements
    -   Improve/fix documentation

Credits
-------

-   Vishal Rana (Author)
-   Nitin Rana (Consultant)
-   Roland Lammel (Maintainer)
-   Martti T. (Maintainer)
-   Pablo Andres Fuente (Maintainer)
-   Contributors

License
-------

MIT
