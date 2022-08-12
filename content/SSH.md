---
title: "SSH"
---

Connect to a server:
```bash
ssh -p 1234 user@127.0.0.1
```

Connect to [[Политех]] server:
```bash
ssh std-1746.ist.mospolytech.ru -l std
scp checkmark-outline.svg close-outline.svg std@std-1746.ist.mospolytech.ru:/home/std/www/lab6/img
```

Or with [[kitty]]:
```shell
kitty +kitten ssh std-1746.ist.mospolytech.ru -l std
```

Check if sshd is running:
```shell
ps aux | grep sshd
```

### See also
- [[GPG]]

### Setup
[Enable SSH root login on Debian Linux Server](https://linuxconfig.org/enable-ssh-root-login-on-debian-linux-server)

For VirtualBox:
![[VirtualBox#Configuring SSH]]

##### Changing the default port
[How to Change SSH Port Number in Linux](https://linuxhint.com/changing_ssh_port_number/)
1. Set `Port` in `/etc/ssh/sshd_conf`
2. `# systemctl restart sshd`

### Useful
- [What Is SFTP? (Secure File Transfer Protocol)](https://phoenixnap.com/kb/what-is-sftp)
- [ssh zine](https://wizardzines.com/comics/ssh/)
- [How to copy file remotely via SSH](https://www.simplified.guide/ssh/copy-file)
