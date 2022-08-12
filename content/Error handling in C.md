---
title: "Error handling in C"
---

Important things - `errno` and `perror`. `errno` is an int in `errno.h`, and it's set to various error codes if some function exits with an error. It's zero otherwise. Check this out:
```C
if (errno != 0) {
	perror("strtol");
	exit(EXIT_FAULIRE);
}
```

You can find examples in the man pages of `strtol`, `pipe`, etc.

Using error codes is... Not that convenient. In [[Go]] it's cooler!
