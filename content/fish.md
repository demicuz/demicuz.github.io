---
title: "fish"
date: "2022-08-15"
lastmod: "2022-08-15"
---

A shell!

#todo - are fish completions lazy-loaded?

### See also
- [[Terminal tools]]

### Notes
To accept the autosuggestion, hit `→` (right arrow) or `Ctrl + F`. To accept a single word of the autosuggestion, `Alt + →` (right arrow) or `Alt + F`.

Navigating folders:
- `dirh` prints the history
- `cdh` displays a prompt to quickly navigate the history
- `prevd` moves backward through the history. It is bound to Alt+←
- `nextd` moves forward through the history. It is bound to Alt+→

### Plugins
Install fisher, a plugin manager. It's *the only* way to manage plugins. Don't even touch oh-my-fish.

### Variables
To make environment [variables](https://fishshell.com/docs/current/language.html#variables) available to other programs (and shells) that `fish` launches, you should [export](https://fishshell.com/docs/current/language.html#variables-export) them.

### Links
- [jorgebucaran/awsm.fish](https://github.com/jorgebucaran/awsm.fish)
