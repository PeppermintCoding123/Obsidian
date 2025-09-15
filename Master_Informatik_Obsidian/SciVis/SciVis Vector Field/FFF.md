= Feature Flow Field
define vector field $\mathbf{f}$ such that critical lines of $\mathbf{s}$ are streamlines of $\mathbf{f}$. 
=> critical point tracking in $\mathbf{v}$ = streamline integration in $\mathbf{f}$
$$\mathbf{f}(x, y, t) = \text{grad}(u) \times \text{grad} (v) = \begin{pmatrix}\det(\mathbf{v}_y, \mathbf{v}_t)\\
\det(\mathbf{v}_t, \mathbf{v}_x)\\
\det(\mathbf{v}_x, \mathbf{v}_y)\end{pmatrix}$$
for $$\mathbf{v}(x, y, t) = \begin{pmatrix}u(x, y, t)\\
v(x, y, t)\end{pmatrix}$$
![[Drawing FFF.excalidraw]]
[[Unsteady 2D Topology]]