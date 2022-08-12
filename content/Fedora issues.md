---
title: "Fedora issues"
---

### Broken packages
Sometimes there's a broken update that gets pushed through RPM Fusion or something. This command may solve it:
```shell
sudo dnf update --refresh -y --best --allowerasing   
```

From [this issue](https://www.reddit.com/r/Fedora/comments/w9iw76/have_an_issue_with_kde_plasma_reinstall_and_login/) with Plasma being broken.
