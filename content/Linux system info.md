---
title: "Linux system info"
---

### CPU
`/proc/cpuinfo` and `lscpu` have all the info.

As far as I know, **physical processor** refers to a real, single physical processor, not a processor core. And **virtual processors** are cores times the number of threads on each core (I think?).
See [Counting processors on your Linux box | Network World](https://www.networkworld.com/article/2715970/counting-processors-on-your-linux-box.html).

To get CPU load you can use `top`. Or `/proc/stat`. Example: [bash - How to get overall CPU usage (e.g. 57%) on Linux](https://stackoverflow.com/questions/9229333/)
Or even better, [/proc/loadavg](https://stackoverflow.com/questions/11987495/).

### Memory
`free` - display amount of free and used memory in the system (parses `/proc/meminfo`). `-m` to print in mebibytes, `--mega` to print in megabytes.

### Disk
`df` - display disk space usage.
`--block-size=MB` for megabytes, `--block-size=M` (or `MiB`) for mebibytes.

Show 20 most space-consuming files (or folders):
```bash
du -h | sort -rh | head -n 20
# or this, to avoid comparing subdirectories:
du -sh * | sort -rh | head -n 20
# or, to include hidden files
du -sh {*,.[^.],.??*} | sort -rh | head -n 20
```
[About](https://unix.stackexchange.com/questions/186214) this arcane `{*,.[^.],.??*}` stuff. Don't know if works in [[fish]].

You can also try this:
```bash
du -sk * | sort -rn
```

### Network
`netstat` all the way. `netstat -n` for resolving hostnames fast. Helps on a [[Virtual machines|VM]].
