# CV02.1 Image
- $I = rand(256, 256)$
- Values = $256^{65\,536}$
- natural image - vs synthetic
- **Signal** = continuous to discrete later to continuous

## Sampling
- Pixel = Sample
- assume uniform sample density

## Photographs
- averages over specific areas
- <span style="color:rgb(24, 203, 21)">Quantization</span> = Mapping values to smaller set of discrete finite values

## <span style="color:rgb(24, 203, 21)">Resolution</span>
- = Sampling density across image
- = How many samples per image
- pixel density
- <span style="color:rgb(24, 203, 21)"><b>Geometric resolution</b></span>
	- mathematical how many samples distributed across image plane?
- <span style="color:rgb(24, 203, 21)"><b>Spatial Resolution</b></span>
	- Size of spacial features that you can still resolve in image = Content of Data, not how it is structured
	- Measured in degrees - how far black & white lines [[MTF - Modular Transfer Function]]
![[Pasted image 20250915185809.png]]
# CV02.2 Color 1
- additive Mixing => separate into RGB
- <span style="color:rgb(112, 155, 255)">im(down, right, color)</span> Channels
	- Also more than 8-bit
	- #OpenCV BGR, not RGB
- = perceptual quality, relative
## Eye
### Retina
= Film / sensor of eye
- Rod = light & dark
- Cones
### Sensitivity
400 (Violett) & 700 (Red) nanometers

### <span style="color:rgb(112, 155, 255)">Illuminance </span>
= light comming in

### <span style="color:rgb(112, 155, 255)">Reflectance spectra</span>
= Light comming out when reflecting white illuminant

## Physics
<span style="color:rgb(112, 155, 255)">Metamer </span>= 2 spectra with the same perceptual impression

# CV02.3 Color space
### Camera
<span style="color:rgb(112, 155, 255)"><b>Prims</b></span>
- Dicroatic prysim
- Basically 3 Black & White images of just 1 filtered light
<span style="color:rgb(112, 155, 255)"><b>Bayer filter</b></span>
- Measure what color is in front of you 
- Interpolate from the neighbors

## Default color space
This cube with black at the space we can not see
![[Pasted image 20250916184502.png]]
Other color spaces can decouple things

Add picture of all diffarent color spaces
![[Drawing 2025-09-16 colorspaces.excalidraw]]