---
title: "UNIX (Linux) processes"
---

All info about running processes is in `/proc`. See [this comic](https://wizardzines.com/comics/proc/).

### Related
- [[Race condition]]
- [[Managing processes in C]]

### Useful commands
- [[pstree]]
- `kill PID1 PID2 ...` - kill 'em!
- `pidof <program-name>` - get process ID
- `killall/pkill` - kill all processes by name ([more info](https://unix.stackexchange.com/questions/91527))
- `bg`, `fg` - bring to background/foreground
- `jobs` - show background processes (I think?)
- `CTRL + Z` - pauses the active process. Enter `bg` to continue its running in the background.
- `disown -h` - to make sure command will run after you close the ssh session.

### Process termination
[This comic](https://wizardzines.com/comics/kill/) :)

The signals to send are `SIGINT`, `SIGTERM`, `SIGKILL`. Maybe there are others. See [[How Linux Signals Work - SIGINT, SIGTERM and SIGKILL]]. See also [How to Kill a Process in Linux with Kill, Pkill and Killall | PhoenixNAP KB](https://phoenixnap.com/kb/how-to-kill-a-process-in-linux).

`SIGKILL` will always work and shut the process abruptly. If it doesn't work - the operating system has failed! `SIGTERM` (and `SIGINT`) may be handled by the program itself and thus may not work if the process is hanging.

If a program is hanging, `killall [-9 | -KILL] <program-name>` should do the thing. If you don't know the name, you can look it up with `top` or something.
