---
title: "Bash quirks"
date: "2023-01-29"
---

### Bash syntax is a joke
**Don't use spaces before or after `=` when declaring variables**

No:
```bash
msg = "hello"
echo $msg
```

```
msg: command not found
```

No:
```bash
msg= "hello"
echo $msg
```

```
hello: command not found
```

Yep:
```bash
msg="hello"
echo $msg
```

```
hello
```

---

**Use quotes around a variable for multiline output**

No:
```bash
msg="\
hello
multiline"
echo $msg
```

```
hello multiline
```

Yep:
```bash
msg="\
hello
multiline"
echo "$msg"
```

```
hello
multiline
```

### if
`if` or `if [ ]` or `if [[ ]]` or `if [[[ ]]]`??? I don't know!

See [Differences Between `[ ]` and `[[ ]]` in Bash](https://www.baeldung.com/linux/bash-single-vs-double-brackets).