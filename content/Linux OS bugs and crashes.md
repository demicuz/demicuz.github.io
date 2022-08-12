---
title: "Linux OS bugs and crashes"
---

### `/tmp` running out of space
I was compiling a [[Rust]] project with quite a lot of dependencies on Fedora. I didn't have some libraries that it needed, so compilation failed. I was installing the libraries and then trying to compile again.

Apparently, between the compilations Rust wasn't cleaning temporary build files in `/tmp`, so they were taking up a lot of space there. So I've got to a point when a build failed due to lack of space in `/tmp`. It took like 3 or 4 failed compilations. Seems like there's a separate partition here, I wonder what size it was.

So I thought, maybe I'm gonna log out and then log in, and all the files in `/tmp` will get deleted. So I did that and KDE Plasma successfully crashed due to... Inability to write some shite in `/tmp`. Because of lack of space. Had to log in to TTY and reboot from there.

### `ibus` conflicting with KDE keyboard manager
A classic one. Just don't turn it on, that's it. But stupid Zoom application installs it anyway and enables it when launched.
