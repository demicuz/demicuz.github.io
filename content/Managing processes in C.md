---
title: "Managing processes in C"
date: "2022-08-14"
lastmod: "2022-08-14"
---

[[UNIX processes]]
### Functions
`sigsuspend(const sigset_t *mask)` - tbd
`fork()`, `wait()`, etc. - see [[pipex]]

### Notes
There's a catch when `fork()`ing after `printf()`. The output from `printf()` may be stored in a buffer, and that buffer gets copied after `fork()`. So the buffer may be flushed twice (and printing something twice). Example:

```C
#include <unistd.h>
#include <stdio.h>
#include <sys/wait.h>

int main(int argc, char const *argv[])
{
	printf("Wat");
	int id = fork();
	if (id != 0)
		wait(NULL);
	return 0;
}
```

Output:
```
WatWat
```

It doesn't happen if you call `exec()` after `fork()` though, because `exec()` starts with fresh stdio buffers. More [here](https://stackoverflow.com/questions/5422831).

### Links
- [Unix Processes in C - YouTube](https://www.youtube.com/playlist?list=PLfqABt5AS4FkW5mOn2Tn9ZZLLDwA3kZUY)
