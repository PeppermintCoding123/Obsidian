= SF routing
- <span style="color:rgb(166, 0, 255)">1 Package</span> from Sorce-node to Destination-node
- through<span style="color:rgb(166, 0, 255)"> sequence of intermediat enodes</span> 

- node needs <span style="color:rgb(166, 0, 255)">packet buffer</span> 

packet forward if:
- <span style="color:rgb(166, 0, 255)">output channel</span> available
- <span style="color:rgb(166, 0, 255)">packet buffer</span> available

[[Latency]] 
= proportional to distance from source to destination 
= proportional to \#Hops
$$T_{SF} = \frac{N\cdot (D+1)}{W}$$
![[Pasted image 20260718135937.png]]
