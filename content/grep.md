---
title: "grep"
date: "2023-01-15"
lastmod: "2023-01-15"
---

- `-E` - use extended regular expressions, whatever that means
- `-i` - case-insensitive
- `-v` - inVert matches (return those that don't match)
- `-r` - recursive search. Search all files, for example.
- `-n` - print line numers

Search for whole words with `grep "\bmyword\b"`. `\b` means boundaries.

todo something strange happening when using with `watch`. It ignores spaces.

### See also
- [[ripgrep]]
- [[ag]] ([link](https://github.com/ggreer/the_silver_searcher))