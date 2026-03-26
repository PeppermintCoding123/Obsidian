- At point $(i,j,k)$ choose **random gradient** $\Gamma_{ijk}$
- using Array of precomputed Gradients $G[]$ & Hash-function $\phi()$:
$$\Gamma_{i,j,k}=G\left(\phi(i+\phi(j+\phi(k)))\right)$$
- interpolate with smoothstep function
$$s(x) = t^2(3-2t); \quad t=clamp(\frac{x-edge_0}{edge_1-edge_0}, 0, 1)$$
- turbulence = add noise on top of each other
$$n_t(x)=\sum_i \frac{|n(2^ix)|}{2^i}$$
![[Pasted image 20260324182011.png]]