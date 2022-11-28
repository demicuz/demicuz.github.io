---
title: "Linux shared libraries"
date: "2022-11-23"
---

Have an `.so` extension. Or sometimes with numbers, like `so.1` or `so.1.7`. It denotes the version of the library. You can find 64-bit libraries in `/usr/lib64` and 32-bit libraries in `/usr/lib`. At least that's the way it is on my Fedora.

Use `ldconfig` to get info about system-wide libraries. E.g.:
```shell
ldconfig -p | grep libmimalloc
```

To check against what libraries an ELF was compiled:
```shell
readelf -d /usr/bin/python3.10 | grep 'NEEDED'
```

You also need to know whether ELF is 32-bit or 64-bit.