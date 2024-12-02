---
project: furlex
stars: 45
description: A structured data extraction tool written in Elixir
url: https://github.com/claytongentry/furlex
---

Furlex
======

Furlex is a structured data extraction tool written in Elixir.

It currently supports unfurling oEmbed, Twitter Card, Facebook Open Graph, JSON-LD and plain ole' HTML `<meta />` data out of any url you supply.

Installation
------------

Add `:furlex` to your list of dependencies in `mix.exs`:

def deps do
  \[{:furlex, "~> 0.5.0"}\]
end

Then run `$ mix deps.get`. Also add `:furlex` to your applications list:

def application do
  \[applications: \[:furlex\]\]
end

Jason is the default json library in Furlex. You can however configure Furlex to use another library. For example:

config :furlex, :json\_library, YourLibraryOfChoice

Usage
-----

To unfurl a url, simply pass it to `Furlex.unfurl/1`

iex(1)\> Furlex.unfurl "https://www.youtube.com/watch?v=Gh6H7Md\_L2k"
{:ok,
 %Furlex{canonical\_url: "https://www.youtube.com/watch?v=Gh6H7Md\_L2k",
  facebook: %{"fb:app\_id" \=> "87741124305",
    "og:description" \=> "Watch the full episode: https://www.thisoldhouse.com/watch/ask-toh-future-house-offerman Ask This Old House host Kevin O’Connor visits Nick Offerman in Los A...",
    "og:image" \=> "https://i.ytimg.com/vi/Gh6H7Md\_L2k/maxresdefault.jpg",
    "og:site\_name" \=> "YouTube",
    "og:title" \=> "Touring Nick Offerman’s Wood Shop", "og:type" \=> "video",
    "og:url" \=> "https://www.youtube.com/watch?v=Gh6H7Md\_L2k",
    "og:video:height" \=> \["720", "720"\],
    "og:video:secure\_url" \=> \["https://www.youtube.com/embed/Gh6H7Md\_L2k",
     "https://www.youtube.com/v/Gh6H7Md\_L2k?version=3&autohide=1"\],
    "og:video:type" \=> \["text/html", "application/x-shockwave-flash"\],
    "og:video:url" \=> \["https://www.youtube.com/embed/Gh6H7Md\_L2k",
     "http://www.youtube.com/v/Gh6H7Md\_L2k?version=3&autohide=1"\],
    "og:video:width" \=> \["1280", "1280"\]},
  json\_ld: \[%{"@context" \=> "http://schema.org", "@type" \=> "BreadcrumbList",
     "itemListElement" \=> \[%{"@type" \=> "ListItem",
        "item" \=> %{"@id" \=> "http://www.youtube.com/user/thisoldhouse",
          "name" \=> "This Old House"}, "position" \=> 1}\]}\],
  oembed: %{"author\_name" \=> "This Old House",
    "author\_url" \=> "https://www.youtube.com/user/thisoldhouse",
    "height" \=> 270,
    "html" \=> "<iframe width=\\"480\\" height=\\"270\\" src=\\"https://www.youtube.com/embed/Gh6H7Md\_L2k?feature=oembed\\" frameborder=\\"0\\" gesture=\\"media\\" allow=\\"encrypted-media\\" allowfullscreen></iframe>",
    "provider\_name" \=> "YouTube", "provider\_url" \=> "https://www.youtube.com/",
    "thumbnail\_height" \=> 360,
    "thumbnail\_url" \=> "https://i.ytimg.com/vi/Gh6H7Md\_L2k/hqdefault.jpg",
    "thumbnail\_width" \=> 480, "title" \=> "Touring Nick Offerman’s Wood Shop",
    "type" \=> "video", "version" \=> "1.0", "width" \=> 480},
  other: %{"description" \=> "Watch the full episode: https://www.thisoldhouse.com/watch/ask-toh-future-house-offerman Ask This Old House host Kevin O’Connor visits Nick Offerman in Los A...",
    "keywords" \=> "this old house, how-to, home improvement, Episode, TV Show, DIY, Ask This Old House, Nick Offerman, Kevin O'Connor, woodworking, wood shop",
    "theme-color" \=> "#ff0000",
    "title" \=> "Touring Nick Offerman’s Wood Shop"},
  status\_code: 200,
  twitter: %{"twitter:app:id:googleplay" \=> "com.google.android.youtube",
    "twitter:app:id:ipad" \=> "544007664",
    "twitter:app:id:iphone" \=> "544007664",
    "twitter:app:name:googleplay" \=> "YouTube",
    "twitter:app:name:ipad" \=> "YouTube",
    "twitter:app:name:iphone" \=> "YouTube",
    "twitter:app:url:googleplay" \=> "https://www.youtube.com/watch?v=Gh6H7Md\_L2k",
    "twitter:app:url:ipad" \=> "vnd.youtube://www.youtube.com/watch?v=Gh6H7Md\_L2k&feature=applinks",
    "twitter:app:url:iphone" \=> "vnd.youtube://www.youtube.com/watch?v=Gh6H7Md\_L2k&feature=applinks",
    "twitter:card" \=> "player",
    "twitter:description" \=> "Watch the full episode: https://www.thisoldhouse.com/watch/ask-toh-future-house-offerman Ask This Old House host Kevin O’Connor visits Nick Offerman in Los A...",
    "twitter:image" \=> "https://i.ytimg.com/vi/Gh6H7Md\_L2k/maxresdefault.jpg",
    "twitter:player" \=> "https://www.youtube.com/embed/Gh6H7Md\_L2k",
    "twitter:player:height" \=> "720", "twitter:player:width" \=> "1280",
    "twitter:site" \=> "@youtube",
    "twitter:title" \=> "Touring Nick Offerman’s Wood Shop",
    "twitter:url" \=> "https://www.youtube.com/watch?v=Gh6H7Md\_L2k"}}}

Configuration
-------------

Furlex accepts a few optional configuration parameters.

You may configure additional tags to capture under the Facebook OpenGraph and TwitterCard parsers.

config :furlex, Furlex.Parser.Facebook,
  tags: ~w(my:custom:facebook:tag another:custom:facebook:tag)

config :furlex, Furlex.Parser.Twitter,
  tags: ~w(my:custom:twitter:tag)

You may also configure the depth of the resulting Furlex map with a `:group_keys?` boolean.

config :furlex, group\_keys?: true

If this option is set to false or unconfigured, Furlex will return values mapped directly beneath OpenGraph and TwitterCard keys, i.e.

%Furlex{twitter: %{
  "twitter:app:id:googleplay" \=> "com.google.android.youtube",
  "twitter:app:id:ipad"       \=> "544007664",
  "twitter:app:id:iphone"     \=> "544007664"
}}

If true, Furlex will return values grouped into colon-delimited map structures, i.e.

%Furlex{twitter: %{
  "twitter" \=> %{
    "app" \=> %{
      "id" \=> %{
        "googleplay" \=> "com.google.android.youtube",
        "ipad"       \=> "544007664",
        "iphone"     \=> "544007664"
      }
    }
  }
}}

License
-------

Copyright 2017 Clayton Gentry

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

```
http://www.apache.org/licenses/LICENSE-2.0`
```

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
