---
title: "My OS"
date: "2022-08-15"
lastmod: "2022-08-15"
---

#todo rewrite this stuff. I use [[Fedora]] now.

- [[Software I use]]
- [[KDE settings I tend to change]]
- [[Stuff to do after Linux installation]]
- [[Software to update by hand]]

### Things I've changed in my [[Kubuntu]] (old)

#### Changes to [[GRUB]]
Added `iommu=soft` due to [this issue](https://bugzilla.kernel.org/show_bug.cgi?id=202665) that crashes my laptop. *UPD*: removed it, just because it spams errors in `journalctl`. I'm to lazy to figure out whether there's something to worry about, so just restored default GRUB config. UPD2: system freezes returned 🥲. Kernel version: 5.11.0-41 generic.

#### Other changes
- Set interface scale to 125%
- Enabled REISUB
- Installed various utils (`bmon`, `screenfetch`, `qbittorent`)
- Changed DNS from `127.0.0.53` to smth. But I think this DNS was set up by nginx lol.

Force font DPI setting - It was on, set to 120, but the default is off. Turned it off. Dunno why it was on.
UPD: it seems like it should be set to 120. Turned it back on.

### Dumb fixes
- [hashman.ca :: Repack Zoom .debs to remove the `ibus` dependency](https://hashman.ca/zoom/)
- snaps and flatpacks not added to applications if using [[zsh]]: [bug](https://bugs.launchpad.net/ubuntu/+source/snapd/+bug/1640514), see comment 38 for a fix.

### Bugs I've encountered
- amdgpu shit again ([logs](https://pastebin.com/qZg5imae))
	- [Bug #1883493 “amdgpu hangs from time to time with *ERROR* Waitin...” : Bugs : linux package : Ubuntu](https://bugs.launchpad.net/ubuntu/+source/linux/+bug/1883493)
	- [213145 – AMDGPU resets, timesout and crashes after "*ERROR* Waiting for fences timed out!"](https://bugzilla.kernel.org/show_bug.cgi?id=213145)
	- [*ERROR* IB test failed on gfx (-110) on P14s Gen2 AMD when waking up from s0ix (#1824)](https://gitlab.freedesktop.org/drm/amd/-/issues/1824)
	- [Ryzen 4700U failing to enter suspend/modern-standby correctly (#1230)](https://gitlab.freedesktop.org/drm/amd/-/issues/1230)
