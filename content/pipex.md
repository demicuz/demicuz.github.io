---
title: "pipex"
---

This project is about [[Redirection in Bash]] and piping. We're gonna implement it from scratch in C. [[Managing processes in C]] is also useful here.

### To-do
Look into [implementation by jbelinda](https://projects.intra.42.fr/projects/pipex/projects_users/2468738).

### Testers
- [vfurmane/pipex-tester](https://github.com/vfurmane/pipex-tester)

### Functions
`pid_t fork()`
Creates a child process. Returns 0 to the child process and child's pid to the parent process or -1 on error. [[File descriptor]] table gets inherited, so that you have access to all the open files via the same descriptors. The descriptors are independent (if you close it in one process, it remains open in the other), but file *description* is shared. So operations like `lseek` take effect in both processes.

`int pipe(int pipefd[])`
Creates a pipe. Takes an array of two integers, writes two file descriptors in them. `pipefd[0]` is read, `pipefd[1]` is write. On success, zero is returned. On error, -1 is returned, `errno` is set appropriately, and `pipefd` is left unchanged.

`_exit(status)`
> The basic difference between `exit()` and `_exit()` is that the former performs clean-up related to user-mode constructs in the library, and calls user-supplied cleanup functions, whereas the latter performs only the kernel cleanup for the process.
([source](https://www.unixguide.net/unix/programming/1.1.3.shtml))

See [[#Links]] for more details. In short, child processes should call `_exit()`. But I don't really know if I should use it. The parent process should `wait()`, and this command should also free resources (?).

`pid_t wait(int *wstatus)`
`pid_t waitpid(pid_t pid, int *wstatus, int options)`
From `man 2 wait`:
> All of these system calls are used to wait for state changes in a child of the calling process, and obtain information about the child whose state has changed. A state change is considered to be: the child terminated; the child was stopped by a signal; or the child was resumed by a signal. In the case of a terminated child, performing a wait allows the system to release the resources associated with the child; if a wait is not performed, then the terminated child remains in a "zombie" state.

> The `wait()` system call suspends execution of the calling thread until one of its children terminates.

> If `wstatus` is  not NULL, `wait()` and `waitpid()` store status information in the int to which it points. This integer can be inspected with (...some macros...).

> `wait()`: on success, returns the process ID of the terminated child; on error, -1 is returned.

So it's enough to just call `wait(NULL)` to wait for one of the child processes to finish.

`dup(), dup2()`
Duplicate file descriptors. Useful for piping I/O of another program to a file.
> In general, after a process has had its image swapped out with `exec`, it will have all the open file descriptors it had before `exec`. (Except for those descriptors with the `CLOSE_ON_EXEC` flag set, but ignore that for now). Therefore, if you `dup2` something to `0`, then `wc` will read it. ([Source](https://stackoverflow.com/questions/8860895))

### To-do
- Don't forget to check absolute paths to commands (e.g. `/usr/bin/wc`).
- Should I call `close()` if I call `exit()` anyway?
- How to check for memory leaks in children properly?

### Evaluation
What if some command doesn't exist? Or fails to launch? Or returns an error code? Or crashes?
What if the last argument as a valid command name? What if we launch it multiple times?
Try with `yes | head`.
Try with large files (>64MB).

### Notes
##### Pipes are buffered
Pipes have a write buffer that can fill up. Then it blocks write calls. You should continuously read from a pipe in order for another process to write to it. See [here](https://stackoverflow.com/questions/55257628). On Mac OS and Linux it's probably around 64 megabytes. It can be extended by the system though.

##### Close unused ends of pipes
If a pipe has at least one descriptor referring to its write end, then it remains open. And if some program waits for continuous input, it will keep waiting. So when using `dup2()` to substitute stdin and stdout and then call `exec`, don't forget to close all the fd's.

##### Continuous execution
Continue execution if some command exits improperly or doesn't exist. Much like bash.

### Examples
- [Connecting n commands with pipes in a shell?](https://stackoverflow.com/questions/8082932)

### Links
- [pipes - wizardzines](https://wizardzines.com/comics/pipes/)
- [bash redirects - wizardzines](https://wizardzines.com/comics/redirects/)
- [What is the difference between using _exit() & exit() in a conventional Linux fork-exec?](https://stackoverflow.com/questions/5422831/)
- [Differences between fork and exec](https://stackoverflow.com/questions/1653340)
- [How are pipes implemented in the bash shell?](https://stackoverflow.com/questions/31527077)
- [What happens to malloc'ed memory after exec() changes the program image?](https://stackoverflow.com/questions/5429141)
