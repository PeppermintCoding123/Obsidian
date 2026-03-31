$\mathcal{S}:= \langle \mathcal{L}, \mathcal{M}, \vDash\rangle$
- $\mathcal{L}$ = set of propositions
- $\mathcal{M}$ = set of Models
- $\vDash \subseteq \mathcal{M} \times \mathcal{L}$ satisfaction relation. 
	- $\mathcal{M}\vDash A$ => $\mathcal{M}$ satisfies $A$

Let $M \in \mathcal{M}$ and $A \in \mathcal{L}$:
- $M\vDash A \Rightarrow$ $A$ is satisfied by $M$
- $\exists M: M\vDash A \Rightarrow$ $A$ is satisfiable 
- $\nexists M: M\vDash A \Rightarrow$ $A$ is unsatisfiable
- $M \nvDash A\Rightarrow$ $A$ is falsified by $M$
- $\forall M \in \mathcal{M}: M\vDash A \Rightarrow$ $\vDash A$ , $A$ is valid/unfalsifiable
- $\exists M\in M: M \nvDash A \Rightarrow$ $\nvDash A$, $A$ is invalid/falsifiable

$\Rightarrow$ invalid $\subseteq$ unsatisfiable
$\Rightarrow$ satisfiable $\subseteq$ valid
(only $=$ if $|M| = 1$)

[[AI1-overview.canvas]]