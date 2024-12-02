---
project: swoosh_mua
stars: 1
description: Another SMTP adapter for Swoosh
url: https://github.com/ruslandoga/swoosh_mua
---

Archiving in favor of swoosh/swoosh#870

* * *

Swoosh.Mua
==========

Swoosh adapter for Mua.

Installation
------------

defp deps do
  \[
    {:swoosh\_mua, "~> 0.1.0"}
  \]
end

Usage
-----

\# for supported configuration, please see https://hexdocs.pm/mua/Mua.html#t:option/0
Application.put\_env(:example, Mailer, adapter: Swoosh.Mua)

defmodule Mailer do
  use Swoosh.Mailer, otp\_app: :example
end

email \=
  Swoosh.Email.new(
    from: {"Mua", "mua@github.com"},
    to: {"Receiver", "receiver@mailhog.example"},
    subject: "how are you?",
    text\_body: "I'm fine",
    html\_body: "I'm <i>fine</i>"
  )

Mailer.deliver(email)
