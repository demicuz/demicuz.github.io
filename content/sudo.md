---
title: "sudo"
---

It's a program that allows to execute commands as another user, often as `root`.

### Commands
- `sudo -k` - reset the timer that doesn't require password to use `sudo`
- `sudo -v` - disable password prompt for current session
- `sudo -l` - list `sudo` privileges
- `sudo -lU username` - list `sudo` privileges for other users 

### sudoers file
`sudo` is configured through `/etc/sudoers`. You should never edit it, use `visudo` instead!

`Defaults requiretty` - doesn't allow to `sudo` from scripts

### Useful
- [How To Edit the Sudoers File](https://www.digitalocean.com/community/tutorials/how-to-edit-the-sudoers-file)
- [10 Useful Sudoers Configurations for Setting 'sudo' in Linux](https://www.tecmint.com/sudoers-configurations-for-setting-sudo-in-linux/) (logging, etc.)

### See also
- [[su]]
