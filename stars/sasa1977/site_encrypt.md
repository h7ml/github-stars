---
project: site_encrypt
stars: 471
description: Integrated certification via Let's encrypt for Elixir-powered sites 
url: https://github.com/sasa1977/site_encrypt
---

SiteEncrypt
===========

This project aims to provide integrated certification via Let's encrypt for sites implemented in Elixir.

Integrated certification means that you don't need to run any other OS process in background. Start your site for the first time, and the system will obtain the certificate, and periodically renew it before it expires.

The target projects are small-to-medium Elixir based sites which don't sit behind reverse proxies such as nginx.

Status
------

-   The library is tested in a simple production, where it has been constantly running since mid 2018.
-   Native Elixir client is very new, and not considered stable. If you prefer reliable behaviour, use the Certbot client. This will require installing Certbot >= 0.31
-   The API is not stable. Expect breaking changes in the future.

Quick start
-----------

A basic demo Phoenix project is available here.

1.  Add the dependency to `mix.exs`:
    
    defmodule PhoenixDemo.Mixfile do
      \# ...
    
      defp deps do
        \[
          \# ...
          {:site\_encrypt, "~> 0.6"}
        \]
      end
    end
    
    Don't forget to invoke `mix.deps` after that.
    
2.  Expand your endpoint
    
    defmodule PhoenixDemo.Endpoint do
      \# ...
    
      \# add this instead of \`use Phoenix.Endpoint\`
      use SiteEncrypt.Phoenix.Endpoint, otp\_app: :my\_app
    
      \# ...
    
      @impl SiteEncrypt
      def certification do
        SiteEncrypt.configure(
          \# Note that native client is very immature. If you want a more stable behaviour, you can
          \# provide \`:certbot\` instead. Note that in this case certbot needs to be installed on the
          \# host machine.
          client: :native,
    
          domains: \["mysite.com", "www.mysite.com"\],
          emails: \["contact@abc.org", "another\_contact@abc.org"\],
    
          \# By default the certs will be stored in tmp/site\_encrypt\_db, which is convenient for
          \# local development. Make sure that tmp folder is gitignored.
          #
          \# Set OS env var SITE\_ENCRYPT\_DB on staging/production hosts to some absolute path
          \# outside of the deployment folder. Otherwise, the deploy may delete the db\_folder,
          \# which will effectively remove the generated key and certificate files.
          db\_folder:
            System.get\_env("SITE\_ENCRYPT\_DB", Path.join("tmp", "site\_encrypt\_db")),
    
          \# set OS env var CERT\_MODE to "staging" or "production" on staging/production hosts
          directory\_url:
            case System.get\_env("CERT\_MODE", "local") do
              "local" \-> {:internal, port: 4002}
              "staging" \-> "https://acme-staging-v02.api.letsencrypt.org/directory"
              "production" \-> "https://acme-v02.api.letsencrypt.org/directory"
            end
        )
      end
    
      \# ...
    end
    
3.  Start the endpoint:
    
    defmodule PhoenixDemo.Application do
      use Application
    
      def start(\_type, \_args) do
        children \= \[PhoenixDemo.Endpoint\]
        opts \= \[strategy: :one\_for\_one, name: PhoenixDemo.Supervisor\]
        Supervisor.start\_link(children, opts)
      end
    
      \# ...
    end
    
4.  Optionally add a certification test
    
    defmodule PhoenixDemo.Endpoint.CertificationTest do
      use ExUnit.Case, async: false
      import SiteEncrypt.Phoenix.Test
    
      test "certification" do
        clean\_restart(PhoenixDemo.Endpoint)
        cert \= get\_cert(PhoenixDemo.Endpoint)
        assert cert.domains \== ~w/mysite.com www.mysite.com/
      end
    end
    

And that's it! At this point you can start the system:

```
$ iex -S mix phx.server

[info]  Generating a temporary self-signed certificate. This certificate will be used until a proper certificate is issued by the CA server.
[info]  Running PhoenixDemo.Endpoint with cowboy 2.7.0 at 0.0.0.0:4000 (http)
[info]  Running PhoenixDemo.Endpoint with cowboy 2.7.0 at 0.0.0.0:4001 (https)
[info]  Running local ACME server at port 4002
[info]  Ordering a new certificate for domain mysite.com
[info]  New certificate for domain mysite.com obtained
[info]  Certificate successfully obtained!
```

And visit your certified site at https://localhost:4001

Testing in production
---------------------

In general, the configuration above should work out of the box in production, as long as the domain is correctly setup, and ports properly forwarded, so the HTTP site is externally available at port 80.

If you want a more manual first deploy test, here's how you can do it:

1.  Explicitly set `mode: :manual` in `certification/0`. This means that the site won't automatically certify itself. However, during the first boot it will generate a self-signed certificate.
    
2.  Deploy the site and verify that it's externally reachable via HTTP on port 80.
    
3.  Start a remote `iex` shell session to the running system.
    
4.  Perform a trial certification through the staging Let's Encrypt CA:
    
    iex\> SiteEncrypt.dry\_certify(
           MySystemWeb.Endpoint,
           directory\_url: "https://acme-staging-v02.api.letsencrypt.org/directory"
         )
    

Keep in mind that this can be only invoked in the remote `iex` shell session inside the running system.

If the certification succeeds, the function will return the key and the certificate. These files won't be stored on disk, and they won't be used by the endpoint.

1.  If the trial certification succeeded, you can proceed to start the real certification as follows:
    
    iex\> SiteEncrypt.force\_certify(MySystemWeb.Endpoint)
    

Unlike the trial certification, this function will go to the CA as configured by the `certification/0` callback in the endpoint. The key and the certificate files will be stored on the disk, and the site will immediately used them. Therefore, if this function succeeds, you can visit your site via HTTPS.

1.  If all went well, remove the `:mode` setting from the `certification/0` callback and redeploy your system.

**Note**: be careful not to invoke these functions too frequently, because you might trip some rate limit on Let's Encrypt. See here for more details.

License
-------

MIT
