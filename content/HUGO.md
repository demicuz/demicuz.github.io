---
title: "HUGO"
tags: [tool, web]
date: "2022-10-15"
lastmod: "2022-10-15"
---
A [[Static site generators|static site generator]].

[This](https://discourse.gohugo.io/t/markdown-not-adding-a-br-when-adding-a-line-break/28263/13) seems to enable rendering of single line breaks:
```toml
# config.toml
[markup.goldmark.renderer]
hardWraps = true
```
