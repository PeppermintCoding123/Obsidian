= Inverse distance Weighting
(not explicit topology)

<span style="color:rgb(0, 176, 240)">weights: </span>
$$w_i(x) = \frac{1}{d(x, x_i)^p}$$
<span style="color:rgb(0, 176, 240)">if </span>$d(x,x_i) \neq 0 \forall i$
$$\frac{\sum_{i=1}^{n} w_i(x)\cdot a_i}{\sum_{i=1}^{n} w_i(x)}$$
<span style="color:rgb(0, 176, 240)">if </span>$\exists i : d(x,x_i) = 0$
$$a_i = a(x_i)$$
#TODO: wie actually das verwänden