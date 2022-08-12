---
title: "Angles and rotation in GLSL"
---

Zero starts from the right axis, positive rotation is clockwise. If we do `fract(atan(y, x))` on the translated UV, we'll get this:
![|400](https://i.imgur.com/viawkB3.png)

[Matrix multiplication](https://stackoverflow.com/questions/24593939/matrix-multiplication-with-vector-in-glsl). See also [this](https://en.wikibooks.org/wiki/GLSL_Programming/Vector_and_Matrix_Operations) and [this](https://en.wikibooks.org/wiki/GLSL_Programming/Applying_Matrix_Transformations).

To summarize, if you want to apply matrix to a vector, you write it in this order, like in good ol' math:
```C
vec3 new_vector = matrix * old_vector;
```
 
 You can also write it in reverse order, but that will multiply by a *transposed* matrix. Sadly, `some_vec *= matrix` will do exactly that.
 
 ### So, how to rotate something in GLSL?
 ```C
vec2 rotated_vector = rotation_matrix * vector;
```
