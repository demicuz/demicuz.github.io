---
title: "Babashka"
tags: [tool, coding, clojure]
date: "2022-09-03"
lastmod: "2022-09-03"
---

[[Clojure]] for scripting, aimed to replace [[Bash]].

### Built-in variables
`*command-line-args*` - the name says it all
`*input*` - stdin, for scripts only. EDN by default, use `-i` to read text

### Commands
Start nREPL server:
```
bb --nrepl-server
```

### Resources
- [Babashka book](https://book.babashka.org/)
- [Babahska example projects](https://github.com/babashka/babashka/blob/master/doc/projects.md#release-on-push-github-action)
- https://github.com/prestancedesign/babashka-htmx-todoapp