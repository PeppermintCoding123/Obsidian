Problem: Most rays do not hit lightsource
Parameterize with
$$d\Omega_{omega} = dA_y \frac{N_y\circ \omega}{r^2}$$
$$L(x, \omega_{out})= \int_{A} f(x, \frac{y-x}{||y-x||}, \omega_{out}) L_e(y) G(x,y) V(x,y) \;dA_y$$
$G(x,y) = \frac{N_x\circ(y-x) \cdot N_y \circ (x-y)}{||x-y||^4}$

#### choose samples for light:
rectangular:
- same as sampling pixel
sperical:
- same as using random direction

[[Global Illumination - overview.canvas]]
[[03 - GI- Direct Illumination]]