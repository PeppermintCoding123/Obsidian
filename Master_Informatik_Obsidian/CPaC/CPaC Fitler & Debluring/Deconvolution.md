= ill posed problem: 
**find $x$ such that $f*x = y$**
f = filter
x = origional image
y = blured Image


=> Penalty on Gradient to avoid unnatural Images
![[Pasted image 20251002121737.png]]
### Deconvolution with prior
$$x = arg min  \quad |f*x-y|^2 +\lambda \sum_i \rho(\nabla x_i)$$
$\lambda$ = Weight
$\sum_i \rho(\nabla x_i)$ = Derivatives prior
$|f*x-y|^2$ = Convolution error

prefered $\rho(\nabla x) = ||\nabla x||^{0.8}$ because penalize small gradients more & localize
instead of $\rho(\nabla x) = ||\nabla x||^{2}$
![[Pasted image 20251002122519.png]]

[[CPaC_Overveiw.canvas|CPaC_Overveiw]]