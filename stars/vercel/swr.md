---
project: swr
stars: 31794
description: React Hooks for Data Fetching
url: https://github.com/vercel/swr
---

  

Introduction
------------

SWR is a React Hooks library for data fetching.

The name “**SWR**” is derived from `stale-while-revalidate`, a cache invalidation strategy popularized by HTTP RFC 5861. **SWR** first returns the data from cache (stale), then sends the request (revalidate), and finally comes with the up-to-date data again.

With just one hook, you can significantly simplify the data fetching logic in your project. And it also covered in all aspects of speed, correctness, and stability to help you build better experiences:

-   **Fast**, **lightweight** and **reusable** data fetching
-   Transport and protocol agnostic
-   Built-in **cache** and request deduplication
-   **Real-time** experience
-   Revalidation on focus
-   Revalidation on network recovery
-   Polling
-   Pagination and scroll position recovery
-   SSR and SSG
-   Local mutation (Optimistic UI)
-   Built-in smart error retry
-   TypeScript
-   React Suspense
-   React Native

...and a lot more.

With SWR, components will get **a stream of data updates constantly and automatically**. Thus, the UI will be always **fast** and **reactive**.

* * *

**View full documentation and examples on swr.vercel.app.**

  

Quick Start
-----------

import useSWR from 'swr'

function Profile() {
  const { data, error, isLoading } \= useSWR('/api/user', fetcher)

  if (error) return <div\>failed to load</div\>
  if (isLoading) return <div\>loading...</div\>
  return <div\>hello {data.name}!</div\>
}

In this example, the React Hook `useSWR` accepts a `key` and a `fetcher` function. The `key` is a unique identifier of the request, normally the URL of the API. And the `fetcher` accepts `key` as its parameter and returns the data asynchronously.

`useSWR` also returns 3 values: `data`, `isLoading` and `error`. When the request (fetcher) is not yet finished, `data` will be `undefined` and `isLoading` will be `true`. When we get a response, it sets `data` and `error` based on the result of `fetcher`, `isLoading` to false and rerenders the component.

Note that `fetcher` can be any asynchronous function, you can use your favourite data-fetching library to handle that part.

* * *

**View full documentation and examples on swr.vercel.app.**

  

Authors
-------

This library is created by the team behind Next.js, with contributions from our community:

-   Shu Ding (@shuding\_) - Vercel
-   Jiachi Liu (@huozhi) - Vercel
-   Guillermo Rauch (@rauchg) - Vercel
-   Joe Haddad (@timer150) - Vercel
-   Paco Coursey (@pacocoursey) - Vercel

Contributors

Thanks to Ryan Chen for providing the awesome `swr` npm package name!

  

License
-------

The MIT License.
