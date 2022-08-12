---
title: "LLDB"
---

A debugger! It has some cool features that GDB probably doesn't have. Like in gui mode you can use arrows to expand/collapse nested structures! But gui in LLDB is mostly a hacked around thing. You can't even run commands within it.

### General
- `lldb -- prog arg1 arg2` - passing arguments (or even without `--`, dunno)
- `b` to set breakpoints; use `help b` for more info
- `run` or `r` - run!
- `n`, `s` - next, step into
- `c` for `continue`
- `frame variable` or `fr v` - print variables visible in the current frame
- `frame select` or `fr s` - print last selected frame
- `frame select 2` or `f 2` - select frames (`0` is current frame, `1` is next in the call stack and so on)
- `bt` for backtrace
- `gui` or `gu` or `ui` for gui

##### Watchpoints
Prints the variable when it's accessed or changed.
- `watchpoint set variable globalVar`
- `watchpoint set variable -w read | write | read_write globalVar`
- `w s v d.memberVar` - for local variables. Also shorter commands

##### Terminating
- `kill` - kill the process
- `quit` or `q` or `CTRLD + D` - quit

### Links
- [Debugging C/C++ with LLDB Tutorial - YouTube](https://www.youtube.com/watch?v=2GV0K9Y2MKA&t=1914s)
- [GDB to LLDB command map — The LLDB Debugger](https://lldb.llvm.org/use/map.html)
- [PDR: LLDB Tutorial](https://aaronbloomfield.github.io/pdr/tutorials/02-lldb/index.html)
