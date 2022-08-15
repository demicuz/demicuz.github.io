---
title: "dnf"
date: "2022-08-16"
lastmod: "2022-08-16"
---

A notorious package manager for [[Fedora]].

stuff to check out later:
`--best`
`--allowerasing`
`distrosync`

### Flags
`--refresh`
Perform metadata update before installing anything.

### Recipes
```shell
dnf repoquery --whatrequires ibus
```
`repoquery` in general is a powerful command.

### Repos
All repos are stored in `/etc/yum.repos.d/` (including coprs).

### Useful
- [command-not-found.com](https://command-not-found.com/)
