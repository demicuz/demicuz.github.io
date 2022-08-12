---
title: "Managing users in Linux"
---

The data about users is stored in `/etc/passwd`. Editing it manually is usually a bad idea. You can read about its structure [here](https://www.cyberciti.biz/faq/understanding-etcpasswd-file-format/).

`/etc/group` stores info about groups. Each user has a *primary* group, named the same as the user, and may be in *supplementary* groups (like sudo, fuse, etc.).

##### Commands
- `who` - show who is logged in
- `whoami` - current user name
- `su` - substitute user. Execute commands or log in as another user. Set to `root` by default.
	- `su username` - switch to a given user
	- `su - username` - switch to a given user and simulate a full login shell
- `sudo <some_command>` - execute command as `root`. Unlike `su`, will request the password of the *current* user, not `root` password. The user is required to be in `sudo` group. See also [[sudo]].
- `id` - get user group (or other) id, e.g. `id -g psharen`

Modify users:
- `adduser [_login_]` - add a user
- `deluser [_login_]` - delete user
- `usermod` - modify user account
	- `usermod -aG group1,group2 user` - add user to groups
	- `-a` - append, used only with `-G`
	- `-G` - groups
- `gpasswd -a username group` - also add user to groups
- `adduser [_login_] [_group_]` - also add user to groups
- `passwd [_user_]` - set passwords. Defaults to current user, but can edit other users' as well, if under `root`.

Groups:
- `groups <username>` - display the user's groups, defaults to current user
- `addgroup` - create groups (only root can do that). There's also `groupadd`, but it's more for scripting purposes. On my machine, `addgroup` is a symlink to `adduser`
- `delgroup` - delete groups

##### Useful
- [How to List Users in Linux](https://linuxize.com/post/how-to-list-users-in-linux/) *warning*: scripts are mostly not functional
- [How To Edit the Sudoers File | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-edit-the-sudoers-file)
- [Groups and processes, how it works under the hood](https://unix.stackexchange.com/questions/6387)
- [SystemGroups - Debian Wiki](https://wiki.debian.org/SystemGroups) - has some info about system groups like `cdrom`, `fuse`, etc. Those are mostly obselete.
- [GID, current, primary, supplementary, effective and real group IDs?](https://unix.stackexchange.com/questions/18198/gid-current-primary-supplementary-effective-and-real-group-ids)
- [How do groups work on Linux?](https://jvns.ca/blog/2017/11/20/groups/)
- [addgroup vs groupadd](https://unix.stackexchange.com/questions/55564/addgroup-vs-groupadd)

---
##### See also
- [[Linux password policy]]
