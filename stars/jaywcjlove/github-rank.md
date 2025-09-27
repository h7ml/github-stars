---
project: github-rank
stars: 2257
description: 🕷️Github China/Global User Ranking, Global Warehouse Star Ranking (Github Action is automatically updated daily).
url: https://github.com/jaywcjlove/github-rank
---

Special thanks to:  
You’re welcome to advertise here :)  
  
Using my app is also a way to support me:  
  
  

* * *

\[中文\] Preview: Github | Gitee | UNPKG | Githack | Statically | Netlify

Github global/Chinese user rankings, global repositories Star rankings, page data generated through Github API v3, ranking preview.

-   Github **Global** User Followers Ranking Preview
-   Github **China** User Followers Ranking Preview
-   Github **Global** Org User Followers Ranking Preview
-   Github Global repositories Star Most Ranking Preview
-   Github community trend list daily, weekly, monthly preview **`daily`** **`weekly`** **`monthly`**

Released on `npm` from `April 20, 2019,` the version number is defined by `year`, `month`, and `day`, such as: `v19.4.20`.

Warning

Due to the large number of projects, the free quota is insufficient, resulting in some charges. We have now adjusted it to run every `7` days to save costs.

Now it can be updated automatically every day, using GitHub Actions Workflows to trigger the GitHub workflow every day at 00:00 (8:00 am Beijing time) through the timer, automatically crawl the data, submit the generated web page to the gh-pages branch, and Automatically publish npm version, really fragrant! !

Update date: 2025-09-22 00:53:53

Plug-in Usage
-------------

npm install @wcj/github-rank --save-dev

Users can obtain ranking data by importing data, or directly access the user leaderboard through UNPKG.

import users from '@wcj/github-rank';
import repos from '@wcj/github-rank/dist/repos.json';
import trendingDaily from '@wcj/github-rank/dist/trending-daily.json';
import trendingWeekly from '@wcj/github-rank/dist/trending-weekly.json';
import trendingMonthly from '@wcj/github-rank/dist/trending-monthly.json';

import users from '@wcj/github-rank';

// By default users outputs the following data:
\[
  {
    "login": "jaywcjlove",
    "id": 1680273,
    "node\_id": "MDQ6VXNlcjE2ODAyNzM=",
    "avatar\_url": "https://avatars1.githubusercontent.com/u/1680273?v=4",
    "gravatar\_id": "",
    "url": "https://api.github.com/users/jaywcjlove",
    "html\_url": "https://github.com/jaywcjlove",
    "followers\_url": "https://api.github.com/users/jaywcjlove/followers",
    "following\_url": "https://api.github.com/users/jaywcjlove/following{/other\_user}",
    "gists\_url": "https://api.github.com/users/jaywcjlove/gists{/gist\_id}",
    "starred\_url": "https://api.github.com/users/jaywcjlove/starred{/owner}{/repo}",
    "subscriptions\_url": "https://api.github.com/users/jaywcjlove/subscriptions",
    "organizations\_url": "https://api.github.com/users/jaywcjlove/orgs",
    "repos\_url": "https://api.github.com/users/jaywcjlove/repos",
    "events\_url": "https://api.github.com/users/jaywcjlove/events{/privacy}",
    "received\_events\_url": "https://api.github.com/users/jaywcjlove/received\_events",
    "type": "User",
    "site\_admin": false,
    "score": 1,
    "rank": 117,
    "name": "小弟调调™",
    "company": "ʕ•̫͡•ʔ-̫͡-ʕ•͓͡•ʔ-̫͡-ʔ",
    "blog": "http://wangchujiang.com",
    "location": "Shanghai, China",
    "email": "wowohoo@qq.com",
    "hireable": true,
    "bio": "(͡·̮̃·̃) 撸码的乐趣 💯 ，“人没了，™代码还在”",
    "public\_repos": 78,
    "public\_gists": 1,
    "followers": 2519,
    "following": 91,
    "created\_at": "2012-04-26T00:30:25Z",
    "updated\_at": "2019-04-12T14:27:54Z"
  }
\]

Development
-----------

$ git clone https://github.com/jaywcjlove/github-rank.git
$ cd github-rank
$ npm install   # Install dependencies
$ npm run build # Compilation output script

Crawlers get data

$ npm run get:trending    # Get trending data
$ npm run get:repos       # Get repos data
$ npm run get:users       # Get users data
$ npm run get:users:china # Get users(china) data

Generate HTML page

$ npm run start

Contributors
------------

As always, thanks to our amazing contributors!

Made with contributors, automatically generated.

License
-------

Licensed under the MIT License.
