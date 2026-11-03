1. we want to integrate function that is uniform?
	- uniform random sampling, evaluate & take largest?
	- sample more there where the functin is largest, since this contributes most
		- Better convergence
		- less noise, or same with less samples
2. integrate non-uniform distributed functions
	- find PDF $p(x)$, such that $\int p(x) dx = 1$ 
	- => accumulate where function is highest => weights in Monte-Carlo integration
	- ![[Drawing Monte-Carloe-Wieghting samples.excalidraw]]
	- $\sum_i \frac{f(x_i)}{p(x_i)}$
3. How to choose samples? [[Inversion Method]]
	- probability of the sample left of x: so $[-\infty, x]$
	- $P(x) = \int_{-\infty}^x p(x') dx'$
	- ![[Drawing Dencity Sampling.excalidraw]]
	- => $P^{-1}(\xi) = x$
	- use this as x in $\sum_i \frac{f(x_i)}{p(x_i)}$


[[Global Illumination - overview.canvas]]