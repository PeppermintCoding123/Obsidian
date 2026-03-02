Inference Rules of Hilbert Calculus $\mathcal{H}^0$: 

$$\frac{}{P\Rightarrow Q \Rightarrow P} K$$
$$\frac{}{(P\Rightarrow Q\Rightarrow R) \Rightarrow (P\Rightarrow Q) \Rightarrow P \Rightarrow R} S$$
$$\frac{A \Rightarrow B \; A}{B} MP$$
$$\frac{A}{[B/X](A)} Subst$$

Let $\mathcal{L}:= \langle \mathcal{L}, \mathcal{M}, \vDash \rangle$ logical system.
- $\exists (\mathcal{H}\vdash_{\mathcal{C}}A) \Rightarrow \mathcal{H}\vDash \mathcal{A}$ => $\mathcal{C}$ is [[Sound]] for $\mathcal{L}$
- $\mathcal{H}\vDash \mathcal{A} \Rightarrow \mathcal{H}\vdash_{\mathcal{C}}A$ => $\mathcal{C}$ is [[Complete]] for $\mathcal{L}$