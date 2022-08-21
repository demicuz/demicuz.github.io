---
title: "Fedora issues"
date: "2022-08-17"
lastmod: "2022-08-17"
---

### Broken packages
Sometimes there's a broken update that gets pushed through RPM Fusion or something. This command may solve it:
```shell
sudo dnf update --refresh -y --best --allowerasing   
```

From [this issue](https://www.reddit.com/r/Fedora/comments/w9iw76/have_an_issue_with_kde_plasma_reinstall_and_login/) with Plasma being broken.

### Broken `irqbalance`
Just wait for Fedora 37 release. See [this issue](https://bugzilla.redhat.com/show_bug.cgi?id=1952715).