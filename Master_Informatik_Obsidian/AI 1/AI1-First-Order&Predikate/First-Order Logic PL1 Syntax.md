# Signature $\sum_1$:
connectives: $\sum_0 = \{T, F, \neq, \wedge, \vee, \Rightarrow, \Leftrightarrow, ... \}$
function constants: $\sum_k^f = \{f, g, h, ...\}$
predicate constants: $\sum_k^p = \{p, q, r, ...\}$
	- isPrime
	- isBlond
	- Properties & relations
Skolem constants: $\sum_k^{sk} = \{f_k^1, f_k^1, ...\}$
$\sum_1 := \sum^f \cup \sum^p \cup \sum^{sk}$

### Variables $\mathcal{V}_\iota :=\{X,Y, Z, ...\}$
### Term 
$A\in wff_\iota(\sum_1, \mathcal{V}_\iota)$
- $\mathcal{V}_\iota \subseteq wff_\iota(\sum_1, \mathcal{V}_\iota)$ - Constants & Variables
- if $f\in \sum_k^f$, $\forall i\leq k : A^i \in wff_\iota(\sum_1, \mathcal{V}_\iota) \Rightarrow f(A¹, ..., A^k)\in wff_\iota(\sum_1, \mathcal{V}_\iota)$ - Functions applied to constants
### First-order propositions
$A \in wff_\sigma(\sum_1, \mathcal{V}_\iota)$
- $p\in\sum_k^p, \forall i\leq k: A^i \in wff_\iota(\sum_1, \mathcal{V}_\iota) \Rightarrow p(A^1, ..., A^k)\in wff_\sigma(\sum_1, \mathcal{V}_\iota)$
- $A, B \in wff_\sigma(\sum_1, \mathcal{V}_\iota). X \in \mathcal{V}_\iota \Rightarrow T, A\wedge B, \neg A, \forall X .A \in wff_\sigma(\sum_1, \mathcal{V}_\iota)$

[[First Order Logic PL1]]

[[AI1-overview.canvas]]