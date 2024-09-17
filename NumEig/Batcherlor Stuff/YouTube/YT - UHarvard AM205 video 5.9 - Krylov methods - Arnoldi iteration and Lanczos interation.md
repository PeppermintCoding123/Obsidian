 #NumEig
https://www.youtube.com/watch?v=2Y1ZDQw_2zw&t=783s

Krylov-Method overview

#ArnoldiIteration 
H is upper-Hessenberg if $a_{ij}=0 \; \forall i>j+1$
H is lower-Hessenberg if $a_{ij}=0 \; \forall i<j+1$
=> use simpler form of H

let $A\in \mathbb{C}^{\;n\times n}$ $=QHQ^*$, $H$ Hessenberg, $Q$ unitary

first $m<<n$ columns of $AQ=QH$
need $Q_m = [q_1|q_2|...|q_m ]$ $\mathbb{C}^{\;n\times m}$
need $\tilde{H}_m = \begin{bmatrix}h_{11} & \dots & \dots & h_{1n} \\ h_{21} & h_{22} & \ddots & \vdots \\ 0 & \ddots & \ddots & \vdots \\ \vdots & \ddots & h_{m,m-1} & h_{mm} \\ 0 & \dots & 0 & h_{m+1,m} \end{bmatrix}$
=> $AQ_m = Q_m\tilde{H}_m$

especially: $Aq_m = h_{1m}q_m+... + h_{mm}q_m+h_{m+1,m}q_{m+1}$
equivalently: $q_m+1 = (Aq_m-h_{1m}q_1-...-h_{mm}q_m)/h_{m+1,m}$

choose $b$ arbitrarily
$q_1 = b/||b||_2$
for $m$ = 1,2,3,... do
	$v =Aq_m$
	for $j$ = 1,2,...,m do
		$h_{jm} = q_j^*v$
		$v=v-h_{jm}q_j$
	end 
	$h_{m+1,m} = ||v||_2$
	$q_{m+1} = v/h_{m+1,m}$
end

like modified GS

$q_j$ are orthonormal basis

#### How to find the Eigenvalues of Arnoldi iteration?
Let $H_m = Q_m^*AQ_m$ removing last row of $\tilde{H}_m$
At each step we compute eigenvalues of $H_m$ z.B. via QR
is estimate for Ritz values - extreme eigenvalues of $A$

introduction optimal polynomial $p$

#LanczosAlgorithm

great implementation of this but nothing to Arnoldi