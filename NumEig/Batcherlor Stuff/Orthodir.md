[[Generalized conjugate-gradient acceleration of nonsymmetrizable iterative methods]]

#NumEig
$u^{(n+1)}=u^{(n)}+\hat{\lambda}_nq^{(n)}$
$\hat{\lambda}_n = (Y\delta^{(n)},Q^{-1}Aq^{(n)})/(YQ^{-1}Aq^{(n)},Q^{-1}Aq^{(n)})$
$q^{(0)}=\delta^{(0)}$
$q^{(n)}=Q^{-1}Aq^{(n-1)}+\beta_{n,n-1}q^{(n-1)}+...+\beta_{n,n-s}q^{(n-s)}$
$\beta_{n,i}=-(Y(Q^{-1}A)^2q^{(n-1)},Q^{-1}Aq^{(i)}) / (YQ^{-1}Aq^{(i)},Q^{-1}Aq^{(i)})$
