start rendering => 3D space store
next point: 
	if close enought (3D [[Nearest Neighbor]]): reuse value 
	else: generate new cache
	**or** do gradients with Taylor approximation
# 1. Extrapolate better
![[Pasted image 20260911111458.png]]

# 2. estimate weights for interpolation
$$w_i = \frac{1}{e_i(\Delta x , \Delta \varphi)}\quad e(\Delta x , \Delta \varphi) = \frac{4\Delta x}{\pi R} + \sin \Delta \varphi$$
weight for interpoolation = 1/error estimation
$\Delta x$ translate by
$\Delta \varphi$ rotate by
$R = \frac{n}{\sum_{i=1}^n 1/r_i}$ harmonic average for $r_i$ = length of ray $i$

$$E(x, n) = \frac{\sum_{i= 1}^k w_i E_i(x, n)}{\sum_{i= 1}^k w_i}$$
$E_i(x, n)$= extrapolation from chace $i$
$w_i$ = weight of chache $i$
$i$ iterates over $k$ relavant Neares Neighbours
- chache is relevant if weight above threshold
- find cache by storing in octatree structure
![[Pasted image 20260911112952.png]]

# summery:
For each eye ray:
– search nearby, relevant caches
– if none
	→ generate new one by casting many indirect rays or paths
	→ compute irradiance gradients
	→ store cache in octree data structure
– compute weights for all nearby caches
– extrapolate irradiance for all nearby caches
– interpolate extrapolations using weights


[[Irradiance Caching]], [[Irradiance Gradients]]
[[Global Illumination - overview.canvas]]