---
title: "minitalk"
---

This project is about [[Managing processes in C]] using [[UNIX signals]].

### Notes
Seems like it's better to use `sigaction` instead of `signal` ([source](https://stackoverflow.com/questions/6729147/)). It's behavior is more rigorously defined and it also can receive PID of a sender process (I think). It's also more portable.

See also `getpid()`.

[Signal basics](https://towardsdatascience.com/signals-in-linux-b34cea8c5791)
[Minitalk wiki](https://github.com/mlanca-c/Minitalk/wiki)

It's possible for a process to send signals to itself. Weird.

### To dispatch
- https://stackoverflow.com/questions/48409070/difference-between-a-process-signal-mask-blocked-signal-set-and-a-blocked-sign
- [pause vs sigsuspend](https://stackoverflow.com/questions/6328055/whats-the-problem-of-pause-at-all)

### Links
https://github.com/mlanca-c/Minitalk
