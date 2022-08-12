---
title: "ELF binaries"
---

If dynamically linked, use this to know the dependencies:
```shell
readelf -d $executable | grep 'NEEDED'
# or
ldd $executable
```
