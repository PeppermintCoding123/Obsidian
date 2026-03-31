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
<span style="color:rgb(255, 221, 0)"><b>Correlation</b></span>
$$h[m,n]= \sum_{k,l} f[k,l] I[m+k, n + l]$$
`h = cv2.filter2D(f,I)`
- Commutative
- **NOT** Associative
### <span style="color:rgb(255, 221, 0)">Convolution</span>
$$*= h[m,n]= \sum_{k,l} f[k,l] I[m-k, n - l]$$
- take image filter, rotate 180° and do correlation (adding when sliding filter along)
- `h = cv2.filter2D(cv2.flip(f),I)`
- Commutative: $a * b = b * a$
- Associative: $a * (b * c) = (a*b)*c$
- Distributes over addition: $a*(b+c) = (a*b)+(a*c)$
- Scalars factor out: $ka * b = k(a*b)$
- Identity: unit impulse   $e = [0,0,1,0,0] => a*e = a$

# <span style="color:rgb(255, 221, 0)">Gaussian</span>
$$G_\sigma = \frac{1}{2\pi\sigma^2}exp(\frac{-(x^2+ y ^2)}{2 \sigma ^2})$$
- [[Low-pass filter]] 
	- = blur = remove high frequencies
- Gaussian times Gaussian = Gaussian
[[Gaussian Blur]]
## Separable
- convolve in 1 direction, then in 2. direction, instead of a 2D
$$G_\sigma(x, y) = \frac{1}{2\pi\sigma^2}exp(\frac{-(x^2+ y ^2)}{2 \sigma ^2}) = (\frac{1}{\sqrt{2\pi}\sigma}exp(\frac{-x^2}{2 \sigma ^2}))*(\frac{1}{\sqrt{2\pi}\sigma}exp(\frac{-y^2}{2 \sigma ^2}))$$
##### Complexity
$M\times N$ image & $P\times Q$ filter
- $O(MNPQ)$ for 2D convolution
- $O(MN(P+Q))$ for Separable 2D
# Box filter
- axis aligned artifacts
- computational simplicity
[[Box Filter]]

# <span style="color:rgb(255, 221, 0)">Sobel Filter</span>
$$G_x = \begin{bmatrix}   1 & 0 & -1\\
2 & 0 & -2\\
1 & 0& -1\end{bmatrix}, \quad G_y = \begin{bmatrix}   1 & 2 & 1\\
0& 0 & 0\\
-1 & -2& -1\end{bmatrix}$$
- Vertical & Horizontal Edges
- Get  [[Central Differences]]

# Non-Linear Filter

# <span style="color:rgb(255, 221, 0)">Median Filter</span>
- take average of stuff

# <span style="color:rgb(255, 221, 0)">Morphological Operators</span>

- Dilation => make foreground bigger
- Erosion => make foreground smaller
- Opening => Erosion + Dilation
- Closing => Dilation + Erosion
=> Clean up text in images

# CV03.2 Thinking in Frequency 

## Aliasing
- wrong wave pattern for actual pattern
- mecanically sample continous reality at regular grid
[[Aliasing with Fourier]]
### <span style="color:rgb(255, 221, 0)">Nyquist-Shannon Sampling Theorem</span>
When sampling at discrete intervalls, the sampling frequency must be $\geq 2 \times f_{max}$ 
=> sampling grid at least 2x as dense as actual frequency

#### Fix:
- remove too high frequencies / apply smoothing
- blur image & then sample [[Low-pass filter]]
	- Image pyramids

# CV03.3 Thinking in The Frequency Domain 2/2
- fourier series=> Any univariate function can be rewritten as a weighted sum of sines and cosines of different frequencies.
### Domains:
**Spacial = Temporal** => TD
**Frequency = Fourier** Domain => FD
$a\cdot \sin(p\cdot t)$
a= amplitude
p = phase = shift $2\pi f$ = changes frequency

**Square Wave spectra** = $A \sum_{f= 1}^{\infty} 1/f \sin(2\pi f t)$ 

# Fourier analysis images:
![[Drawing FourierImages.excalidraw]]
TD local => FD spread out
FD local => TD spread out

Fourier Transform = Basis transform
![[Pasted image 20250919151057.png]]
### $A = \pm \sqrt{Re(\phi)^2 + Im (\phi)^2 }$
<span style="color:rgb(255, 221, 0)">Amplitude</span> = magnitude of sin wave
### $\phi = \tan ^{-1}\frac{Im(\phi)}{Re(\phi)}$
<span style="color:rgb(255, 221, 0)">Angle/ Phase</span> = how much shifted to right

Translate image => Amplitude = unchanged, adds constant to phase

#### Properties Fourier Transform
- linear $F[ax(t)+by(t)]= aF[x(t)] + bF[y(t)]$
- symmetric about origin
- energy of signal = energy of Fourier transform

## Convolution Theorem
### $F[g*h]= F[g]F[h]$
Fourier transform of convolution = point wise multiplication of Fourier Transform of each individual
### $g*h=F^{-1}[F[g]F[h]]$
Convolution in spatial domain is equivalent to multiplication in frequency domain

#### Invert convolution:
- Fourier transform imags & divide by fourier transform of convolution filter & convert back


## JPEG
- Tile image into same size 8x8
- describe through Discrete Cosine Transform (variant of Fourier Transform)
- Only store most intense / brightest convolutions
- intencity separate from colours=> YCbCR
	- downsample Cb&Cr by 2




Afterwords here:
https://www.fau.tv/course/id/4224

Next: [[CV04 - Edges and Corners]]
CV - [[Computer Vision]] #ComputerVision 