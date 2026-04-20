### [[Sphere Intersection - Ray]]:
Define:
ray = $\{e+dx|x\in \mathbb{R}\}$
plane = $\{y\in \mathbb{R} | n \circ (c - y) = 0\}$
ray as $y$ in plane equasion:
$n \circ (c-(e+dx))= 0 \Leftrightarrow n\circ (c-e) + x(n\circ d)=0 \Leftrightarrow x = \frac{n\circ (c-e)}{n \circ d} \wedge n\circ d \neq 0$

Algorithm:
if $d\circ n == 0$: return None
$x = \frac{n\circ (c-e)}{n \circ d}$
if $x < 0:$ return None (behind camera)
$p = e+dx$ (point on plane)
if $length(c,p)\geq r$: return None
return $p$
![[Pasted image 20260402121430.png]]
### Camera in space
given: 
camera position 
looking at point
up-vector
calculate:
eye
u
v
w
![[Pasted image 20260402124842.png]]

[[Eye Ray]]

[[Computer Graphics - overview.canvas]]