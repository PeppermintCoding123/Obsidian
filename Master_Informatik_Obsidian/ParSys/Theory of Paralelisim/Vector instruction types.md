- vecor-vector
- vector-scalar
- vector-memory (load/store)
- vector reduction
	$V_i \rightarrow s$ - extract scalar
	$V_i \times V_j \rightarrow s$ - min, max, sum, mean

Gather $M\times V_0 \rightarrow V_1$
- fetch from memory the non-zero elements of [[sparce]] vector
Scatter $V_1 \times V_0 \rightarrow M$
- write into a [[sparce]] vector
Masking $V_0 \times V_m \rightarrow V_1$
- use mask to compress or expand vector to shorter or longer index vector