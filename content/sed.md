---
title: "sed"
date: "2022-12-31"
---

```shell
sed -E 's/(=[[:blank:]]*)(.*)/\1"\2"/'
make re &| sed -E 's/(.*:[[:digit:]]+:[[:digit:]]+)/==> \1 <==/g'
make re &| sed -E 's/(.*:[[:digit:]]+:[[:digit:]]+)/\e]8;;http://example.com\a\1\e]8;;\a/g'

echo -e '\e]8;;http://example.com\aThis is a link\e]8;;\a' | sed 's/foo/bar/g'

sed -e $'s#^\(.*\:[[:digit:]]\+:[[:digit:]]\+\)#\e]8;;file:'`pwd`/$'\\1\a\\1\e]8;;\a#'
```

### Links
- [Add quotes around a value using `sed`](https://unix.stackexchange.com/questions/120211/)
- [What characters do I need to escape when using sed in a sh script?](https://unix.stackexchange.com/questions/32907/)