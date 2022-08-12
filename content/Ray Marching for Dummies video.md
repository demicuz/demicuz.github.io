---
title: "Ray Marching for Dummies video.md"
---

<iframe src="http://www.youtube.com/embed/PGtv-dBi2wE" width="560" height="315" frameborder="0" allowfullscreen></iframe>

### Notes
There are two approaches to the `RayMarch` function - calculate and return the position in space vs return the distance that we should walk along the `rayDir`. Pos might be useful when calculating normals (saves you a multiplication and addition, meh), while distance can be used for fog/shading/etc.

`28:00` - Be careful when marching from some surface (to the light, for example), because by default, the distance from the point to the surface is less than the EPSILON. ^b12f24
