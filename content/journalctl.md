---
title: "journalctl"
date: "2023-01-24"
---

Had a crash? Use this on the next boot:
```shell
journalctl -b-1 -p err | tail
```

### Links
- [How To Use Journalctl | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-use-journalctl-to-view-and-manipulate-systemd-logs)