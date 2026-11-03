#TODO understand Herleitung
Do not parameterize along polar coordinates => infinitesimal solid angle do not have uniform size

#### polar coords
$\omega(\theta, \phi) = \begin{pmatrix}\sin\theta \cos \phi \\ \sin \theta sin \phi \\ cos \theta\end{pmatrix}$
$\int_{\Omega^+ } f(\omega) d\omega = \int_0^{\pi/2} \int_0^{2\pi} f(\omega(\theta, \phi))d\phi d\theta$ -NOOOOO
Do not parameterize along polar coordinates => infinitesimal solid angle do not have uniform size

#### radius
solid angle $d\omega = \sin \theta d\theta d\phi$
$\int_{\Omega^+ } f(\omega) d\omega = \int_0^{\pi/2} \int_0^{2\pi} f(\omega(\theta, \phi))\textcolor{cyan}{\sin \theta} d\phi d\theta$
![[Pasted image 20260829182355.png]]
#### height
$\omega(z, \phi) = \begin{pmatrix}\sqrt{1-z^2}\cdot \cos \phi \\ \sqrt{1-z^2}\cdot \sin \phi \\ z\end{pmatrix}$
$d\omega = d\phi dz$
$\int_{\Omega^+ } f(\omega) d\omega = \int_0^{1} \int_0^{2\pi} f(\omega(z, \phi)) d\phi dz$
![[Pasted image 20260829182150.png]]

[[Global Illumination - overview.canvas]]
[[03 - GI- Direct Illumination]]