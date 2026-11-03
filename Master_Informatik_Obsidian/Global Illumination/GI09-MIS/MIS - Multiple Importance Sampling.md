![[Drawing importance sampling.excalidraw]]

# Problem: Glossy BRDF, <span style="color:rgb(0, 176, 240)">large light source</span>
- high variance BRDF => <span style="color:rgb(0, 176, 240)">good to sample BRDF</span>
- low variance light => bad to sample light
# Problem: <span style="color:rgb(120, 120, 120)"><span style="color:rgb(120, 120, 120)">Diffuse BRDF,</span></span> <span style="color:rgb(255, 138, 185)">small light source</span>
- low variance BRDF => bad to sample BRDF
- high variance ligh => <span style="color:rgb(255, 138, 185)">good to sample light</span> 

# 1. use both sampling strategies and weigh
- small weights for samples that result in high variance
- large weights for good samples
$Var(\frac{E_1 + E_2}{2}) = \frac{Var(E_1) + Var(E_2)}{2}$
=> Average of Estimates still has high variance if 1 ha high variance

# 2. Split integrand to weighted sum
$f(x)g(x) = F(x) = F(x)w_1(x) + F(x)w_2(x) = F_1(x) + F_2(x)$
$$w_1(x) = \frac{p_1(x)}{p_1(x) + p_2(x)} \quad w_2(x) = \frac{p_2(x)}{p_1(x) + p_2(x)}$$
if p is small, the integrand should be small

integrate $F_1$ with regards to $p_1$, since this is a good PDF for $F_1$

$$E = \frac{1}{n} \sum \frac{F_1(x-i)}{p_1(x_i)} + \sum \frac{F_2(x-i)}{p_2(x_i)}$$
## More General:
We have i = 1 ... N importance sampling strategies, generating samples according to PDFs pi . With each strategy i, we draw j = 1 ... ni samples X i,j
$$\int F(x)dx \approx \sum_{i= 1}^N \frac{1}{n_i} \sum_{j= 1}^{n_i}\frac{w_i (X_{i,j}) F(X_{i,j})}{p_i(X_{i,j})}$$
### implement $w_i(x)$
Try: as balance heuristic
$$w_i(x) = \frac{n_i p_i(x)}{\sum n_j p_j(x)} \Longrightarrow \int F(x)dx \approx \frac{1}{n} \sum_{i= 1}^N  \sum_{j= 1}^{n_i}\frac{ F(X_{i,j})}{p(X_{i,j})}$$
with $n = \sum n_i$ and $p(x) = \sum_{i= 1}^N \frac{n_i}{n} p_i(x)$
=> build combined PDF that draws samples by drawing samples for each $p_i$

Try: 
$$w_i(x) = \frac{(n_i p_i(x))^\beta}{\sum (n_j p_j(x)) ^\beta} $$
$\beta = 2$ often chosen 