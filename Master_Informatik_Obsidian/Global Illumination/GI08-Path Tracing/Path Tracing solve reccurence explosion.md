# 1. Use direct illumination
$L_{dir} = \int F L_e$

$L = L_e + L_{dir} + \frac{1}{n} \sum F(x_i)(L_{dir} + \frac{1}{n} \sum F(y_i)(L_{dir} + ...))$
=> Separate direct & Indirect light

# 2. Consider higher dimensional Integral 
- each sample of higher dimensional integral = a complete ray = path $(x_i, y_i, z_i)$
$L_e(x_i) + F(x_i, y_i)L_e(y_i) + F(x_i, y_i)F(y_i, z_i)L_e(z_i) + ...$

![[Pasted image 20260911090010.png]]
- 2N random samples for each path
	- 2 samples to determine a direction
	- 2N-dimensional integration

![[Pasted image 20260911085943.png]]

[[Global Illumination - overview.canvas]]