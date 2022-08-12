---
title: "Born2beRoot"
aliases: [b2br]
---

This [[School 21]] project is about [[System Administration (Linux)]], managing [[Virtual machines]], etc.

### Different things to know
- [[AppArmor]]
- root, sudo
- [[UFW]], [[SSH]], [[cron]], crontab, wall

### Links
- [[mmargene - born2beroot]]
- [Google doc with useful info](https://docs.google.com/document/d/1J-FZ1zNYF5NaroW_N2Vcujk1uj3zVzx2L95kXK1XApk/edit#)

### Notes
Maybe config file for everything? Also, it's more convenient to work with the server through [[SSH]] than from VirtualBox.

To use `netstat`, install `net-tools`.

##### Step-by-step thingies I've done
1. [[SSH#Changing the default port]]
2. Commented `AcceptEnv LANG LC_` in `/etc/ssh/sshd_config` because of [this](https://stackoverflow.com/questions/2499794/)
3. Installed `sudo`, `ufw`, apparmor profiles
4. Configured [[UFW]]
5. Configured [[AppArmor]] (enforced `/etc/apparmor.d/*`)
6. Configured `sudo`
7. `sudo crontab -e`, added `monitoring.sh` to execute every 10 minutes
8. Installed `libpam-pwquality`, `libpam-cracklib`, added rules for passwords in `/etc/pam.d/common-password`
9. Edited `/etc/login.defs` (works only for NEW users):
```
PASS_MAX_DAYS 30
PASS_MIN_DAYS 2
PASS_WARN_AGE 7
```

#### To-do
- [x] Disable SSH as root (remove `PermitRootLogin yes` from `/etc/ssh/sshd_config`)
- [ ] I think I should disable DHCP
- [x] Set up correct [[sudo]] policy

### Things to know
[[LVM]]
[[Apt vs Aptutide]]
[[AppArmor]]

### To learn
- `awk` magic
- What is a mount point?
	- Seems to be just a root folder for a partition
- Difference between a disk partition and a volume
	- Sometimes they're used interchangeably, but a partition is a disk thingie that is written in `GUID` partition table (for example), and a volume can be logical, e.g. occupy multiple partitions and other stuff. See [on Wikipedia](https://en.wikipedia.org/wiki/Volume_(computing)#Differences_from_partition).

### Useful commands
- `du -h /somestorage` to show disk space
- `lsblk (-o name,size,fstype)` to show devices
- `hostnamectl` - info about hostname
	- `hostnamectl set-hostname newhostname` - change hostname. Located at `/etc/hostname`. Don't forget to change `/etc/hosts` or restart the machine.
	- `hostname newhostname` - changes hostname, but only for this boot session.
