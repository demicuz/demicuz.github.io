---
title: "Memory leaks"
date: "2022-08-28"
lastmod: "2022-08-28"
---

### Useful Valgrind flags
- `--leak-check=full`
- `--trace-children=yes`
- `--show-leak-kinds=all`
- `--track-origins=yes`
- `--verbose`
- `--log-file=valgrind-out.txt`

### Calling free() after calling exit()
In short - not needed for individual programs. All modern OS'es recycle memory allocated to a process when it terminates.

> When your program ends, as in this example, all of the resources assigned to your process are simply recycled/torn down by the operating system. In the case of memory, all of the memory pages that are assigned to you are simply marked as "free" and recycled for the use of other processes. Pages are a lower-level concept than what malloc handles - as a result, the specifics of malloc/free are all simply washed away as the whole thing gets cleaned up.
> 
> It's the moral equivalent of, when you're done using your laptop and want to give it to a friend, you don't bother to individually delete each file. You just format the hard drive.

BUT. If you use your program in a library or some other program, you should take care of resources properly. Like, clean up all the memory, close opened files and sockets.

### Links
- [How do I use valgrind to find memory leaks?](https://stackoverflow.com/questions/5134891/) - has some useful advices
- [Still reachable in valgrind](https://stackoverflow.com/questions/4406402)
- [c - Still Reachable Leak detected by Valgrind](https://stackoverflow.com/questions/3840582)
- [When you exit a C application, is the malloc-ed memory automatically freed?](https://stackoverflow.com/questions/2213627)
