---
title: "GDB"
date: "2022-08-17"
lastmod: "2022-08-17"
---

### See also
- [[GDB pretty-printing]]
- [[LLDB]]

### General
- Compile with `-g` or `-ggdb` flag to include debug information in the executable
- `gdb --args prog arg1 arg2 arg3` to pass arguments
- Use `start` to execute the program step by step, or `run` to just run
- `next` or `n` - for next instruction. 
- `Enter` to repeat the last command
- `p <variable>` to print variables, `display <variable>` to print it continuously
- `step` or `s` to step into functions. `finish` to finish the stepped-into function
- `backtrace` or `bt` for backtrace
- `ctrl + x, 1` or `tui enable` to enable text text user interface.
- `br` to set breakpoints. `br some_func` or `br some_file.c:42`
- `info args` for info about program arguments, `info breakpoints` for breakpoints
- `set follow-fork-mode child` - follow the forked process instead of parent when using `fork()`
- `set foo=bar` - change variables at runtime! Isn't that awesome? But with great power comes great responsibility
- `call <expr>` - run arbitrary code. Beware of state mutation, as with `set`.

**Misc**
`ctrl + x, o` to switch views (useful in tui mode).
`set print pretty on` - to print structs in a more readable way.
`print *array@size` to print arrays.

### Useful
- [gdbgui](https://www.gdbgui.com/)
- [voltron: A hacky debugger UI for hackers](https://github.com/snare/voltron)
- [Debugging child process after fork (follow-fork-mode child configured)](https://stackoverflow.com/questions/15126925/)
- See [this video](https://www.youtube.com/watch?v=sZ8GJ1TiMdk) at 18:05. It's just magical.
- [GDB vs LLDB (some differences in commands)](https://aaronbloomfield.github.io/pdr/docs/gdb_vs_lldb.html)
	- [GDB to LLDB command map — The LLDB Debugger](https://lldb.llvm.org/use/map.html)
