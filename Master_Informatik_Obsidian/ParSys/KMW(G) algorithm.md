1. Build $G'$, the subgraph of [[zero-weight cycle]]s of $G$
2. Compute the s strongly connected components $G'_1, G'_2, ..., G'_s$ of $G'$
	- if $s = 0:$ $G'$ = empty $\rightarrow$ TRUE
	- if $s = 1$: $G'$ = strongly connected $\rightarrow$ FALSE
	- else: return $(KMW(G'_1) \wedge ... \wedge KMW(G'_s))$ 

$G$ is computable only if $KMW(G)$ returns TRUE