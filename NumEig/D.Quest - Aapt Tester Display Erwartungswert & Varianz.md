#NumEig 
# Bei LinearSystemSolver.py
### Erwartungswert:
https://de.wikipedia.org/wiki/Erwartungswert
Definiert: $\mu$ 
I want to look at "Erwartungswert einer diskreten reellen Zufallsvariable",  because we have $loops$ amount of numbers that we take the average of.
Calculated for each of the 19 Points: $\mathbb{E}(X) = \sum_{i\in I}x_ip_i = \sum_{i\in I} x_i P(X=x_i) = \mu$ 
with $x_i$ being the error-norm `np.abs(np.linalg.norm(np.subtract(x_C, x), axis=1))`
and $p_i$ being the probability of the specific rum: `(1 / loops)`

=> already there as `accumulated_error_...`

### Varianz:
https://de.wikipedia.org/wiki/Varianz_(Stochastik)
Auch Standardabweichung oder Zentrales Moment
$Var(X)=\mathbb{E}((X-\mu)^2) = \int_\Omega(X-\mu)^2dP= \mathbb{E}(X^2)-\mu^2 = \sigma^2$


Hier haben wir diskrete Gleichverteilung mit $p_i$ = `1/loops`
=> Varianz bei diskreten Zufallsvariablen:
= gewichtete Summe der Abweichungsquadrate (vom Erwartungswert)
$\sigma^2 = \sum_{i>=1}(x_i-\mu)^2p_i$

=> this can be calculated after the loops are done, before displaying the graph. I will need:
- the results of the solvers minus the acctual result `x_LSTSQ,x_GMRES,x_GCR_k`
- the expectations calculated after finishing all loops, also known as `accumulated_error_...`
- there will be a variance for each algorithm, that holds the 

1. Save norms of errors in blocks
2. calculate the accumulated error as before, but now from the norm blocks and name exp_...

See: https://numpy.org/doc/stable/reference/generated/numpy.var.html
```
import numpy as np
>>> a = np.array([[1, 2], [3, 4]])
>>> np.var(a)
1.25
>>> np.var(a, axis=0)
array([1.,  1.])
>>> np.var(a, axis=1)
array([0.25,  0.25])
```
compute as follows:
```
N = len(a)
d2 = abs(a - mean)**2  # abs is for complex `a`
var = d2.sum() / (N - ddof)  # note use of `ddof`
```

=> wir kommen auf 1^9 >( für die Varianz
könnte an dem np.abs liegen... 

