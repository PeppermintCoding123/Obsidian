#NumEig 
[[Numerical Methods for Eigenvalue Problems - Steffen Börn, Christian Mehl]]

[[Gram-Schmidt procedure for vectors v1, .... , vm in F^n]]

begin
for $k \in \{ 1, \; ... \; , m\}$ do begin
	$q_k  \leftarrow v_k;$ 
	for $i \in \{ 1, \; ... \; , k-1\}$ do
		$r_{ik} \leftarrow \langle v_k\;; q_i\; \rangle ;$
		$q_k  \leftarrow q_k - r_{ik}q_k;$
	end
	$r_{kk} \leftarrow  \|q_k\|;$
	if $r_{kk} = 0$ then
		STOP
	else
		$q_k \leftarrow \frac{1}{r_{kk}} q_k$
	end
end

"We remark that the modified Gram–Schmidt process is, philosophically speaking, an application of the idea of the Gauss–Seidel sweep used for iteratively solving linear systems."
[[Motivations and realizations of Krylov subspace methods for large sparse linear systems]] Section 2