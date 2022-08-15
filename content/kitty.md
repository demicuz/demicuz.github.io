---
title: "kitty"
date: "2022-08-15"
lastmod: "2022-08-15"
---

A cool terminal emulator!

**Various:**
- Browse last output: `ctrl+shift+g`
	- Hold `ctrl+shift` and right-click on any command output in the scrollback to view it in a pager
- Browse scrollback: `ctrl+shift+h`
- Jump to the previous/next prompt in the scrollback (`ctrl+shift+z` / `ctrl+shift+x`)

**Tabs:**
- New tab: `ctrl+shift+t`
- Close tab: `ctrl+shift+q`
- Next tab: `ctrl+shift+right`
- Previous tab: `ctrl+shift+left`

**Windows:**
- New window: `ctrl+shift+enter`
- Close window: `ctrl+shift+w`
- Next window: `ctrl+shift+]` or `ctrl+alt+→`
- Previous window: `ctrl+shift+[` or `ctrl+alt+←`

### Notes
It's better to install Kitty in a folder accessible to all users (like `/opt`). And edit `visudo` to preserve `TERMINFO` env variable, because backspace and other keys won't work properly.

`sudo apt install kitty-terminfo` does smth on remote machines(?)

### Links
- Made [Mariana](https://gist.github.com/demicuz/5f17f1a1ae45ad8c0646a691a50c9e33) theme (used [this](https://github.com/nthirtyone/mariana-scheme/blob/master/mariana.theme) as a source, some colors seem to be a bit off). Now using Ayu theme, very cool and good contrast!
