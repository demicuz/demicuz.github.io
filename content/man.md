---
title: "man"
date: "2022-10-27"
lastmod: "2022-10-27"
---

Yes. `man`. The holy `man`.

- [How can I search within a manpage?](https://askubuntu.com/questions/20752)
	- `/` to search, `N` and `Shift + N` to skip between results

Use `/\bword\b` to search exactly for `word`. `b` means boundaries.

Place your man pages in `/usr/local/share/man` (on Ubuntu, at least).

### Limit man width
I have a [gist](https://gist.github.com/demicuz/0d434a27300149d529abd4220b7fd255) for fish shell.

### Using VIM as a pager
I have a [gist](https://gist.github.com/demicuz/94ee8ddccfc540342c10a4444a80761d).

### Add custom man pages
In `$HOME/.local/share/man`. E.g. `$HOME/.local/share/man/man1/bat.1`.

### Links
- [How do I manually install a man page file?](https://askubuntu.com/questions/244809)
