Von der Bib, siehe PDF-download

Arnoldi:
Choose a vector $v_1$ such that $||v_1||_2 = 1$
For $j \in 1,2,...,m$ do:
	$h_{i,j} = (Av_j,v_i)$ for $i = 1,2,..,j$
	$w_j = Av_j - \sum_{i=1}^j h_{ij}v_i$
	$h_{j+1,j} = ||w_j||_2$
	If $h_{j+1,j} = 0$ stop
	$v_{j+1} = w_j/h_{j+1,j}$

# 6.4 Arnoldi’s Method for Linear Systems
full orthogonalization method (FOM)
Compute $r_0 = b − Ax_0$, $\beta := ||r_0||_2$, and $v_1 := r_0/\beta$
Deﬁne the $m \times m$ matrix $H_m = \{h_{ij} \}_{i,j=1,...,m}$; Set $H_m = 0$
For $j = 1, 2, . . . , m$, Do
	Compute $w_j := Av_j$
	For $i = 1, . . . , j$, Do
		$h_{ij} = (w_j , v_i)$
		$w_j := w_j − h_{ij} v_i$
	 EndDo
	 Compute $h_{j+1,j} =||w_j||_2$. 
	 If $h_{j+1,j} = 0$ set $m := j$ and go to end
	Compute $v_{j+1} = w_j /h_{j+1,j}$
EndDo
Compute $y_m = H_m^{−1}(\beta e_1)$ and $x_m = x_0 + V_my_m$

#### GMRES
Compute $r_0 = b − Ax_0$, $\beta := ||r_0||_2$, and $v_1 := r_0/\beta$
For $j = 1, 2, . . . , m$, Do
	Compute $w_j := Av_j$
	For $i = 1, . . . , j$, Do
		$h_{ij} = (w_j , v_i)$
		$w_j := w_j − h_{ij} v_i$
	 EndDo
	 Compute $h_{j+1,j} =||w_j||_2$. 
	 If $h_{j+1,j} = 0$ set $m := j$ and go to second last line
	Compute $v_{j+1} = w_j /h_{j+1,j}$
EndDo
Define $(m+1) \times m$ Hessenberg matrix $\widetilde{H}_m$ $= \{h_{ij}\}_{1\leq i \leq m+1, \; 1 \leq j \leq m}$
Compute $y_m$ minimizes $||\beta e_1-\widetilde{H}_my||_2$and $x_m = x_0 + V_my_m$



[[Krylov Subspace Methods for Linear Systems - Tomohiro Sogabe]]
# Eigenleistung
Assume we have Arnoldi with $i+1\times i$ Hessenberg $\widetilde{H}_i$ and $y_k$ minimizes $J(y)= ||\;||r_0|| e_1 - \widetilde{H}_k y||$
$J(y)= ||\beta e_1 - \overline{H}_k y|| = ||V_{k+1}[\beta e_1 - \overline{H}_k y]|| = ||\beta v_1 - AV_k y|| = ||\beta v_1 - V_k^*H_kV_k y||$
Assume $A$ is Hermetian (meaning $A = A^*$ and can have negative EIgenvalues. Hermetian = self-adjoint)
$\Longrightarrow$ $\widetilde{H}_i = V_{i+1}^TAV_i$ is self-adjoint => $\exists$ gaiussian elimination of $\widetilde{H}_i$ without partial pivoting:  $H_i = L_iU_i$