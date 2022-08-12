---
title: "Raymarching and SDFs"
---

[A list of signed distance functions](https://iquilezles.org/www/articles/distfunctions/distfunctions.htm)

### Notes
In [this shadertoy](https://www.shadertoy.com/view/3ljcRh) the epsilon used to calculate the normals is 5 times bigger than `min_dist` to SDF to stop raymarching (`1e-4` and `5e-4`).

### Shadertoys
- [Raymarching visualizer](https://shadertoy.com/view/XtjXRm)

### Tutorials
- [[Ray Marching for Dummies video]]
- [[Inigo Quilez]] YouTube channel

### Useful articles and techniques
- [[Calculating normals in Raymarching]]

### Pitfalls
- SDF subtraction doesn't return the *real* distance to the resulting object. As well as `max` function in general. See [this](https://www.shadertoy.com/view/4sKfDR). If the object being subtracted is fully inside another object, then the distance is correct. Also see [this](https://www.shadertoy.com/view/3t33WH) shadertoy by IQ and the article.
- ![[Ray Marching for Dummies video#^b12f24]]

### Related
- [[Raycasting]]
