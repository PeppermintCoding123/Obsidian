# Multi-View geometry Problem
Structure
- multiple cameras & points on Object
- We know the R & t of the cameras
Motion
- finding extrinsic poistion of camera
Optical Flow
Stereo Correspondence
- Epipolar lines projected onto image plane

### Stereo Vision
Goal: infer information from $\geq 2$ viewpoints
Correspondence problem:
- What are the same points?
Reconstruction Problem:
- Once points are found, what do we do with them?
#### Disparity
= distance from projection of converging point to other projection points
=> see Computational Visual Perception

Scanline = Epipolar line that is alighened with image grid

### ![[Triangulation]]
#### Baseline
Small => large depth error
Large => hard to find correspondences

#### Vergence
- turn cameras towards each other 

=> 
#### Image Rectification
- 2 Cameras & image planes of those 2 Cameras do not ley on 1 Plane
- => Project both images onto 1 Plane (Projective Mapping)

## Correspondence Problem
(finding same point in 2 Images)
Assume: 
- most points on both
Ask:
- What match?
- How measure similarity
- systematic?

### Point Correspondence
#### Similarity Windows
- How far do we have to go in image space & what is the cost 
- ![[Pasted image 20250921163942.png]]
- Sum of Squared Diffarences
	- $SSD = = \sum_{i,j} (f(i,j)-g(i,j))$
- Cross correlations
	- $C = \sum_{i,j} = f(i,j)g(i,j)$
- Normalized cross correlation
	- 
- Textureless regions are non-distinct => high ambiguety for matching

### How big Window
- large => no matches
- small => noise
![[Pasted image 20250921164356.png]]
### Alternatives
#### match scanline (stuff should be close together)
	- Dynamic programming - shortest paths & deal
#### Full 2D grid - in 2 Dimensions
	- Pyramid

### [[Graph cuts]]
- Smoothness
- Data term = how simmilar are pixels & look around them with blured version

#### Stereo Matching as Energy minimization
$$E = \alpha E_{data} (I_1, I_2, D) + \beta E_{smooth} (D)$$
$$E_{data} = \sum_i (W_1(i) - W_2(i+D(i)))^2 \quad E_{smooth} = \sum_{neighbours\; i,j} \rho(D(i)-D(j))$$
### Challenges
- low contrast
- Occlusions
- Brightness Violations - Specular reflections
- Really large baselines - Foreshortening
- Camera Calibration

#ComputerVision [[Computer Vision]] [[CV10 - Structured Light]]