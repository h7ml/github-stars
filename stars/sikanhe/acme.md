---
project: acme
stars: 44
description: Acme (Let's Encrypt) Client for Elixir
url: https://github.com/sikanhe/acme
---

Acme
====

Installation
------------

Add `acme` to your list of dependencies in `mix.exs`:

def deps do
  \[{:acme, "~> 0.5.1"}\]
end

How to connect to an Acme server
--------------------------------

All client request are called with a connection. I chose to do it this way (over something like hard coded config) so you have the flexability to run multiple connections to many Acme servers at the same time or fetch certificates for different accounts.

To connect to an Acme server, you want use the &Acme.Client.start\_link/1 function that takes these options:

-   `server_url` - The Acme server url
-   `private_key` - A private\_key either in PEM format or as a JWK map, this is required unless you use the `private_key_file` option
-   `private_key_file` - Instead of a private key map/pem value, you can also pass a private key file path

{:ok, conn} \= Acme.Client.start\_link(\[
  server: "https://acme-v01.api.letsencrypt.org",
  private\_key\_file: "path/to/key.pem"
\])

Examples
--------

### Staring a connection

Acme.Client.start\_link(server: ..., private\_key: ...)
#=> {:ok, conn}

We are going to reuse this connection for all examples below

### Register an account

Acme.register("mailto:acme@example.com") |> Acme.request(conn)
#=> {:ok, %Registration{...}}
\# Agree to terms
Acme.agree\_terms(registration) |> Acme.request(conn)

### Get new authorization for domain

Acme.authorize("yourdomain.com") |> Acme.request(conn)
#=> {:ok, %Authorization{
  status: "pending",
  challenges: \[
    %Acme.Challenge{
      type: "http-01",
      token "..."
    }
  \]
}}

### Respond to a challenge

challenge \= %Acme.Challenge{type: "http-01", token: ...}
Acme.respond\_challenge(challenge) |> Acme.request(conn)
#=> {:ok, %Challenge{status: "pending", ...}}

### Request a certificate

Generate a CSR, we provide OpenSSL helpers to help you with this in Acme.OpenSSL

\# Certificate subject informations (only common\_name is required)
subject \= %{
  common\_name: "example.acme.com",
  organization\_name: "Acme INC.",
  organizational\_unit: "HR",
  locality\_name: "Philadelphia",
  state\_or\_province: "Pennsylvania",
  country\_name: "US"
}

\# Generate a CSR in DER format
{:ok, csr} \= Acme.OpenSSL.generate\_csr("/path/to/your/private\_key.pem", subject)

\# Request a certificate and get back its URL
Acme.new\_certificate(csr) |> Acme.request(conn)
#=> {:ok, "https://example.com/acme/cert/asdf"}

\# Fetch the certificate using the URL
Acme.get\_certificate("https://example.com/acme/cert/asdf")
|> Acme.request(conn)
#=> {:ok, <<DER-encoded certificate>>}

### Revoke a certificate

You can revoke a certificate by passing the certificate in DER format and specify a reason code. You can see all possible reason codes at: https://tools.ietf.org/html/rfc5280#section-5.3.1

Acme.revoke\_certificate(<<DER\-encoded certificate\>>, 0)
#=> :ok

License
=======

The MIT License (MIT)

Copyright (c) 2017-present, Sikan He

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
