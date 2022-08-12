---
title: "Shadertoy mysterious bugs"
---

- https://www.shadertoy.com/view/XtyGDR - draws a fractal tree. Look in the comments, `int(iter+0.5)` for loop iteration to work on Mac.
- `out` parameters don't receive data (whatever this means) and this can cause problems on some platforms. See comments [here](https://www.shadertoy.com/view/NdS3Dh) for info.
