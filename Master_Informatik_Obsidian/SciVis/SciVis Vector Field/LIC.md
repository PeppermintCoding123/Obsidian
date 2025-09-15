= Line Integral Convolution

$$\mathrm{I}(\mathrm{x}_0) = \int_{-L/2}^{L/2}k(s)\cdot T(\mathrm{x}(s))ds, \quad s.t. \mathrm{x(0)= x_0}$$
$\mathrm{I}(\mathrm{x}_0)$ = intensity of pixel
$\mathrm{x}(s)$ = streamline traced in certain area
$s$ = arc length of streamline
$T$ = input texture
$k$ = constant filter kernel of length L

start at $x_0$ & random texture
follow stream line tangentially from there
sample noise along stream-line
average along values

=> low correlation intensity & neighboring lines
& hing correlation along lines

![[Pasted image 20250906124934.png]]