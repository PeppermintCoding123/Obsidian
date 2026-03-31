$$L_{total} = L_{amb} + L_{diff}+L_{spec}$$
##### Ambient light source
$$L_{amb} = k_{amb}I_{amb}$$
$k_{amb}$ = ambient reflection coefficiant - surface property
$I_{amb}$ = intencity of ambient light source
##### Diffuse Reflection
- Lambert's cosine law
$$L_{diff} = k_{diff}I_{in}(n\cdot l) = k_{diff}I_{in}\cos(\theta) $$
![[Pasted image 20260213162528.png]]

$n\cdot l < 0$ => Light behind surface
$n\cdot v < 0$ => viewer looking at underside & cannot see front face
$\max(0, n\cdot l)$
##### Specular Reflection
$$L_{spec} = k_{spec}I_{in}(v\cdot r)^{n_s} = k_{spec}I_{in}(\cos\phi)^{n_s}$$
![[Pasted image 20260213163334.png]]
$r$ = ideal reflectance vector
$v$ = vector towards viewer
$r = 2(n\cdot l)n-l$

[[Computer Graphics - overview.canvas]]
[[Phong Lighting]]