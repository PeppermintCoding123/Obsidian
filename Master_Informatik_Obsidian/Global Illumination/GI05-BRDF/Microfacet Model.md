$$f(x, \omega_i, \omega_o) = \frac{D(h,n_x)F(\omega_i \circ n_x) G(\omega_i\circ n, \omega_n)}{
\pi (n\circ \omega_i)(n \circ \omega_o)
}$$
$h = \frac{\omega_i + \omega_o}{||\omega_i + \omega_o||}$
![[Pasted image 20261002114750.png]]
D(n)
- smooth surfache -> faces oriented along normal
- routh surface -> orientation jittered
[[Isotropy]]: 
- D depends on angle between $n_x$ & $h$: $D(\theta_h)$, $D(h\circ n_x)$
[[Anisotropy]]:
- D additionally depends on $\phi_h$: $D(\theta_h, \phi_h)$

Examples:
Beckmann-Spizzichino
[[Trowbridge-Reitz]]
![[GGX-distribution]]

# Geometric
self shadowing or masking:
$$G_1(\omega) = \frac{1}{1+\Lambda(\omega)}$$
for [[Trowbridge-Reitz]]
$$\Lambda(\omega) = \frac{-1+\sqrt{1+\alpha ^2 \tan ^2 \theta}}{2}$$
Account for masking AND self-shadowing
$$G(\omega_i, \omega_o) = \frac{1}{1+\Lambda(\omega_i)+\Lambda(\omega_o)}$$
[[Global Illumination - overview.canvas]]