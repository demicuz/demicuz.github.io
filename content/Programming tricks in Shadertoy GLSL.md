---
title: "Programming tricks in Shadertoy GLSL.md"
---

[Link](https://shadertoyunofficial.wordpress.com/2019/01/02/programming-tricks-in-shadertoy-glsl/)

### Drawing lines
```C
float line(vec2 p, vec2 a,vec2 b) { // --- distance to segment with caps
    p -= a, b -= a;
    float h = clamp(dot(p, b) / dot(b, b), 0., 1.);// proj coord on line
    return length(p - b * h);                      // dist to segment
    // We might directly return smoothstep( 3./R.y, 0., dist),
    //     but its more efficient to factor all lines.
    // We can even return dot(,) and take sqrt at the end of polyline:
    // p -= b*h; return dot(p,p);
}
```

### Vector math
A gold mine of useful stuff, like converting to polar and back, complex number operations, etc.

### Computing random values
