---
title: "Calculating normals in Raymarching"
---

[Article by IQ](https://iquilezles.org/www/articles/normalsSDF/normalsSDF.htm)
Example ([source](https://www.shadertoy.com/view/3ljcRh)):
```C
vec3 calcNormal( in vec3 pos )
{
    vec2 e = vec2(1.0,-1.0)*0.5773;
    const float eps = 0.0005;
    return normalize( e.xyy*map( pos + e.xyy*eps ) + 
                      e.yyx*map( pos + e.yyx*eps ) + 
                      e.yxy*map( pos + e.yxy*eps ) + 
                      e.xxx*map( pos + e.xxx*eps ) );
}
```
