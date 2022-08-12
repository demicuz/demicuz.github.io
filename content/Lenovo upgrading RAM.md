---
title: "Lenovo upgrading RAM"
---

I have 8Gb of RAM according to my BIOS, but only 6Gb available to system somehow. Maybe I allocated 2Gb for video memory, I don't remember.

Also I've read that my laptop model has 4Gb soldered and 4Gb in the slot. So if I by addiotional RAM, I have to get rid of the 4Gb thingie. Sigh.

Also I think the maximum RAM supported by the laptop is 12Gb. The configured frequency is 2400 Mhz, but the RAM itself supports up to 2667. Used this command:
```shell
sudo dmidecode --type 17
```
