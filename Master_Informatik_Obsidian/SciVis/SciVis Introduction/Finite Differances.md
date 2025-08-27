#TODO
= ...


# <span style="color:rgb(0, 176, 240)">Finite difference coefficient</span>
### <span style="color:rgb(0, 176, 240)">Forward differences</span>
$$f'(x) ≈ (f(x+h) − f(x)) / h$$
### <span style="color:rgb(0, 176, 240)">Backward differences</span>
$$f'(x) ≈ (f(x-h) − f(x)) / h$$
### <span style="color:rgb(0, 176, 240)">Central differences</span>
$$f'(x) ≈ (f(x+h) − f(x−h)) / (2h)$$

For all of them on <span style="color:rgb(0, 176, 240)"><b>2. derivative</b>:</span>
$$f''(x) ≈ [f(x−h) − 2f(x) + f(x+h)] / h^2.$$=> precomputed weights for 