---
title: "MiniLibX"
---

#todo/coding Should somehow add support for shaders. The Mac version has it.
### Notes
On my laptop it uses [shm](https://en.wikipedia.org/wiki/MIT-SHM) image format.

Default `Colormap`: 32
Default `depth`: 24

Seems like you need to know whether big or little endian your system is to manipulate colors correctly. Nuts.

### Issues
On X11 you have to [wait](https://stackoverflow.com/questions/30861472/) until `Expose` event before drawing anything on the screen.

More or less good font I have on my system:
`-bitstream-courier 10 pitch-bold-r-normal--0-0-120-120-m-0-iso8859-1`

### See also
[[xlib]]

### Links
- [MiniLibX - 42 Docs](https://harm-smits.github.io/42docs/libs/minilibx)
- [X PixMap - Wikipedia](https://en.wikipedia.org/wiki/X_PixMap)
	- [What is the difference between XYPixmap, ZPixmap, XImage, XShmImage and Bitmap in X?](https://stackoverflow.com/questions/28323960/what-is-the-difference-between-xypixmap-zpixmap-ximage-xshmimage-and-bitmap-i)
- [3D Graphics and Animation Programming Tutorial in C/Linux #01 - Creating Triangle - YouTube](https://www.youtube.com/watch?v=C-jp-_Dlz6E&list=PLApkofOilm_8-xCq2fE8cprlkhGSGeRpb&index=4)
