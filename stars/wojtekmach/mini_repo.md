---
project: mini_repo
stars: 194
description: MiniRepo allows self-hosting of Hex packages.
url: https://github.com/wojtekmach/mini_repo
---

MiniRepo
========

⚠️ MiniRepo is deprecated in favour of an offical self-hosting solution from the Hex team, `mix hex.registry build` (available from Hex v0.21+).

MiniRepo allows self-hosting of Hex packages.

Features:

-   Pluggable storage. MiniRepo ships with following adapters:
    
    -   Local filesystem
        
    -   S3
        
-   Mirroring
    
-   Publishing packages via HTTP API
    
-   Hosting of multiple repositories and mirrors
    
    MiniRepo exposes following URLs for API and repository access:
    
    -   http://some\_url/api/
        
    -   http://some\_url/repos/
        

Learn more about Hex specifications here.

Setup
-----

Clone and install dependencies:

```
git clone git@github.com:wojtekmach/mini_repo.git
cd mini_repo
mix deps.get
```

Start a development server:

```
iex -S mix
```

By default, the development server is configured with two repositories:

-   `test_repo` is a custom repository
    
-   `hexpm_mirror` is a mirror of the official Hex.pm repository, configured to only fetch package `decimal`.
    

Both repositories are configured to store files locally. See `config/dev.exs` for more information.

Make sure to also read "Deployment with releases" section below.

Usage
-----

Once you have the MiniRepo server running, here is how you can use it with Mix or Rebar3.

### Usage with Mix

Let's create a new package and publish it to our `test_repo` repository:

```
$ mix new foo
$ cd foo
```

Make following changes to that package's `mix.exs`:

  def project() do
    \[
      app: :foo,
      version: "0.1.0",
      elixir: "~> 1.9",
      start\_permanent: Mix.env() \== :prod,
      deps: deps(),
      description: "Some description",
      package: package(),
      hex: hex(),
    \]
  end

  defp deps() do
    \[\]
  end

  defp package() do
    \[
      licenses: \["Apache-2.0"\],
      links: %{}
    \]
  end

  defp hex() do
    \[
      api\_url: "http://localhost:4000/api/repos/test\_repo",
      \# make sure to change it, see \`auth\_token\` in config/releases.exs
      api\_key: "secret"
    \]
  end

Now publish the package:

```
$ mix hex.publish package
```

Finally, let's use this package from another project.

First, configure Hex to use the custom repository:

```
$ cd /path/to/mini_repo
$ mix hex.repo add test_repo http://localhost:4000/repos/test_repo --public-key priv/test_repo_public.pem
```

Now, create a new Mix project:

```
$ mix new bar
$ cd bar
```

And configure the dependency, note the `repo` configuration option.

  defp deps() do
    \[
      {:foo, "~> 0.1", repo: "test\_repo"}
    \]
  end

Since the development server includes a `hexpm_mirror` repo, let's try that too:

```
$ HEX_MIRROR_URL=http://localhost:4000/repos/hexpm_mirror mix hex.package fetch decimal 1.8.0
```

See Hex.pm guide on publishing packages and Hex docs, in particular `mix help hex.config`, for more information.

### Usage with Rebar3

Let's create a new package and publish it to our `test_repo` repository:

```
$ rebar3 new lib baz
$ cd baz
```

Now, let's configure Rebar3 to use our custom repo, put the following into your global rebar3 configuration:

%% ~/.config/rebar3/rebar.config
{plugins, \[rebar3\_hex\]}.
{hex, \[
  {repos, \[
    #{
      name \=> <<"test\_repo"\>>,

      %% make sure to change it, see \`auth\_token\` in config/releases.exs
      api\_key \=> <<"secret"\>>,
      api\_url \=> <<"http://localhost:4000/api/repos/test\_repo"\>>,
      api\_repository \=> undefined,

      repo\_url \=> <<"http://localhost:4000/repos/test\_repo"\>>,
      repo\_organization \=> undefined,
      repo\_public\_key \=> <<"\-----BEGIN RSA PUBLIC KEY-----
MIIBCgKCAQEAxfUmzcCs9+rHvGiTvethBN0dVNgvJKss2z48mMjgOd9owiBMvHWQ
wBSncGgZHbahVJbz3bRfvKVAi1mgWx1233MlWJHR+qc2iQyXKW35cYsUOJtGAgmM
10kLvKhxKXdMgJASb02logFVuz2Ov3a/blHGDSqH6HCXok7tUY6ZwRIv7+zsQTga
ttpaLngmgGA2vPUQjUHIDSR6+j65szripj7BLyzqfncCcZK0nKYalBkwcXbrOln0
FucLkxYiy1saxxJlfHQ9W7j9YmjbZDDmSgnbJfi2/WpOgclptthYNA9+OYbz9peD
X9EXqozUvq0yXdgoqOnUfzYTrFOHg/MIHQIDAQAB
\-----END RSA PUBLIC KEY-----"\>>
    }
  \]}
\]}.

And publish the package specifying the repo:

```
$ rebar3 hex publish -r test_repo
```

Finally, let's use this package from another project:

```
$ rebar3 new lib qux
$ cd qux
```

Add the dependency to the project's `rebar.config`:

```
{erl_opts, [debug_info]}.
{deps, [
  {baz, "0.1.0"}
]}.
```

And make sure the dependecy was correctly resolved:

```
$ rebar3 deps
(...)
===> Verifying dependencies...
baz (package 0.1.0)
```

See Hex.pm guide on publishing packages with Rebar3 and Rebar3 docs for more information.

### Deployment with releases

It's recommended to deploy MiniRepo with Elixir releases.

Let's now assemble the release locally:

```
$ MIX_ENV=prod mix release
* assembling mini_repo-0.1.0 on MIX_ENV=prod
(...)
```

And start it:

```
PORT=4000 \
MINI_REPO_URL=http://localhost:4000 \
MINI_REPO_AUTH_TOKEN=secret \
_build/prod/rel/mini_repo/bin/mini_repo start
```

As you can see, some configuration can be set by adjusting system environment variables, see `config/releases.exs`

**Warning**: MiniRepo by default has very basic authorization uses pre-generated public/private keys for repository signing. Make sure to generate your own public/private keys and consider adding authentication that makes sense in your organization.

Also, see `mix help release` for general information on Elixir releases.

More information
----------------

See following modules documentation to learn more about given feature:

-   `MiniRepo.Store.Local`
    
-   `MiniRepo.Store.S3`
    
-   `MiniRepo.Mirror`
    

Contributing
------------

The goal of MiniRepo is to provide a minimal server that implements Hex specifications. Why minimal? By keeping the project focused on bare minimum we hope it's easy to understand and serves as a good starting point for a more complete solution that makes sense in a given organization. A production grade system should include infrastructure for monitoring, backups, SSL, and more, not to mention features like user management, SSO and such, but that's out of the scope of MiniRepo project.

We welcome anyone to contribute to the project, especially around documentation and guides, but features specific to narrow set of users likely won't be accepted. For a complete and production-grade implementation see source code of Hex.pm, however keep in mind it's optimised for running the public registry for the community and thus have different features and constraints than a self-hosted solution might have.

License
-------

Copyright (c) 2019 Plataformatec Copyright (c) 2020 Dashbit

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

```
http://www.apache.org/licenses/LICENSE-2.0
```

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
