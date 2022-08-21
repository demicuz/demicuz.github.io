---
title: "minishell"
date: "2022-08-18"
---

Hello world

A [[School 21]] project. Write your own shell.

You should watch intranet tutorials!

### Lexer and parser
I want to implement a [[Recursive descent parser]].

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
echo foo bar > out baz # writes "foo bar baz" to file "out"
> out echo foo bar baz # does the same
```

If the output is both redirected to a file and piped to the next command, **it won't be piped**, only written to a file.

```shell
echo foo > bar | tee # doesn't pring anything, writes to "bar"
echo foo > bar | echo baz > wat # writes to files "bar" and "wat"
```

`|` (pipe) has higher priority then `&&`/`||`. I don't know if `&&` has precedence over `||`.

Backslash `\` escapes **one** special char (space, `&`, `|`, maybe others).

Seems like we don't have to implement command substitution (`$(...)`) and arithmetic expansion.

Some examples of how Bash does stuff:
```shell
tee << eof
> $PWD
> '$PWD'
> "$PWD"
> eof
/home/psharen/42/minishell/experiments
'/home/psharen/42/minishell/experiments'
"/home/psharen/42/minishell/experiments"

echo wat > foo bar baz # will create only foo, won't throw errors

rm foo\  bar # delete the files named 'foo ' and 'bar'
```

**Links**
- [BNF for bash](https://flylib.com/books/en/4.108.1.100/1/)
- [Bash V2 grammar](https://cmdse.github.io/pages/appendix/bash-grammar.html)
- [Shell Command Language](https://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap02.html)
- [Bash Reference Manual](https://www.gnu.org/software/bash/manual/html_node/index.html)

### Examples
- [Rush-iam/minishell](https://github.com/Rush-iam/minishell)

### Links
- [minishell wiki](https://github.com/Aisoipheo/21_42_wiki/blob/main/minishell/README.md)
- [Unix shell tutorial](https://web.archive.org/web/20170207130846/http://porkmail.org/era/unix/shell.html)

##### Readline
- [Basics of using the readline library](https://eli.thegreenplace.net/2016/basics-of-using-the-readline-library/)