---
title: "cut"
---

Remove sections from each line of files.

### Flags
- `-f` - choose fields
- `-c` - cut characters
- `-d` - set a delimiter

### Examples
```bash
echo "123456789" | cut 2-3 # 23
echo "123456789" | cut -4  # 1234
```
