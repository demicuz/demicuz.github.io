---
title: "Fedora"
---

A [[Linux]] distro.

- [[Fedora issues]]
- [[dnf]]

Maybe install RPM Fusion.
Also can somehow speed up `dnf`.

[Some guy's](https://www.reddit.com/r/Fedora/comments/vzmck8/comment/ig9bgyt) installs for proper video playback:
```shell
sudo dnf -y install ffmpeg ffmpegthumbs
sudo dnf -y install lame\* --exclude=lame-devel
sudo dnf -y install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel
```

OR Multimedia post-install on RPM Fusion. 🤷‍♂️

Also [an issue](https://www.reddit.com/r/Fedora/comments/vak8tz/i_like_to_leave_ubuntu_behind_and_only_use_fedora/) with video playback and how to solve it.

`rpmconf` is a useful tool. Dunno what it does though. `rpmsave`, `rpmnew` - what are those?

Firewall and `selinux` are enabled by default, wtf?

### `dnf`
[Do this](https://www.reddit.com/r/Fedora/comments/ue0oi5/debating_on_moving_from_ubuntu_to_fedora_kde_any/) after installation (but maybe it's default now):
```shell
vim /etc/dnf/dnf.conf
max_parallel_downloads=10
fastestmirror=True
(also maybe) deltarpm=true
```

Also see [this](https://github.com/devangshekhawat/Fedora-36-Post-Install-Guide).

`lspci` to get hardware.

### Network
[Some issue](https://www.reddit.com/r/Fedora/comments/ttf8v4/wifi_problems_on_fedora_but_not_manjaro_or_ubuntu/) with Fedora abandoning old TLS's.

### Video and stuff
- [How to install AMD drivers on Fedora? - Ask Fedora](https://ask.fedoraproject.org/t/how-to-install-amd-drivers-on-fedora/5838)

For [[Firefox]]:
You can check hardware acceleration state at about:support page, look at Compositing row. If there's `WebRender`, you're running on hardware. If there's `WebRender (software)` you're on non-accelerated backend.

Also [this page](https://fedoraproject.org/wiki/Firefox_Hardware_acceleration).

### Links
- [Installation](https://github.com/ai/environment/blob/main/Install.md) from [[Andrey Sitnik]]
