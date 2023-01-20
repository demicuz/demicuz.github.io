---
title: "Keyboard key remapping"
date: "2022-10-18"
lastmod: "2022-10-18"
---

- [[Keyboards]]

You can remap Caps Lock either to Esc, or to Ctrl. I don't know yet which is better. Or it can be [both](https://www.reddit.com/r/vim/comments/wmtjfj/comment/ik1n6ll/).

If you use [[Vim]], you probably need this. [[KDE]] can do it through its settings, but it somehow sucks. Weird bugs when remapping Ctrl to Caps Lock.

UPD: remapping Caps to Ctrl with *any* program results in glitches. I'm sure it's KDE's fault.

### Links
- [sezanzeb/input-remapper](https://github.com/sezanzeb/input-remapper) - works fine if you want to remap Caps to Esc. With Ctrl I have glitches on KDE.
- [rvaiya/keyd: A key remapping daemon for linux.](https://github.com/rvaiya/keyd) - tried, lags af
- [interception / linux / plugins / caps2esc](https://gitlab.com/interception/linux/plugins/caps2esc) - lags too. Maybe bc of KDE
- `setxkbmap -option caps:escape` - dunno if it works, and how exactly, if it does. Ancient technology, avoid if possible.
