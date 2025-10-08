- Color chalnells 0-255 are not proportional to intencity of channel
- because of Carthode Ray Tube Monitors - CRT

#### Power Law
$I \varpropto V^\gamma$
$\gamma = 2.2$

### $x_{linear} = x_{sRGB}^\gamma$
=> apply Gamma to sRGB to get linear RGB, do calculations & Convert back
```python
gamma_remove = lambda x: np.power(x, 1/2.2)
gamma_apply = lambda x: np.power(x, 2.2)
```

- apply to luminance for image enhancement
- gamma monitors CRT monitor intencities
- 8Bit linear RGB has less relative precision in darks
![[Pasted image 20251008100746.png]]
![[Pasted image 20251008101241.png]]