---
title: "minishell"
date: "2022-08-18"
---

A [[School 21]] project. Write your own shell.

You should watch intranet tutorials! Though I couldn't find them...

### Lexer and parser
I want to implement a [[Recursive descent parser]]. UPD: I gave up the bonus part. Recursive descent parser is an overkill for the mandatory part, but whatever.

![](https://i.imgur.com/SPnaTSC.png)

- [Parse tree - Wikipedia](https://en.wikipedia.org/wiki/Parse_tree)
- [Context-free grammar - Wikipedia](https://en.wikipedia.org/wiki/Context-free_grammar)
- [[Pattern matching]]
- [BashParser - Greg's Wiki](https://mywiki.wooledge.org/BashParser)

### Clean-up
Should I call `rl_clear_history`? There are no leaks, even if I don't call it.

### Exiting shell
- [Why does Ctrl-D (EOF) exit the shell?](https://unix.stackexchange.com/questions/110240/)

### Notes on Bash behavior
It doesn't matter where exactly you put redirects (`>`, `>>`):
```shell
echo foo bar baz > out # writes "foo bar baz" to file "out"
echo foo bar > out baz # does the same
> out echo foo bar baz # does the same
```

If the output is both redirected to a file and piped to the next command, **it won't be piped**, only written to a file.

```shell
echo foo > bar | tee # doesn't pring anything, writes to "bar"
echo foo > bar | echo baz > wat # writes to files "bar" and "wat"
```

`|` (pipe) has higher priority than `&&`/`||`.

Backslash `\` escapes **one** special char (space, `&`, `|`, maybe others).

Seems like we don't have to implement command substitution (`$(...)`), only environment variables (like `$PWD`).

`&&` and `||` have equal precedence and are executed left to right. Use `()` to change priority. UPD: `()` actually creates a subshell. So stuff like this is valid:
```shell
echo foo | (tee | cat)
```

According to the checklist, "`()` should behave like in Bash". Goodbye bonus part, then.

Some examples of how Bash does stuff:
```bash
$ tee << eof
> $PWD
> '$PWD'
> "$PWD"
> eof
/home/psharen/42/minishell/experiments
'/home/psharen/42/minishell/experiments'
"/home/psharen/42/minishell/experiments"

$ rm foo\  bar # delete the files named 'foo ' (with a space) and 'bar'

# If there's no space between a quoted string and a command,
# they're the same word.
$ e"cho" hello
hello

$ echo "foo"bar
foobar

$ echo "hel""lo"
hello

$ echo foo > bar > baz # writes "foo" to "baz", creates empty file "bar"
# if we would remove write access to "bar", it would give us error and
# won't execute further. The logic is - create/open all needed files
# first, then write to the last one.

$ "" echo hello # nothing happens, not even an error

$ > wat # creates empty file "wat"

```

**Links**
- [BNF for bash](https://flylib.com/books/en/4.108.1.100/1/)
- [Bash V2 grammar](https://cmdse.github.io/pages/appendix/bash-grammar.html)
- [Shell Command Language](https://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap02.html)
- [Bash Reference Manual](https://www.gnu.org/software/bash/manual/html_node/index.html)
- [Bash parsing stages](https://stackoverflow.com/a/54164474)
- [In what order does Bash parser escape characters and split words/tokens within command line?](https://stackoverflow.com/questions/54160869/)

### Non-tty mode
Minishell should work not only as an interactive shell, but as an interpreter too (if I understood the subject right):
```shell
$ echo "echo foo bar" | ./minishell
foo bar
```

### Examples
- [Rush-iam/minishell](https://github.com/Rush-iam/minishell)

### Links
- [minishell wiki](https://github.com/Aisoipheo/21_42_wiki/blob/main/minishell/README.md)
- [Unix shell tutorial](https://web.archive.org/web/20170207130846/http://porkmail.org/era/unix/shell.html)
- [Building a simple compiler of PL/0 language in C](https://briancallahan.net/blog/20210814.html)

##### Readline
- [Basics of using the readline library](https://eli.thegreenplace.net/2016/basics-of-using-the-readline-library/)