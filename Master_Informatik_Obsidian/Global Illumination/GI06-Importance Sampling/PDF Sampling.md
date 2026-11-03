# Discrete version
# [[Inversion Method]]
## Malleys Method
= sampling with respect to the cosine
- sample as disc & lift to hemisphere
- ![[Malleys Method]]
## Importance sample of Phong BRDF
- compute r
- generate basis vectors (u, v, r)
- $\theta = arc \cos ^{n+1}\sqrt{\xi_1}, \varphi = \xi_2 \cdot 2\pi$
- generate direction $\omega = cos \theta \cdot r + \sin \theta \cdot (\cos \varphi \cdot u + \sin \varphi \cdot v)$
- ![[Pasted image 20260904143752.png]]
#Question please explain how this works?
- so wie hemisphere, nur dass r = z-richtung
- Hemisphere sampling - [[Integration over Hemisphere - Direct Illumination]]
[[Global Illumination - overview.canvas]]