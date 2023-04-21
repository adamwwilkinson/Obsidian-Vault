Created: 10/04/2023 at 10:25

### Current From Diffusion
![[Diffusion-1681093701954.jpeg]]
As the particles diffuse, initially there is a very high current, before going to 0 (due to both sides having an approximately equal number of particles). Diffusion is a process *driven by temperature*.

```ad-note
Johnson noise is the noise attributed to charged particles flowing from one side of the box to another, after equilibrium is found.
```

#### Fick's Law
$$F_c = -D_c \frac {dC} {dx}$$
$F_C$ is the flux of carrier $c$ and $C$ is the concentration of that carrier. $D_c$ is knows as the diffusion coefficient.

$$D_c = D_n = l v_{\mathrm {thermal}} = \frac {kT} e \mu_n = V_{\mathrm{Thermal}} \times \mu_n$$
$l$ is the mean-free path.

#### Diffusion Current
The diffusion current due to electrons is,
$$J_n = -eF_n$$

For holes,
$$J_p = eF_p$$

One disadvantage of adding impurities to an intrinsic semiconductor, it's mobility goes down.

### Total Current
$$J_{\mathrm{TOTAL}} = J_n + J_p$$
![[Diffusion-1681094873497.jpeg]]

#### Comparison of Drift and Diffusion Currents
The difference in mobility for holes, and electrons are roughly the same. In an n-type material, the ratio of the drift current of holes to electrons is the same as the ratio of holes compared to electrons.  This mean in an n-type, the drift current of holes is negligeble. Same is true for p-type material, where the drift current of electrons is negligible.

The diffusion current on the other hand is of the same order of magnitude whether for holes or electrons, this means either cannot be ignored.