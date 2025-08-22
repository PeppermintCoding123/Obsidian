#TODO
= ...


# Finite difference coefficient
### Forward differences
$$f'(x) ≈ (f(x+h) − f(x)) / h$$
### Backward differences
$$f'(x) ≈ (f(x+h) − f(x)) / h$$
### Central differences
$$f'(x) ≈ (f(x+h) − f(x−h)) / (2h)$$

For all of them on **2. derivative**:
$$f''(x) ≈ [f(x−h) − 2f(x) + f(x+h)] / h^2.$$=> precomputed weights for 