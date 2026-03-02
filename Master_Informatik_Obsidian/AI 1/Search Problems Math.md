[[search problem]] 
$$\Pi :=\langle \mathcal{S}, \mathcal{A}, \mathcal{T}, \mathcal{I}, \mathcal{G}\rangle $$
[[state]]s $\mathcal{S}$ (set)
[[action]]s  $\mathcal{A}$ (set)
[[transition model]] $\mathcal{T}: \mathcal{A}\times \mathcal{S}\rightarrow \mathcal{P}(\mathcal{S})$ (abbild auf potenzmenge) $\mathcal{T}(a, s) = \mathcal{T}_a(s)$
[[goal state]] $\mathcal{G} \subseteq \mathcal{S}, \mathcal{G}\neq \emptyset$
[[initial state]]s $\mathcal{I} \subseteq \mathcal{S}$

[[applicable]]: $\mathcal{T}(a,s)\neq \emptyset \wedge \forall s' \in \mathcal{T}(a, s)$ is a result of applying $a$ to $s$ => $a \in \mathcal{A}$ applicable in $s \in \mathcal{S}$

result relation of a:  $\mathcal{T}_a: \mathcal{S}\rightarrow \mathcal{P}(\mathcal{}S)$
result relation of $\Pi$:   $\mathcal{T_A}: \cup _{a\in \mathcal{A}} \mathcal{T}_a$

state space induced by $\Pi$: $\langle \mathcal{S}, \mathcal{T_A}\rangle$ (graph)
[[solution]] of $\Pi$: $(a1, ..., a_n): \forall 1<i\leq n:$
	$a_i$ = applicable to $s_{i-1}$
	$s_0 \in \mathcal{I}$
	$s_i \in \mathcal{T}_{a_i}(s_{i-1})$
	$s_n \in \mathcal{G}$

[[cost function]] $c: \mathcal{A}\rightarrow \mathbb{R}_0^+$
step cost: $c(a)$
cost of solution $\sum_i c(a_i)$