= Mapping radiance values to screen RGS 
= map the radiance values to framebuffer values
- look at range of values
- determine tone-mapping function
- apply tone mapping function to all values and write resulting values to frame buffer or image file
or
- write image with radiance float values and use image viewer that selects a tone mapper that allows us to adapt tone mapping interactivally to choose best ons.

# simplest
- look for brightest solution
- scale all values sutch tahat brightest = 1

# ![[Naka-Rushton Equation]]
[[Global Illumination - overview.canvas]]