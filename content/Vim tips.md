---
title: "Vim tips"
date: "2022-10-19"
---

A substitution with an empty search pattern replaces matches from the last search. After finding "foo" (`/foo`) in the file, you can replace all occurrences with `:s//bar/`. [Source](https://twitter.com/jkreeftmeijer/status/1072093481068306433).

Neovim stores its data in this directories:
```
~/.config/nvim
~/.local/share/nvim
~/.local/state/nvim
~/.cache/nvim
```

### Links
- [Use NeoVim’s `inccommand` option for live substitutions.](https://twitter.com/jkreeftmeijer/status/1085183780032208897)