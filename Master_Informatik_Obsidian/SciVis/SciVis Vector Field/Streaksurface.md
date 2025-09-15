## [[Smoke]]-based 

![[Pasted image 20250906153101.png]]
$$\alpha = \alpha_{dencity}\alpha_{shape} \alpha_{curvature} \alpha_fade, \quad 0 \leq \alpha_i \leq 1$$
## Particle based
Splitting
- Ghost particles too far away
- high surface curvature
Delete Particles.
- Ghost particles move too close to original
- $c < c_{min}$ => delete particle
- $c\geq c_{miin}$ => counter --, move ghost particles further away
- ![[Pasted image 20250906153912.png]]
## Triangle based
- particles of 1 [[Timelines]] in vertex buffer - memory in case split
- complete insertion removal of [[Timelines]]
- ![[Pasted image 20250906154115.png]]