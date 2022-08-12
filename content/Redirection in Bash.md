---
title: "Redirection in Bash"
---

![img](https://wizardzines.com/comics/redirects/redirects.png)

`>` redirects output read from a file descriptor to a file. Default descriptor is 1 (`stdout`), so `>name` means `1>name`. Example:
```shell
ls -a > result.txt
```

`<` redirects input. So `wc < file.txt` means `wc` will treat data from `file.txt` as `stdin`.

`2>&` redirects file handle "2" (almost always `stderr`) to some other file handle (it's generally written as `2>&1`, which redirects `stderr` to the same place as stdout).

`&>` and `>&` redirect both `stdout` and `stderr` to a file. It's normally written as `&>file` (or `>&file`). It's functionally the same as `>file 2>&1`. (todo: so why do they have different syntax?)

`&>file` is equivalent to `1>file 2>&1`.

### Notes
- It seems like you can ignore spacing *between* redirection symbols. So `ls > file` and `ls>file` are the same. But when dealing with descriptors and stuff - it should be without spaces (`2>`).
- Files are read/created at first and then the commands are executed. So `ls > file` will write `file` in `file`.

### See also
[[Useful terminal and shell commands#Tips|Terminal tips]]

### Links
- [bash redirects - wizardzines](https://wizardzines.com/comics/redirects/)
- [Read and write data from anywhere with redirection in the Linux terminal | Opensource.com](https://opensource.com/article/20/6/redirection-bash)
- [Input Output Redirection in Linux/Unix Examples](https://www.guru99.com/linux-redirection.html)
- [What does &> do in bash? - Stack Overflow](https://stackoverflow.com/questions/24793069/)
- [What's the difference of redirect an output using ">", "&>", ">&" and "2&>"? - Stack Overflow](https://stackoverflow.com/questions/4749226/)

More advanced:
- [What does the < (left chevron / triangle bracket) do?](https://unix.stackexchange.com/questions/283374/)
- [What does <<< mean?](https://unix.stackexchange.com/questions/80362/)
- [What's the difference between <<, <<< and < < in bash?](https://askubuntu.com/questions/678915/)
