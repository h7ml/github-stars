---
project: webpack-retry-chunk-load-plugin
stars: 247
description: A webpack plugin to retry loading of chunks that failed to load
url: https://github.com/mattlewis92/webpack-retry-chunk-load-plugin
---

webpack-retry-chunk-load-plugin
===============================

A webpack plugin to retry loading of async chunks that failed to load

Usage
-----

// webpack.config.js
const { RetryChunkLoadPlugin } \= require('webpack-retry-chunk-load-plugin');

plugins: \[
  new RetryChunkLoadPlugin({
    // optional stringified function to get the cache busting query string appended to the script src
    // if not set will default to appending the string \`?cache-bust=true\`
    cacheBust: \`function() {
      return Date.now();
    }\`,
    // optional value to set the amount of time in milliseconds before trying to load the chunk again. Default is 0
    // if string, value must be code to generate a delay value. Receives retryCount as argument 
    // e.g. \`function(retryAttempt) { return retryAttempt \* 1000 }\`
    retryDelay: 3000,
    // optional value to set the maximum number of retries to load the chunk. Default is 1
    maxRetries: 5,
    // optional list of chunks to which retry script should be injected
    // if not set will add retry script to all chunks that have webpack script loading
    chunks: \['chunkName'\],
    // optional code to be executed in the browser context if after all retries chunk is not loaded.
    // if not set - nothing will happen and error will be returned to the chunk loader.
    lastResortScript: "window.location.href='/500.html';",
  }),
\];

### Webpack compatibility

Webpack version

webpack-retry-chunk-load-plugin version

5.x

2.x

4.x

1.x

### angular cli

To use this with the angular CLI you can use the fantastic `angular-builders` project to extend the built in webpack config

License
-------

MIT
