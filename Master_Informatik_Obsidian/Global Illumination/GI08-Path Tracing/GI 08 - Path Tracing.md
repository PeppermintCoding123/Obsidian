up till now:
Incident light from Light source:
$$
L(x, \omega_o)= \int f(x, \omega_i, \omega_o) L_e(ray(x, \omega_i), -\omega_i) N(x) \circ \omega_i \;d\omega_i$$
or surface parameterisation (Le sampling)
$$L(x, \omega_o)= \int f\Big (x, \frac{x-y}{||x-y||}, \omega_o \Big) G(x, y) V(x, y) L_e \Big(y, \frac{y-x}{||y-x||}\Big) \;dA_y$$
x = point on surface,
y = point on lightsource
[[Path Tracing Basic Idear]]
[[Path Tracing Pseudo code evolution]]
[[Path Tracing solve reccurence explosion]]
[[Improve basic Path Tracing]]
[[Path Tracing with Russian Roulette]]
[[Sorted Deffered Shading for Production Path Tracing]]
[[Next-Event-Estimation]]

[[Global Illumination - overview.canvas]]
