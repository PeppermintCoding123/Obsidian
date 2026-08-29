T1
[[KMW(G) algorithm]]


T2
Loop Transformations
```
for i = 1 to N
	for j = 1 to i
		A[j] = A[j-1] * C[i,j-1]
	endfor
endfor
```
#### 1. Get A & b from loop
$$\mathcal{I} = \Big \{ \begin{pmatrix}i \\ j\end{pmatrix} | A \cdot \begin{pmatrix}i \\ j\end{pmatrix} \leq b \Big\}$$
hier $i \geq 1; i\leq N; j\geq 1; j\geq i$
$\begin{pmatrix}-1& 0 \\1 & 0\\ 0& -1 \\ -1 & 1\end{pmatrix} \begin{pmatrix}i \\ j\end{pmatrix} \leq \begin{pmatrix}-1 \\N \\ -1 \\0\end{pmatrix}$

#### 2. M mit A multiplizieren
$$A \cdot M^{-1} \cdot M\begin{pmatrix}i \\ j\end{pmatrix} \leq b \Leftrightarrow
A \cdot M^{-1} \begin{pmatrix}i' \\ j'\end{pmatrix} \leq b $$
#### 3. Gleichung für $i, j$ lösen & in algorithmus einsetzen
$$M  \begin{pmatrix}i \\ j\end{pmatrix}  = \begin{pmatrix}i' \\ j'\end{pmatrix}$$
