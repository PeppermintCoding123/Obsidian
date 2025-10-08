- - Meteriang adjustmensts
- <span style="color:rgb(0, 176, 240)">Iso</span>
	- Analog amplification process - Digital cameras
	- no sensitivity on digital cameras
	- camera chips have some noise
- Sensitivity - Film crystals
	- big critals -course image  - sensitive film 3200 sensitive
	- slower dev film cristal - 100 - high quality 
- Color
	- <span style="color:rgb(0, 176, 240)">CMOS</span> - Infra red
	- prisim
	- Mosaik
- Geometric distortion
	- Spherical - apature
	- Asigmatisim - Change focal lenth
	- R - pin, barral
	- Croma - apature
- <span style="color:rgb(0, 176, 240)">CCD</span> - Charge Couple Devices
	- Colomb
	- Interline & Frame 
- <span style="color:rgb(0, 176, 240)">CMOS</span>
	- phones
	- each pixel own amplifier

Composition & Blending
- <span style="color:rgb(112, 155, 255)">Alpha Hacking</span> - Gradient of where to place what alpha
- <span style="color:rgb(112, 155, 255)">Setteling Alpha - Gradient Distance Transform</span> 
	- ![[Pasted image 20251008162441.png]]
	- Window size = size of largest prominent feature
- Blending regions - Fourier domain blending, average out
- <span style="color:rgb(112, 155, 255)">Pyramid Blending - Dowsampling recursively</span> 
- Oktaves - 
- 2 Ban Blending 
- Gradient domain blending - Differenciate, blend, go back
- Poisson blending - also blend colour

<span style="color:rgb(255, 133, 133)">Poisson equasion</span> - seamless cloning #TODO equasion
- matching intencity gradients => colour shifts of forgrouns
- membrane into boundary
- Target Images not changed
![[Pasted image 20251008170737.png]]

<span style="color:rgb(255, 133, 133)">Segmenting</span>
- <span style="color:rgb(255, 133, 133)">Overlap error</span> $(I_0-I_1)^2$

Avoid Ghosting
- seamless pixel blend
- avoid artifacts along boundary - blend seamlessly 

Matting for Video
- Greenscreen acting - costfunction form movement is much more complicated

Composition & Blending
Inverse Rendering problem - where is light comming from?
Appearence
	- Shape, surface structure, relfectance
	- Macro
	- Messo
	- Micro

## Radients
Radient flux - power emitted per unit time
Radient intecity - power per solid eangle
Light flux - power emitted in solid angel


## Debluring
- blind deconvolution
	- ![[Pasted image 20251002130406.png]]

## Video
Morphing - combining
Crossfading - frame by frame