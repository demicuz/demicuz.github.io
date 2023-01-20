---
title: "Stuff to do after Linux installation"
date: "2022-12-23"
---
[Enable SyRrq](https://fedoraproject.org/wiki/QA/Sysrq) for the magic `REISUB` spell when the system freezes.
[Disable freaking system beep](https://wiki.archlinux.org/title/PC_speaker#Globally). On my laptop it's extremely loud.
Remove garbage from [[Linux autostart]]. I removed this in [[KDE]] [[Fedora]]:
```
geoclue-demo-agent.desktop
kaccess.desktop
liveinst-setup.desktop
org.kde.discover.notifier.desktop
org.kde.kalendarac.desktop
org.kde.kdeconnect.daemon.desktop
spice-vdagent.desktop
vboxclient.desktop
```

### Limit CPU temp
For my garbage Lenovo laptop. It has extremely buggy BIOS which doesn't control the fan properly and CPU gets overheated as a result.

Download and compile [RyzenAdj](https://github.com/FlyGoat/RyzenAdj).

Add a small script to KDE autostart menu:
```bash
#!/bin/bash

sudo /opt/RyzenAdj/ryzenadj --tctl-temp=63 && notify-send "Successfully set tctl_temp to 63"

# Wait for the GUI to be ready
# while [[ ! $(pgrep plasmashell) ]]; do sleep 1; done
# sudo /opt/RyzenAdj/ryzenadj --tctl-temp=62 && notify-send "Sucessfully set tctl_temp to 62"
```

Also set it to use `sudo` without password using [this](https://askubuntu.com/questions/197536/running-a-startup-program-in-terminal-with-sudo?rq=1) method. Using `sudo visudo` add this **to the end of the file**:
```
psharen ALL=NOPASSWD: /opt/RyzenAdj/ryzenadj
```

You can also add a custom shortcut to launch it (`Meta + T`). But after suspend/wakeup cycle this setting breaks. And there's no way under KDE to execute something after wakeup, AFAIK. So I used [this method](https://askubuntu.com/questions/226278/run-script-on-wakeup) and added a small script to `/lib/systemd/system-sleep/`:
```bash
#!/bin/sh

case $1/$2 in
  pre/*)
    # echo "Going to $2..."
    # Place your pre suspend commands here, or `exit 0` if no pre suspend action required
    exit 0
    ;;
  post/*)
    # echo "Waking up from $2..."
    # Place your post suspend (resume) commands here, or `exit 0` if no post suspend action required
    # while [[ ! $(pgrep plasmashell) ]]; do sleep 1; done
        /opt/RyzenAdj/ryzenadj --tctl-temp=63
    ;;
esac
```
