---
title: "libft"
date: "2022-08-24"
lastmod: "2022-08-24"
---

### Notes
Functions working with memory can be faster if the operations are done on word-size blocks at a time rather than bytes. So if I'll ever need a faster implementation, I can explore this further. See [c - Understanding the source code of memcpy() - Stack Overflow](https://stackoverflow.com/questions/17591624/understanding-the-source-code-of-memcpy).

Also somehow `memcpy` behaves like `memmove` on my machine (Kubuntu). Didn't check on iMacs.

### Links
- [Why does strchr take an int for the char to be found?](https://stackoverflow.com/questions/2394011/) - tl;dr: purely historical reasons.