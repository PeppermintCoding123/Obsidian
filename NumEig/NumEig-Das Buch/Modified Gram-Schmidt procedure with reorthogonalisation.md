NumEigNumerischeEigenwerte 
[[Numerical Methods for Eigenvalue Problems - Steffen Börn, Christian Mehl]]

[[Modified Gram-Schmidt procedure for vectors v1, .... , vm in F^n]]

begin
for $k \in \{ 1, \; ... \; , m\}$ do begin
	$q_k  \leftarrow v_k;$
	for $i \in \{ 1, \; ... \; , k-1\}$ do
		$r_{ik} \leftarrow \langle v_k\;; q_i\; \rangle ;$
		$q_k  \leftarrow q_k - r_{ik}q_i;$
	end
	for $i \in \{ 1, \; ... \; , k-1\}$ do
		$s_i \leftarrow \langle q_k\;; q_i\; \rangle ;$
		$q_k \leftarrow q_k - s_iq_i ;$
		$r_{ik} \leftarrow r_{ik} + s_i$
	end
	$r_{kk} \leftarrow  \|q_k\|;$
	if $r_{kk} = 0$ then
		STOP
	else
		$q_k \leftarrow \frac{1}{r_{kk}} q_k$
	end
end
