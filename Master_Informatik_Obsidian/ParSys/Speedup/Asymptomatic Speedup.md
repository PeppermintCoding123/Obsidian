$$S_\infty := \frac{T(1)}{T(\infty)} = \frac{\sum_{i=1}^{m}W_i}{\sum_{i=1}^m \frac{W_i}{i}} = \frac{T_1}{T}$$
$T$ = responce times in case of 1 and $\infty$ Processors
$T(1) = \sum_{i=1}^{m}t_i(1) = \sum_{i=1}^{m}\frac{W_i}{\Delta}$
$T(\infty) = \sum_{i=1}^{m}\frac{W_i}{i \cdot \Delta}$



$W_i = i \cdot \Delta \cdot t_i$
- i = DOP = Wieviel arbeit gleichzeitig machen?
- t_i = für wieviele zeitschritte wird es gemacht
- delta = clock rate verhältnis, wie schnell arbeitet 1 prozessor vs der andere.

$W_i$ = sub-work of W that is executed with [[DOP]] = i

$t_i(k) = \frac{W_i}{k\cdot \Delta} (k \leq i)$ execution time of $W_i$

