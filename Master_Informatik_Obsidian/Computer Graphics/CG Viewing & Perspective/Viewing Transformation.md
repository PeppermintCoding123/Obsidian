$e$ = camera position
$a$ = look-at point
$g = a - e$ = viewing direction
$t$ = up-verctor

##### New Basis: $e$ = origin, $(u, v, w)$ = Basis Vectors
$w = -\frac{g}{||g||}$ 
$u = \frac{t\times w}{||t\times w||}$ 
$v = w\times u$
![[Pasted image 20260214172156.png]]
#### Viewing transformation 
$R = \begin{pmatrix}\vdots&\vdots&\vdots\\u&v&w \\ \vdots&\vdots&\vdots\end{pmatrix}$
$M_v = \begin{pmatrix}u_x&u_y&u_z & -u^T e\\v_x&v_y&v_z & -v^T e\\w_x&w_y&w_z & -w^T e\end{pmatrix}$


[[Computer Graphics - overview.canvas]]
[[CG Viewing & Perspective]]