
[[Generalized conjugate-gradient acceleration of nonsymmetrizable iterative methods]]
#NumEig
$u^{(n+1)}=u^{(n)}+\lambda_np^{(n)}$
$\lambda_n = (Y\delta^{(n)},Q^{-1}Ap^{(n)})/(YQ^{-1}Ap^{(n)},Q^{-1}Ap^{(n)})$
$p^{(0)}=\delta^{(0)}$
$p^{(n)}=\delta^{(n)}+\alpha_{n,n-1}p^{(n-1)}+...+\alpha_{n,n-s}p^{(n-s)}$
$\alpha_{n,i}=-(YQ^{-1}A\delta^{(n)},Q^{-1}Ap^{(i)}) / (YQ^{-1}Ap^{(i)},Q^{-1}Ap^{(i)})$

#### Orthomin(k)
see [[Variational iterative methods for nonsymmetric systems of linear equations]]
Algorithm 2.2.
Choose $x_0$    (a)
$r_0 = f-Ax_0$    (b)
$p_0 = r_0$    (c)
For $i=0$ step $1$ until Convergence Do
$a_i = (r_i,Ap_i)/(Ap_i,Ap_i)$    (d)
$x_{i+1} = x_i + a_ip_i$    (e)
$r_{i+1}=r_i-a_iAp_p$    (f)

$b_j^{(i)}= (Ar_{i+1},Ap_j)/(Ap_j,Ap_j) \quad j\leq i$
$p_{i+1}=r_{i+1} + \sum_{j=i-k+1}^ib_j^{(i)}p_j$


Diffarent from [[Orthodir]] in $\alpha$ and $p^{(n)}$





## Further Reading:
Vinsome, P.K.W.: "Orthomin, an Iterative Method for Solving Sparse Sets of Simultaneous Linear Equations," paper SPE 5729 presented at the 1976 SPE Symposium of Numerical Reservoir Simulation of Reservoir Performance, Los Angeles, 19-20 February.
https://onepetro.org/SPENSS/proceedings-abstract/76NSS/All-76NSS/138793
#NumEig Not jet done.

Now: 
# A variant algorithm of the Orthomin(_m_) method for solving linear systems
Kuniyoshi Abe, Shao-Liang Zhang 
https://www.sciencedirect.com/science/article/pii/S0096300308006267