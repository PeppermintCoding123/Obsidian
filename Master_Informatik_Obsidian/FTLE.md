= finite-time Lyapunov exponent

### flow map
$$\phi_t^\tau(\mathrm{x})=\mathrm{x} + \int_t^{t+\tau}\mathrm{v}(\mathrm{x}'(t),t)dt, \quad s.t. \mathrm{x}'(t)= \mathrm{x}$$
$t$ = start time
$\tau$ = Integration duration
$\mathrm{x}$ = start position
#### flow map gradient
$$\nabla \phi(\mathrm{x}) = (\phi_x\; \phi_y)(\mathrm{x})= 
\begin{pmatrix}\frac{\phi_t^\tau(\mathrm{x}_{i+1,j}) - \phi_t^\tau(\mathrm{x}_{i-1,j})}
{||\mathrm{x}_{i+1, j}-\mathrm{x}_{i-1,j}||}&
\frac{\phi_t^\tau(\mathrm{x}_{i,j+1}) - \phi_t^\tau(\mathrm{x}_{i,j-1})}
{||\mathrm{x}_{i, j+1}-\mathrm{x}_{i,j-1}||}\end{pmatrix}$$
= finite differences of right & left and top and bottom of point

#### Cauchy-Green tensor $\mathbf{C}$
$$\mathbf{C} = \Delta = \nabla \phi_t^\tau(\mathrm{x})^T\nabla \phi_t^\tau(\mathrm{x})$$
- must be symmetric
=> [[EW]] of tensor: $\lambda_1<\lambda_2$

# FTLE
$${FTLE}(\mathrm{x}, t, \tau) = \frac{1}{|\tau|} \ln\sqrt{\lambda_{max}(\Delta)} = \frac{1}{|\tau|} \ln\sqrt{\lambda_{max}(\nabla \phi_t^\tau(\mathrm{x})^T\nabla \phi_t^\tau(\mathrm{x}))}$$
- $\tau = +$=> forward-FTLE = $FTLE+$ =>  repelling structures
- $\tau = -$=> backward-FTLE = $FTLE-$ =>   attracting structures