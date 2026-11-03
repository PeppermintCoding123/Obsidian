See: [[Phong energy conservation]]
Phong lighting model:
$$L_{spec} = (r \circ c)^{n_{shiny}}$$
BRDF:
$$f_{Phong}(v, l) = k_{spec}(v \circ r)^{n_{shiny}}$$
Blinn-Phong
$$L_{spec} = (n \circ h)^{n_{shiny}}$$
[[Blinn-Phong BRDF]]
$$f_{Blinn-Phong}(v, l) = k_{spec}(n \circ h)^{n_{shiny}}$$


r = reflection vecor of light
$h = \frac{v+l}{||v+l||}$ halfway vector

# PROBLEM:
highlights seem darker with increasing exponent

![[Pasted image 20261001173401.png]]


[[Phong Lighting]]
[[Phong Shading]]
[[Blinn-Phong BRDF]]
[[Global Illumination - overview.canvas]]