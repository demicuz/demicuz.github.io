---
title: "GLSL"
---

### Essentials
#### Pages
- [[Angles and rotation in GLSL]]

#### Functions ^h1saewe
```C
smoothstep(edge1, edge2, x);
distance();
clamp();

// A neat trick with max:
max(vec2(.4, .1), .3) // vec2(.4, .3)

float distance(TYPE a, TYPE b) // = length(a - b)
TYPE reflect(TYPE i, TYPE n) // = i - 2. * dot(n, i) * n 
   // this computes the reflection of vector 'i' 
   // at a plane of normalized(!) normal vector 'n'

all(); any(); lessthen(); // and etc
```

Some 3D functions: ^c4jjbre
```C
reflect(); refract(); faceforward(); // etc
```

- [[dFdx and dFdy]]
- [sign](https://www.khronos.org/registry/OpenGL-Refpages/gl4/html/sign.xhtml) - use this to get the sign.

#### Variables
```C
// define an array of floats
float a[];
float[] b;
// define an arrays of floats with length of 5
float c[5];
float[5] d

int a[4] = int[](4, 2, 0, 5, 1);
float a[5] = float[5](3.4, 4.2, 5.0, 5.2, 1.1);
int[] c = int[3](1, 2, 3);
int[] d = int[](5, 7, 3, 4, 5, 6);
```

#### Data types
floats, ints, etc.. Some exotic ones:
- `bvec(2,3,4)` - a boolean vector ^c28a06
- `ivec(2,3,4)` - an integer vector

#### Syntax neatos
- You can actually do `1.0 - vec3(1,2,3)` or some stuff like that. It's the same as `vec3(1.0) - vec3(1,2,3)` ^nk0sofj
#### Dealing with matrices
```C
mat3 m = mat3(
   1.1, 2.1, 3.1, // first column (not row!)
   1.2, 2.2, 3.2, // second column
   1.3, 2.3, 3.3  // third column
);
mat3 id = mat3(1.0); // puts 1.0 on the diagonal
                     // all other components are 0.0
vec3 column0 = vec3(0.0, 1.0, 0.0);
vec3 column1 = vec3(1.0, 0.0, 0.0);
vec3 column2 = vec3(0.0, 0.0, 1.0);
mat3 n = mat3(column0, column1, column2); // sets columns of matrix n
```

You can also define non-square matrices with `matNxM`, e.g. `mat2x3`.

If a larger matrix is constructed from a smaller matrix, the additional rows and columns are set to the values they would have in an identity matrix:
```C
mat2 m2x2 = mat2(
   1.1, 2.1, 
   1.2, 2.2
);
mat3 m3x3 = mat3(m2x2); // = mat3(
   // 1.1, 2.1, 0.0,   
   // 1.2, 2.2, 0.0,
   // 0.0, 0.0, 1.0)
mat2 mm2x2 = mat2(m3x3); // = m2x2
```

If a smaller matrix is constructed from a larger matrix, the top, left submatrix of the larger matrix is chosen, e.g. in the last line of the previous example.

See also [[Angles and rotation in GLSL]]

### Snippets
#### Custom blurring function
```C
#define BLUR 10. / min(iResolution.x, iResolution.y)
#define SS(edge, x) smoothstep(-BLUR, BLUR, x - edge)
```

### Pitfalls & trivia
- `pow(x,y)` is doing `exp(y*log(x))`: costly, not valid for x<0, not perfect precision.
	- for x^2, do prefer `x*x`!
	- for 2^x use `exp2(x)`. The reverse `log2` also exist.
- `mix` function doesn't clamp *a* (the last value)! So if it's greater than 1, the second color gets multiplied. Because it's implemented like this: $$(1-a)x+ay$$
- [[GLSL compilation]]

### To process #todo
#### Shaders
- Flipping tiles (https://www.shadertoy.com/view/XtS3Dt)
- Geometric Grid Pattern (https://www.shadertoy.com/view/Wdd3DX)
- Portal 2 Box Flip Rotation (https://www.shadertoy.com/view/ltBcD3)
#### Box formula by [[Shane]]
This renders a horizontal or vertical box-line from point `a` to point `b` with a line width of `w`. It's different to the the usual line formula because it doesn't render the rounded caps on the end. Sometimes, you don't want those. It utilizes IQ's box formula and was put together in a hurry, so I'd imagine there are more efficient ways to do the same, but it gets the job done. I put together a more generalized angular line formula as well.
```C
float lBoxHV(vec2 p, vec2 a, vec2 b, float w){
    
   vec2 l = abs(b - a); // Box-line length.
   p -= vec2(mix(a.x, b.x, .5), mix(a.y, b.y, .5)); // Positioning the box center.
   
   // Applying the above to IQ's box distance formula.
   vec2 d = abs(p) - (l + w)/2.; 
   return min(max(d.x, d.y), 0.) + length(max(d, 0.));
}
```

### Related
- [[GLSL and graphics programming resources]]
- [[Colors]]
- [[THREE.js]]
