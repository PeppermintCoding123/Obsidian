#TODO 

[[Computer Graphics - overview.canvas]]

# Words & Formulas 
### ray
$x(\alpha) = k + \alpha l$, 
$k$ = ray starting point, $l$ = rays direction, $\alpha$ =  ray parameter

# intersection point
between eye ray & point on surface thrue a specific point

### reflection ray
$x_{refl} (t) = p_{intersect} + t l$
$l$ is the light vector hitting surface

### shadow ray
$x_{shadow}(t) = p_{intersect} + t (P_{light}-P_{intersect})$

### distribution ray tracing
applied for:
- depth of field
- motion blur
- shadow rays distributed over light source
- anti-alliazing


### When to use [[Fresnel Term]]
the fresnel term is used to describe the fact that the fraction 
of reflected light varies with the angle of incidence 
It's used in the Torrance Sparrow Light model, a physically based model.



[[Ray Exersises]]

### time complexity of rendering process
$k$ spheres, subdivided into $n$ triangles. scene rendered in $p$ pixels. little occlusion
Razterisation using triangles:
-> vertex shader: $O(kn)$
-> pixel shader: $O(p)$
Ray casting with direct ray-shere intersection test in $O(1)$: $O(pk)$
Ray casting on a well-chosen bounding volume hierarchy of triangles :
-> $O(p\; \log k)$
-> building the hirarky $O(k\; \log k)$

### Types of Rays:
- eye ray through pixel
- [[Reflection ray - ray tracing]]
- [[Shadow ray - ray tracing]]
- [[Refraction ray - ray tracing]]
- eye rays for anti-aliasing
- [[distribution ray tracing]] on diffuse and glossy surfaces



