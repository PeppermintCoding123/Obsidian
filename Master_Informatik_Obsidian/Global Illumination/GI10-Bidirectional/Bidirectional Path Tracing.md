$p_0, p_1,..., p_t$ = path from camera
$q_0, q_1, ..., q_s$ = path from light source

## How to connect?
compute [[throughput]] when calculation paths (accumulated [[BRDF]]s and [[PDF]]s)
$$T_{new} = T_\text{camera path} \times BRDF_\text{last camera vertex} \times G_{connection} \times BRDF_\text{last light vertex} \times T_\text{light path}$$
$$T_{all} = T_{cam} f(x) \cdot G(x, y)\cdot f(y) T_{light}$$
T = throughput
$G(x, y) = \frac{<N_x, (y-x)> \cdot <N_y, (x-y)>}{||x-y||^4}$ (normalise both & devide by squared distance)
$t$ = light path length
$s$ = camera path length
connect many paths of length $s' + t'$

Considder $t'= 0$ consider separately, since no light source

![[Pasted image 20260911134129.png]] ![[Pasted image 20260911135157.png]]
a) standard path tracing without direct illumination sampling (ray happen to intercect with light)
b) Path tracing with direct illunination sampling
c) Particle tracing from light source with explicite visibility test between point on surface & camera
d) Particle tracing (particle happens to intersect with cameras lense)

### Weight
Weight strategies with [[MIS - Multiple Importance Sampling]] 
& sum all

[[Path Tracing Basic Idear]]
[[Global Illumination - overview.canvas]]