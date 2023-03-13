---
title: "KVM virt-manager"
date: "2023-01-30"
---

### How to SSH into a guest
Tried with [[Ubuntu Sever]]. During installation, don't forget to tick `OpenSSH server` option. Then:
```shell
sudo apt update
sudo apt install ssh
```

Don't know if this needed, but did that anyway. Then get guest's ip (e.g. with `ifconfig`). And then on the host:
```
ssh <guest_user_name>@<guest_ip>
```

[Source](https://www.youtube.com/watch?v=x5UoQ_xFhVI).

### Links
- [quickemu](https://github.com/quickemu-project/quickemu)