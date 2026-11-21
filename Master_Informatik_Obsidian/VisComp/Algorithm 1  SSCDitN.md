Numerical time integration procedure.

# Input:
$q_v \leftarrow (q_v (x , t_0 ))_{x \in \Omega} , q_c \leftarrow (q_c (x , t_0))_{x \in \Omega} , q_r \leftarrow (q_r (x , t_0 ))_{x \in \Omega}$
$θ \leftarrow (θ (x , t_0 ))_{x \in \Omega} , u \leftarrow (u(x , t_0))_{x \in \Omega} , t \leftarrow t_0$
# Procedure:
$u ← \text{advect}(u, ∆t )$ //advect velocity field -> 4.3
$u ← \text{diffuse}(u, ν, ∆t )$ //include viscosity as diffusion process -> 4.3
$ω ← ∇ × u$ //compute vorticity field
$f_\omega ← ε · ∆x · (\text{normalize}(∇ ∥ω ∥) × ω)$ //vorticity confinement
$u ← u + f_ω · ∆t$ //apply vorticity confinement force
$b ← (0, 0, B)^T$ //compute buoyancy according to [[(15) SSCDitN]]
$f ← \text{getExternalForce}(t)$ //compute external net force
$u ← u + (b + f ) · ∆t$ //apply buoyancy and external force ([[(20) SSCDitN]]?)
$∇p ← project(∇ · u, ∆t )$ //pressure projection
$u ← u − ∇p · ∆t$ //pressure update
$[θ, q_v , q_c , q_r ] ← \text{advect}(θ, q_v , q_c , q_r , u, ∆t )$ //[[advection]] quantities
$q_{v s} ← \text{getSaturationRatio}(\text{getAbsoluteTemperature}(θ ), p_∞ )$ //see
[[(16) SSCDitN]] and Eq. (28)
$q_v ← q_v + \min(q_{v s} − q_v , q_c ) + E_r$
$q_c ← q_c − \min(q_{v s} − q_v , q_c ) − A_c − K_c$ #Question(why min here?)
$q_r ← q_r + A_c + K_c − E_r$
$X_v ← \text{getMoleFraction}(q_v )$ //see Eq. (9)
$\mathcal{M}_{th} ← \text{getAverageMolarMass}(X_v )$ //see Eq. (7)
$\gamma_{th} ← \text{getIsentropicExponent}(X_v \mathcal{M}_W /\mathcal{M}_{th} )$ //see [[(11) SSCDitN]]
$c_p^{th} ← \text{getHeatCapacity}(\gamma_{th}, \mathcal{M}_{th} )$ //see [[(18) SSCDitN]]
$θ ← θ + L/c_p^{th} · \text{getMoleFraction}(−\min(q_{vs} − q_v , q_c ))$ //see Eq. (9) [[(21) SSCDitN]]
$t_1 ← t_0 + ∆t$

# Output:
$q_v ← (q_v (x , t_1 ))_{x ∈Ω} , q_c ← (q_c (x , t_1))_{x ∈Ω} , q_r ← (q_r (x , t_1 ))_{x ∈Ω}$
$θ ← (θ (x , t_1 ))_{x ∈Ω} , u ← (u(x , t_1))_{x ∈Ω} , t ← t_1$
