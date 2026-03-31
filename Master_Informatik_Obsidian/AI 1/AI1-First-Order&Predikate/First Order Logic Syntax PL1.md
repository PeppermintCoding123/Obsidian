= [[Propositional Logic PL0]] with quantify over individuals
- troth with PL0
- individuals - number, cars, ...
# Signature
connectives $\sum_0 = \{T, F, \neg, \vee, \wedge, \Rightarrow, \Leftrightarrow, ...\}$
function constants : $\sum_k^f = \{f, g, h, ...\}$
predicate constants: $\sum_k^p=\{p, q, r, ...\}$
Skolem constants: $\sum_k^{sk}= \{f_k^1, f_k^2, ...\}$
$\sum_1 = \sum^f \cup \sum^p \cup \sum^{sk}$

Individual Variables $\mathcal{V}_\iota := \{X, Y, Z, ...\}$

# Syntax
Term $A\in wff_\iota(\sum_1, \mathcal{V}_\iota)$
- $\mathcal{V}_\iota \subseteq wff_\iota(\sum_1, \mathcal{V}_\iota)$
- if: $\forall f\in \sum_k^f, \forall i\leq k \; A^i \in wff_\iota(\sum_1, \mathcal{V}_\iota) \Rightarrow f(A^1, ..., A^k)$
First order propositions: $A \in wff_\sigma(\sum_1, \mathcal{V}_\iota)$
- if: $p\in \sum_k^p, \forall i\leq k A^i\in wff_\iota(\sum_1, \mathcal{V}_\iota) \Rightarrow p(A^1, ..., A^k)\in wff_\iota(\sum_1, \mathcal{V}_\sigma)$
- if: $A, B\in wff_\sigma(\sum_1, \mathcal{V}_\iota), X\in \mathcal{V}_\iota \Rightarrow T, A\wedge B, \neg A, \forall A. \in wff_\iota(\sum_1, \mathcal{V}_\iota)$
Seite 405 weiter

[[First Order Logic PL1]]
[[AI1-overview.canvas]]