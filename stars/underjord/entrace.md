---
project: entrace
stars: 50
description: null
url: https://github.com/underjord/entrace
---

Entrace
=======

A library to make it easy to use the fantastic Erlang/OTP tracing facilities in an idiomatically Elixir way. Built-in safeties and discoverable function naming. The hope is that this makes a BEAM superpower more well-known in the Elixir community.

Tested to work at least as far back as OTP 24, gets more features under OTP 25/26.

Installation
------------

To install, add it to `mix.exs` under the `deps`:

\# ..
{:entrace, "~> 0.1"},
\# ..

In an Elixir app
----------------

Create a module for your app:

defmodule MyApp.Tracer do
    use Entrace.Tracer
end

In your `application.ex` add this to your supervisor children, like an Ecto Repo or a Phoenix PubSub module:

\# ..
  MyApp.Tracer,
\# ..

When you want to trace a function in your app from iex:

\# This will trace across your cluster
MyApp.Tracer.trace\_cluster({MyApp.TheModule, :my\_function, 3}, &IO.inspect/1)

In a Phoenix app?
-----------------

There is another library using Entrace that will enable using it inside of Phoenix Live Dashboard. You get web UI for tracing :) Check it out at entrace\_live\_dashboard.

Using the primitives
--------------------

{:ok, pid} \= Entrace.start\_link()
Entrace.trace\_cluster(pid, {MyApp.TheModule, :my\_function, 3}, &IO.inspect/1)
