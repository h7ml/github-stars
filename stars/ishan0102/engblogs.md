---
project: engblogs
stars: 166
description: learn from your favorite tech companies
url: https://github.com/ishan0102/engblogs
---

engblogs.dev
============

learn from your favorite tech companies

what is this
------------

you could use an RSS reader but what's the fun in that? I run a cronjob that scrapes the RSS feeds of the companies listed below, calls gpt-3.5 to generate a short summary, and stores the data in supabase. there's a little next.js app hosted on vercel that lets you browse the data.

get the data
------------

if you're interested in using this data for training an LLM or building your own project, be my guest. just credit my github please :) you can run this command to get the posts data:

curl 'https://corpcplcbbbchszhzofk.supabase.co/rest/v1/posts?select=\*' \\
-H "apikey: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImNvcnBjcGxjYmJiY2hzemh6b2ZrIiwicm9sZSI6ImFub24iLCJpYXQiOjE2ODYyNzU2MzgsImV4cCI6MjAwMTg1MTYzOH0.c5ALD\_rsD48EcZTrEeHZqfTCLf5L61IIlSgxuH4PVHI" \\
-H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImNvcnBjcGxjYmJiY2hzemh6b2ZrIiwicm9sZSI6ImFub24iLCJpYXQiOjE2ODYyNzU2MzgsImV4cCI6MjAwMTg1MTYzOH0.c5ALD\_rsD48EcZTrEeHZqfTCLf5L61IIlSgxuH4PVHI"

this will return some JSON

cron
----

for my own reference, this is the cron command that ended up working:

0 \* \* \* \* ~/documents/engblogs/scripts/run.sh \>/dev/null 2>&1

it runs once per hour

contribute
----------

please do! run `npm run dev` in the `client` folder to start the webapp. the `scripts` folder contains the code to fetch data from RSS feeds, which you can repurpose for any RSS feeds you want.

blog links
----------

Company

Link

AWS ML

https://aws.amazon.com/blogs/machine-learning/feed/

Airbnb

https://medium.com/feed/airbnb-engineering

Apple ML

https://machinelearning.apple.com/rss.xml

Berkeley AI

https://bair.berkeley.edu/blog/feed.xml

Chromium

http://blog.chromium.org/feeds/posts/default

Cohere AI

https://txt.cohere.ai/rss/

Databricks

https://www.databricks.com/blog/feed

DeepMind

https://www.deepmind.com/blog/rss.xml

DoorDash

https://doordash.engineering/category/backend/feed/

DoorDash ML

https://doordash.engineering/category/data-science-and-machine-learning/feed/

Dropbox

https://dropbox.tech/feed

Duolingo

https://blog.duolingo.com/rss/

GitHub

https://github.blog/engineering.atom

Google AI

https://feeds.feedburner.com/blogspot/gJZg

Hudson River Trading

https://www.hudsonrivertrading.com/feed/

Ink and Switch

https://www.inkandswitch.com/index.xml

Instacart

https://tech.instacart.com/feed

Instagram

https://instagram-engineering.com/feed

Jane Street

https://blog.janestreet.com/feed.xml

LinkedIn

https://engineering.linkedin.com/blog.rss.html

Lyft

https://eng.lyft.com/feed

MIT AI

https://news.mit.edu/rss/topic/artificial-intelligence2

Meta

https://engineering.fb.com/feed

Microsoft AI

https://blogs.microsoft.com/ai/feed

Modular AI

https://www.modular.com/blog/rss.xml

MongoDB

https://www.mongodb.com/blog/rss

Netflix

https://netflixtechblog.com/feed

OpenAI

https://openai.com/blog/rss

Pinterest

https://medium.com/feed/@Pinterest\_Engineering

Roblox

https://corp.roblox.com/feed/

Salesforce

https://engineering.salesforce.com/feed

Snorkel AI

https://snorkel.ai/feed

SoundCloud

https://developers.soundcloud.com/blog/blog.rss

Spotify

https://engineering.atspotify.com/feed

Stability AI

https://stability.ai/blog?format=rss

Stanford AI

https://ai.stanford.edu/blog/feed.xml

Stripe

https://stripe.com/blog/feed.rss

The New York Times

http://open.blogs.nytimes.com/feed/

Two Sigma

https://www.twosigma.com/topic/engineering/feed/

Uber

https://www.uber.com/blog/engineering/rss/
