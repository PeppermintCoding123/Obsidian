use less samples & weigh other samples accordingly

$$\int_0^1 f(x)dx \approx \frac{1}{n} \sum f(x_i) \approx \frac{1}{n} \sum \frac{f(x_i)w_i}{1-p_i}$$
with probability $p_i$ set $w_i = 0$, with $1-p_i$ set $w_i = 1$

=>
- no max path length
- for each bounce random number $\xi$
- $if (\xi < p)$ continue path & weigh with $1 / p$ 

Choose $p$ as amount of incident light that is reflected at point $x$


[[Path Tracing Basic Idear]]
[[GI 08 - Path Tracing]]
[[Path Tracing Pseudo code evolution]]
