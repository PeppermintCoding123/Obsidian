See [[Variational iterative methods for nonsymmetric systems of linear equations]]
#NumEig #KrylovSubspace 

Algorithm 2.2.
Choose $x_0$    (a)
$r_0 = f-Ax_0$    (b)
$p_0 = r_0$    (c)
For $i=0$ step $1$ until Convergence Do
$a_i = (r_i,Ap_i)/(Ap_i,Ap_i)$    (d)
$x_{i+1} = x_i + a_ip_i$    (e)
$r_{i+1}=r_i-a_iAp_p$    (f)

$p_{i+1}=r_{i+1} + \sum_{j=0}^ib_j^{(i)}p_j$
$b_j^{(i)}= (Ar_{i+1},Ap_j)/(Ap_j,Ap_j) \quad j\leq i$
$x_{i+1}$ minimize $E(w)$ over $x_0+\langle p_0,...,p_i\rangle$ 