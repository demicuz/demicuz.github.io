---
title: "Bash"
aliases: [Shell]
date: "2022-08-24"
lastmod: "2022-08-24"
---

- [[Redirection in Bash]]

### Tips
Seems like you can enclose variables into `{}` when using variables and text together:
```bash
echo "Memory Usage: $uram/${tram}MB ($pram%)"
```

- [bash - Repeatedly run a shell command until it fails?](https://stackoverflow.com/questions/12967232)

Semicolon `;` is not needed at the end of lines.
You can set strings to interpret escape sequences with `$''`:
```shell
$ echo $'Name\tAge\nBob\t24\nMary\t36'
Name    Age
Bob     24
Mary    36
```

### Setting env variables
Use `sudo -H vim /etc/environment`. [Link](https://askubuntu.com/questions/58814).

### `.profile`, `.bashrc` and `.bash_profile`
Is a mess! I don't even know wtf is going on! #todo!

**Links**
[Difference Between .bashrc, .bash-profile, and .profile](https://www.baeldung.com/linux/bashrc-vs-bash-profile-vs-profile)

### Related
- [[C (language)|C]]

### Useful
- [[Useful terminal and shell commands]]
- [explainshell.com - match command-line arguments to their help text](https://explainshell.com/)
- [tldr pages](https://tldr.sh/)
- [cheat.sh](https://github.com/chubin/cheat.sh)
	
