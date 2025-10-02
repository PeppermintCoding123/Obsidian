# Good
Compute L2 distance $D_{ij}$ between all frames
$$D_{ij} = ||I_i-I_j||_2$$
![[Drawing 2025-10-02 14.36.58.excalidraw]]
# Cost
$C_{i\rightarrow j} = D_{i+1,j}$
![[Pasted image 20251002142624.png]]
# Probabilities
$P_{i\rightarrow j} ~ exp(-C_{i\rightarrow j} / \sigma^2)$
- $\sigma$ = standard deviation of how many jumps appear
	- high $\sigma$ => jittery
	- low $\sigma$ => jump less
![[Drawing 2025-10-02 14.29.41.excalidraw]]


[[CPaC_Overveiw.canvas|CPaC_Overveiw]]