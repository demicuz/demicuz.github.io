---
title: "GLSL compilation"
---

The compiler usually tries to unroll loops for performance gain, but if there are too many cycles, the code can get too long and overwhelm the GPU. Or sometimes slow down the compilation. You can prevent this by tricking the compiler and throwing non-constants to the loop conditions. Example:
```C
#define ZERO (min(iFrame,0))
for( int i=ZERO; i<24; i++ )
{
	...
}
```

### Useful
- [Puzzling compilation errors in shadertoy](https://shadertoyunofficial.wordpress.com/2018/03/26/puzzling-compilation-errors-in-shadertoy/)
