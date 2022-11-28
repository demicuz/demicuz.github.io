---
title: "VirtualBox"
date: "2022-11-10"
lastmod: "2022-11-10"
---

### Snapshots
![Snapshots List For a Virtual Machine](https://docs.oracle.com/en/virtualization/virtualbox/6.0/user/images/snapshots-1.png)
They're like diff files between different `.vdi` images. When a snapshot is created, the base `.vdi` is frozen and the changes are written to a differencing image.
> Differencing images can be chained. If another differencing image is created for a virtual disk that already has a differencing image, then it becomes a _grandchild_ of the original parent. The first differencing image then becomes read-only as well, and write operations only go to the second-level differencing image. When reading from the virtual disk, Oracle VM VirtualBox needs to look into the second differencing image first, then into the first if the sector was not found, and then into the original image. ([From the docs](https://docs.oracle.com/en/virtualization/virtualbox/6.0/user/diffimages.html))

From [1.10. Snapshots - Docs](https://docs.oracle.com/en/virtualization/virtualbox/6.0/user/snapshots.html):
> To avoid losing the current state when restoring a snapshot, you can create a new snapshot before the restore operation.

Some tips on using them:
- <mark style="background: #FF5582A6;">Don't use them as backups</mark> 
- Don't use them for too long, as they are just diff files and occupy more and more space when being used. Below 72 hours should be fine.
- Don't chain more than 2-3 snapshots



### Configuring SSH
- [How to connect to VirtualBox via SSH - Linux Networking](https://linuxconfig.org/unable-to-ssh-into-virtualbox-guest-machine)
- [Easy way to SSH into VirtualBox machine | Any OS - DEV Community](https://dev.to/developertharun/easy-way-to-ssh-into-virtualbox-machine-any-os-just-x-steps-5d9i)

### Links
- [How to Install VirtualBox on Fedora 36 / Fedora 35 | ITzGeek](https://www.itzgeek.com/how-tos/linux/fedora-how-tos/install-virtualbox-on-fedora.html)