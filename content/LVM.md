---
title: "LVM"
---

Stands for Logical Volume Management. Instead of managing physical volumes, let's create logical ones and translate them to physical. Logical volume can span multiple physical volumes (and multiple disks).

**NOTE**: you can't use logical volumes for `/boot`. That is because [[GRUB]] can't read from logical volumes.

### Useful
- [Complete Beginner's Guide to LVM in Linux [With Hands-on]](https://linuxhandbook.com/lvm-guide/)
- [Logical Volume Manager (LVM) versus standard partitioning in Linux | Enable Sysadmin](https://www.redhat.com/sysadmin/lvm-vs-partitioning)
