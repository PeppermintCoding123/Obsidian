Choose samples random direction:
### Random direction 1:
use $\omega(z, \phi) = \begin{pmatrix}\sqrt{1-z^2}\cdot \cos \phi \\ \sqrt{1-z^2}\cdot \sin \phi \\ z\end{pmatrix}$
draw random values for $z$ & $\phi$=> random direction with uniform distribution

### Random direction 2:
- draw random 3D point $x\in [-1, 1]^3$
- discard if $||x||> 1$
- else normalize to Einheitskugel
- ![[Pasted image 20260829183157.png]]

[[Global Illumination - overview.canvas]]
[[03 - GI- Direct Illumination]]