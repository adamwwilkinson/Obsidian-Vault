Created: 21/08/2024 at 15:40

Stepper motors are used for *position control*. They are designed to turn the output shaft through to a precise angle.

There are three types,

### Simple Permanent Magnet
Similar to permanent-magnet synchronous motors, except that the stator currents are *switched* instead of varied.
### Variable Reluctance
Do not contain magnets, easy to control, but have relatively large *step angles*.
![[Stepper Motors-1724321247627.jpeg]]
### Hybrid
Makes use of permanent magnets to enhance the reluctance effect, can be made with very small step angles *1.8* degrees, and can develop large values of torque. The stronger the permanent magnet, more flux therefore more torque.
![[Stepper Motors-1724321474309.jpeg]]

4 groups, 2 half aligned, 1 aligned, and one non-aligned. By magnetising poles, you can step by 1.8 degrees.

![[Stepper Motors-1724322406329.jpeg]]
### Alignment Torque
Displacement of any part of the system causes a change in the *reluctance*.
![[Stepper Motors-1724321674999.jpeg]]
The stator tries to rotate the rotor where the reluctance is minimum.

#### Maximum Torque
- $r$: mean radius
- $l_g$​: the radial length of the air gap
- $\theta$: the angle of overlap between the stator and the rotor
- $d$: the depth of the device perpendicular to the plane
- $B$: the flux density

_It is assumed that the flux is entirely confined to the overlapping portion._

---

**Equations:**

$$\Phi = BA = Bdr\theta$$

**The reluctance of each airgap is:**

$$\mathcal{R} = \frac{l_g}{\mu_0 A} = \frac{l_g}{\mu_0 dr\theta}$$

$$\tau_{\theta} = -\frac{1}{2}\Phi^2 \frac{\partial \mathcal{R}}{\partial \theta} = -\frac{1}{2}(Bdr\theta)^2 \frac{\partial}{\partial \theta} \left( \frac{2l_g}{\mu_0 dr\theta} \right)$$

$$\tau_{\theta} = \frac{1}{2}(Bdr\theta)^2 \frac{l_g}{\mu_0 dr\theta^2} = \frac{l_g dr B^2}{\mu_0}$$

_Independent of_ $\theta$!