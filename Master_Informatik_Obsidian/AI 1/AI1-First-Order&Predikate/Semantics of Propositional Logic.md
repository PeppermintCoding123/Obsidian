# Models
$\mathcal{M}:=\langle \mathcal{D}_0, \mathcal{I}\rangle$ model of [[Propositional Logic PL0]]
$\mathcal{D}_0=\{T, F\}$ universe
$\mathcal{I}$ interpretation that assigns values to essential connectives

Example: $\mathcal{I}(\neg): \mathcal{D}_0 \rightarrow \mathcal{D}_0; T\mapsto F, F\mapsto T$

logical constant => a constant whose value is fixed by interpretation

# Evaluation
= what the formulaes mean
$\varphi:\mathcal{V}_0 \rightarrow \mathcal{D}_0$ **variable assignment** assigns values to propositional variables
$\mathcal{I}_\varphi(), [[]]_\varphi:wff_0(\mathcal{V}_0)\rightarrow \mathcal{D}_0$ **value function** assigns values to PL0 formulae recursively
- $\mathcal{I}_\varphi(P) = \varphi(P)$
- $\mathcal{I}_\varphi(\neg A)= \mathcal{I}(\neg)\mathcal{I}_\varphi(A)$
- $\mathcal{I}_\varphi(A\wedge B)= \mathcal{I}(\wedge)\mathcal{I}_\varphi(A), \mathcal{I}_\varphi(B)$

$\forall \varphi: \mathcal{I}_\varphi(A) = \mathcal{I}_\varphi(B) \Longrightarrow A \Leftrightarrow B$ equivalent formulae 

[[Semantics]]
[[AI1-overview.canvas]]
[[Propositional Logic PL0]]