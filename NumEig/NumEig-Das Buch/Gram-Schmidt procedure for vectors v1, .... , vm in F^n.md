#NumEig
[[Numerical Methods for Eigenvalue Problems - Steffen Börn, Christian Mehl]]

begin
for $k \in \{ 1, \; ... \; , m\}$ do begin
	for $i \in \{ 1, \; ... \; , k-1\}$ do
		$r_{ik} \leftarrow \langle v_k\;; q_i\; \rangle ;$
	$q_k  \leftarrow v_k;$
	end
	for $i \in \{ 1, \; ... \; , k-1\}$ do
		$q_k \leftarrow q_k - r_{ik}q_i ;$
	$r_{kk} \leftarrow  \|q_k\|;$
	end
	if $r_{kk} = 0$ then
		STOP
	else
		$q_k \leftarrow \frac{1}{r_{kk}} q_k$
	end
end

