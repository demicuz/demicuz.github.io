---
title: "OpenGL matrices"
date: "2023-01-02"
---

For matrix operations to work together nicely, use this convention:
- `(x, y, z, 1)` is a position in space.
- `(x, y, z, 0)` is a vector.

**Translation matrix**
$$\begin{bmatrix}
1 & 0 & 0 & X\\
0 & 1 & 0 & Y\\
0 & 0 & 1 & Z\\
0 & 0 & 0 & 1\\
\end{bmatrix}$$

**Scaling matrix**
$$\begin{bmatrix}
x & 0 & 0 & 0\\
0 & y & 0 & 0\\
0 & 0 & z & 0\\
0 & 0 & 0 & 1\\
\end{bmatrix}$$

```
TransformedVector = TranslationMatrix * RotationMatrix * ScaleMatrix * OriginalVector;
```

### The Final Product
```C++
// C++ : compute the matrix
glm::mat4 MVPmatrix = projection * view * model; // Remember : inverted !
```

```GLSL
// GLSL : apply it
transformed_vertex = MVP * in_vertex;
```

### Links
- [Tutorial 3 : Matrices](https://www.opengl-tutorial.org/beginners-tutorials/tutorial-3-matrices/)
- [OpenGL 101: Matrices - projection, view, model](https://solarianprogrammer.com/2013/05/22/opengl-101-matrices-projection-view-model/)