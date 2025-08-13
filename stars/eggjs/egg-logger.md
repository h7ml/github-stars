---
project: egg-logger
stars: 151
description: Egg logger
url: https://github.com/eggjs/egg-logger
---

egg-logger
==========

Egg logger.

Including two base class, `Logger` and `Transport`:

-   Transport: Save log to file, stdout/stderr and network.
-   Logger: A logger can contains multi transports.

* * *

Install
-------

$ npm i egg-logger

Usage
-----

Create a `Logger` and add a file `Transport`.

const Logger \= require('egg-logger').Logger;
const FileTransport \= require('egg-logger').FileTransport;
const ConsoleTransport \= require('egg-logger').ConsoleTransport;

const logger \= new Logger();
logger.set('file', new FileTransport({
  file: '/path/to/file',
  level: 'INFO',
}));
logger.set('console', new ConsoleTransport({
  level: 'DEBUG',
}));
logger.debug('debug foo'); // only output to stdout
logger.info('info foo');
logger.warn('warn foo');
logger.error(new Error('error foo'));

### Enable / Disable Transport

logger.disable('file');
logger.info('info'); // output nothing
logger.enable('file');
logger.info('info'); // output 'info' string

### Duplicate

Duplicate error log to other logger.

Accept an `options.excludes` to special whether excludes some tranports.

logger.duplicate('error', errorLogger, { excludes: \[ 'console' \]});
logger.error(new Error('print to errorLogger')); // will additional call \`errorLogger.error\`

### Redirect

Redirect special level log to other logger.

oneLogger.redirect('debug', debugLogger); // all debug level logs of \`oneLogger\` will delegate to debugLogger

### Reload

logger.reload(); // will close the exists write stream and create a new one.

### Custom Transport

You can make your own `Transport` for logging，e.g.: send log to your logging server.

const urllib \= require('urllib');
const Transport \= require('egg-logger').Transport;

class UrllibTransport extends Transport {

  log(level, args, meta) {
    const msg \= super.log(level, args, meta);
    return urllib.request('url?msg=' + msg);
  }
}

const logger \= new Logger();
logger.set('remote', new UrllibTransport({
  level: 'DEBUG',
}));
logger.info('info');

Console logger level
--------------------

set environment NODE\_CONSOLE\_LOGGRE\_LEVEL = 'INFO' | 'WARN' | 'ERROR'

License
-------

MIT

Contributors
------------

Made with contributors-img.
