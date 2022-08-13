---
title: "Mutex"
---

A special object that controls thread access to shared resources to prevent [[Race condition|data race]]. Only one process at a time is allowed to read/write. Mutexes have some downsides, see.

### Notes
If one process only writes to some variable, and another only reads from it, you don't need to use mutex for this. Because only read and only write are atomic operations.

### Links
- [How does a mutex work? What does it cost?](https://mortoray.com/2019/02/20/how-does-a-mutex-work-what-does-it-cost/)
- [linux - How pthread_mutex_lock is implemented](https://stackoverflow.com/questions/5095781)
- [Thread locks implementation](https://pages.cs.wisc.edu/%7Eremzi/OSTEP/threads-locks.pdf)
- [5 Big Fat Reasons Why Mutexes Suck Big Time](https://accu.org/journals/overload/27/149/ignatchenko_2623/)
- [Is it safe to concurrently read from shared memory?](https://stackoverflow.com/questions/45053875)

### Related
- [[Spinlock]]
