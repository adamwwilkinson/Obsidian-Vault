Created: 25/03/2023 at 09:58

### What
A graphical representation of a system's frequency response.

Often we have circuits with an input and output plot. We apply a voltage at the input and see what the responding voltage is. The network function called the transfer function is described in the laplace domain by,

$$H(s) = \frac {V_{out}(s)} {V_{in}(s)}$$

Generally we want to know how $H(s)$ varies over a range of frequencies i.e. $s=j\omega$. We are mainly focused on the magnitude for this unit.

![[The Bode Plot-1679709665912.jpeg]]
![[The Bode Plot-1679713711348.jpeg]]

### Zeros
![[The Bode Plot-1679713927859.jpeg]]

### Poles
![[The Bode Plot-1679714263859.jpeg]]

### Example
![[The Bode Plot-1679714480485.jpeg]]
![[The Bode Plot-1679714492472.jpeg]]

```ad-info
The flat bit at the bode plot is the pass band, and is where the amplification is supposed to occur.
```

```ad-important
To approximate how a Bode plot would look, find the dB at $\omega = 0$, then continue through until you hit either a pole, or a zero. If a zero, start a linear line with a gradient of 20dB a decade, and if a pole, start a linear line with a gradient of -20dB a decade. As you hit poles and zeros your lines would steepen down, or steepen up respectively. 
```