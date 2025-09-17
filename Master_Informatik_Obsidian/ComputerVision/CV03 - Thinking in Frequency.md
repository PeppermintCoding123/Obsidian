# CV03.1 Image Filtering
# Linear Filtering 
$f$ = filter function that you do stuff on
$m, n$ = Output pixels
$k, l$ = pixels surrounding $m , n$
$$h[m,n]= \sum_{k,l} f[k,l] I[m+k, n + l]$$
## Properties
**Linear**
``imfilter(I, f_1, f_2) = imfilter(I, f_1) + imfilter(I, f_2)``
**Shift invariant**
``imfiletr(I, shift(f)) = shift(imfilter(I,f))``
**Correlation**
$$h[m,n]= \sum_{k,l} f[k,l] I[m+k, n + l]$$
`h = cv2.filter2D(f,I)`
- Commutative
- **NOT** Associative
### Convolution
$$*= h[m,n]= \sum_{k,l} f[k,l] I[m-k, n - l]$$
- take image filter, rotate 180° and do correlation (adding when sliding filter along)
- `h = cv2.filter2D(cv2.flip(f),I)`
- Commutative: $a * b = b * a$
- Associative: $a * (b * c) = (a*b)*c$
- Distributes over addition: $a*(b+c) = (a*b)+(a*c)$
- Scalars factor out: $ka * b = k(a*b)$
- Identity: unit impulse$e = [0,0,1,0,0] => a*e = a$

# Gaussian
$$G_\sigma = \frac{1}{2\pi\sigma^2}exp(\frac{-x^2+ y ^2}{2 \sigma ^2})$$
- [[Low-pass filter]] 
	- = blur = remove high frequencies
- Gaussian times Gaussian = Gaussian
## Separable
- convolve in 1 direction, then in 2. direction, instead of a 2D
$$G_\sigma(x, y) = \frac{1}{2\pi\sigma^2}exp(\frac{-x^2+ y ^2}{2 \sigma ^2}) = (\frac{1}{\sqrt{2\pi}\sigma}exp(\frac{-x^2}{2 \sigma ^2}))*(\frac{1}{\sqrt{2\pi}\sigma}exp(\frac{-y^2}{2 \sigma ^2}))$$
##### Complexity
$M\times N$ image & $P\times Q$ filter
- $O(MNPQ)$ for 2D convolution
- $O(MN(P+Q))$ for Separable 2D
# Box filter
- axis aligned artifacts
- computational simplicity

# Sobel Filter
$$G_x = \begin{bmatrix}   1 & 0 & -1\\
2 & 0 & -2\\
1 & 0& -1\end{bmatrix}, \quad G_x = \begin{bmatrix}   1 & 2 & 1\\
0& 0 & 0\\
-1 & -2& -1\end{bmatrix}$$
- Vertical & Horizontal Edges
- Get  [[Central Differences]]

# Non-Linear Filter

# Median Filter
- take average of stuff

# Morphological Operators

- Dilation => make foreground bigger
- Erosion => make foreground smaller
- Opening => Erosion + Dilation
- Closing => Dilation + Erosion
=> Clean up text in images

# CV03.2 Thinking in Frequency 

## Aliasing
- wrong wave pattern for actual pattern
- mecanically sample continous reality at regular grid
### Nyquist-Shannon Sampling Theorem
When sampling at discrete intervalls, the sampling frequency must be $\geq 2 \times f_{max}$ 
=> sampling grid at least 2x as dense as actual frequency

#### Fix:
- remove too high frequencies / apply smoothing
- blur image & then sample [[Low-pass filter]]
	- Image pyramids

# CV03.3 Thinking in The Frequency Domain 2/2
#TODO
https://www.fau.tv/clip/id/52381
24 minutes

and the next videos
[[Dence Motion Estimation]] auch in 2024 lectures

Afterwords here:
https://www.fau.tv/course/id/4224
