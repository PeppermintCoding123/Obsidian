Chapter 16

# Syntax $\langle\mathcal{S, A, T, I, G}\rangle$
- $\mathcal{S}$ set of facts - welt Zustand
- $a \in \mathcal{A}: a = \langle pre_a, add_a, del_a\rangle$  - Action: preconditions, add, delete, $add_a \cap del_a = \emptyset$
- $\mathcal{T}(a, s):= (s\cup add_a)del_a$ if $pre_a \subseteq s$ - Transition model, undefined if wrong preconditions

### Relaxed
= ignore the delete => at diffarent location at 1 time