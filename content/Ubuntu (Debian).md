---
title: "Ubuntu (Debian)"
---

Is a [[Linux]] distro. Package management is done through Apt and [[Snap]], but [[Flatpak]] seems to be cooler. It doesn't force updates upon you like Snap, at least. And also uses OSTree, whatever that means.

### Useful
- [What is PPA? Everything You Need to Know About PPA in Linux](https://itsfoss.com/ppa-guide/)

### Apt and dpkg
List package dependencies:
```bash
apt-cache depends package-name
```

List packages that depend on a package (reverse dependencies):
```bash
apt-cache rdepends (--installed) package-name
```

Show info about a package:
```bash
apt show PACKAGE_NAME or apt-cache show PACKAGE_NAME
```

Show to what package a file belongs to:
```bash
sudo dpkg -S /usr/bin/evolution
```

### Various stuff
Get all installed fonts:
```bash
fc-list : family | sort | uniq
```
