![[Pasted image 20260829172156.png]]
$$L(x, \omega_{out})= \int_{\Omega^+} L_{in}(x, \omega_in) N \circ \omega_{in} \;d\omega_{in} $$
Ω+ is hemisphere around normal N in surface point x  
L(x, ωout ) is outgoing light from x into direction ωout - physical quantity radiance
L(x, ωin ) is incident radiance - L x, ωin = L(ray x, ωin , −ωin )
![[Pasted image 20260829172634.png]]
## Compute:
$$L(x, \omega_{out})= \int_{\Omega^+} L_{in}(x, \omega_in) N \circ \omega_{in} \;d\omega_{in} \approx \frac{2\pi}{n}\sum_{i= 1}^n L_{in}(x, \omega_in) N\circ \omega_{in}$$
why a 2 in the front? - Why is this 2\pi the size of the domain?
Because we use the domain as the Area around x, = 2\pi

[[Global Illumination - overview.canvas]]
[[03 - GI- Direct Illumination]]