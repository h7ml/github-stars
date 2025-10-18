---
project: textfilter
stars: 2103
description: 敏感词过滤的几种实现+某1w词敏感词库
url: https://github.com/observerss/textfilter
---

很短但是觉得挺有用的东东
所以单独立了个项目备份一下

USAGE:

    >>> f = DFAFilter()
    >>> f.add("sexy")
    >>> f.filter("hello sexy baby")
    hello \*\*\*\* baby
