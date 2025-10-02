# Extraction
- $\alpha$ Frame
- Calculate ariatric Center (Average of x & y coordinates)
- Derive Values / shots from that
- tag the Frames into Directions
- recenter Fish into Baricenter
# Control
$$C_{i\rightarrow j} ^{Animation} = \alpha C_{i\rightarrow j} + \beta \; angle$$
$C_{i\rightarrow j}$ = Similarity term
$angle$ = Control term
- vector to mouse pointer
- velocity vector

Do:
- precompute [[Dead Ends & Future Cost]] for a few angles
- swich between precomputed angles acording to user input
![[Pasted image 20251002135030.png]]

[[CPaC_Overveiw.canvas|CPaC_Overveiw]]