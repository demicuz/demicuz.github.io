---
title: "[Color Grid 1](https://www.shadertoy.com/view/4dBSRK)"
tags: [shadertoy]
---

Author: [[Inigo Quilez]]
![|600](https://i.imgur.com/EtKXHgd.jpg)

The code is short. It uses 2D noise and generates a smooth cellular pattern with varying colors. The noise function looks like this:
```C
0.5+0.5*cos(iTime+sin(dot(floor(px+0.5),vec2(113.1,17.81)))*43758.545);

```
