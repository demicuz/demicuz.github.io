---
title: "HUGO"
tags: [tool, web]
---

[This](https://discourse.gohugo.io/t/markdown-not-adding-a-br-when-adding-a-line-break/28263/13) seems to enable rendering of single line breaks:
```toml
# config.toml
[markup.goldmark.renderer]
hardWraps = true
```
