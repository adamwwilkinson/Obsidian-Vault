Created: 11/09/2024 at 14:59

### Key Points
- create a contant rotating magnetic field
- the effect of winding distribution on the magnetic flux distribution ($\tau = K\phi$)

### Rotating Magnetic Field
#### Electrical Phase Shift
Three phase currents connected to each coil,
$$i_a = I_m \sin(\omega t)$$
$$i_b = I_m \sin(\omega t - 120°)$$
$$i_c = I_m \sin(\omega t + 120°)$$

These currents create a magnetic field in each winding,
$$B_{aa} = B_m \sin(\omega t)$$
$$B_{bb} = B_m \sin(\omega t - 120°)$$
$$B_{cc} = B_m \sin(\omega t + 120°)$$
where $B_m = \frac{4}{\pi} \cdot \frac{N}{2} \cdot I_m$

#### Spatial Phase Shift
The electrical phase shift would happen regardless of how the windings are distributed. However, the spatial phase shift is dependent on the winding distribution.
![[Synchronous Machines-1726038673517.jpeg]]

![[Synchronous Machines-1726038974530.jpeg]]

You always get you magnetic flux density to be $B_{\text{total}} = 1.5B_m$ with $\theta = \omega t$.

#### Electrical Speed vs Mechanical Speed
$$\omega_e = \omega_m \cdot P$$
where $P$ is the number of pole pairs.

$$f_e = f_m \cdot P$$
where $f_e$ is the electrical frequency and $f_m$ is the mechanical frequency.

The electrical speed is the speed of the rotating magnetic field, while the mechanical speed is the speed of the rotor.

### Induced Voltage in Stator
Assuming three phases produce components of a field, $\theta$ is the angle between stator field and reference axis.
![[Synchronous Machines-1726374480572.jpeg]]

$$B_a = ki_a \cos \theta \qquad B_b = ki_b \cos(\theta + 120°) \qquad B_c = ki_c \cos(\theta - 120°)$$
![[Synchronous Machines-1726378809951.jpeg]]

### Torque in Coil
$$\tau = 2Bli r \sin \alpha$$

We can write,
$$\tau = \frac 2 \pi \pi Blir \sin \alpha = \frac 2 \pi \phi i \cos(\omega t | \theta) \sin \alpha$$
where $\phi = B(\pi lr)$ is the virtual flux linkage.

$$\tau_{\text{total}} = \frac 4 \pi \phi i \cos \theta_0 \implies \text{Constant Torque}$$
where $\theta_0$ is the angle between the rotor and the stator.

### Power in AC Machine
Synchronous machines can be run in two modes, motor and generator. 
![[Synchronous Machines-1726984975155.jpeg]]

### Types of Rotors
#### Salient Pole
Low cost, and for low speed applications.
![[Synchronous Machines-1726985270155.jpeg]]
#### Cylindrical Rotor
For high speed application
![[Synchronous Machines-1726985283189.jpeg]]

### Construction of Synchronous Machine
#### Stator
First need to create a yoke to hold the stator and rotor. Place slots in the yoke to allow the windings to be placed. These slots reduce the *skin effect*.

```ad-note
The skin effect refers to the phenomena that within a wire carring AC current, the larger the frequency, the more the current is carried on the surface of the wire. This leads to a hollow central core and reduces the effective cross-sectional area of the wire.
```

Next laminating the yoke to minimise partial discharge to the steel reducing the parasitic capacitance.

#### Rotor
##### Salient
Wind the coils around the poles to ensure a uniform magnetic field.

##### Cylindrical
Evenly distribute the coil windings around the rotor to ensure a uniform magnetic field.

#### Slip Rings
If three-phase AC is supplied to the rotor, there'd be three separate slip rings to allow the current to flow to the rotor.


### Connection of Synchronous Machine
A synchro scope is a required tool to connect the machine to the grid. The synchro scope is used to match the phase of the machine to the grid. Were they out of phase, it could lead to very large current surges turning on a transformer causing a trip.

### Synchronism
The magnetic field of the stator is locked with the magnetic field of the rotor, and is equal to the electrical speed of the rotor BUT NOT the mechanical speed of the rotor.

#### Electrical to Mechanical Speed
Having electrical speed in hertz, we can convert to mechanical speed in RPM.
$$1 Hz = 1 rev/s = 60 rev/min$$

### Armature
In a DC machine the armature is the rotor, while in an AC machine the armature is the stator. Why is this?

The armature is where the electromotor force is produced. In a DC machine $e_s = \frac {d\lambda}{dt} = 0$ on the stator, while in an AC machine $e_s = \frac {d\lambda}{dt}$ = 0 on the rotor.

### Different Test
#### Open Circuit Test
With current being 0 due to the open circuit, the voltage across the stator is the induced voltage. This test is used to determine the magnetisation curve.

#### Short Circuit Test
Measure current going through and voltage. $\frac {E_A}{I_A}$ gets you the impedance of the machine. This test is used to determine the equivalent circuit of the machine.

### Phasor Diagrams
#### Generator
![[Synchronous Machines-1727001942489.jpeg]]

Treating the right-side of the equivalent circuit as the reference, we can draw the phasor diagram. The angle between the voltage and current is the power factor.

$jX_s I_A$ is perpendicular to $I_A R_A$ as the j is perpendicular.

Normally $R_A$ can be ignored.o

##### Effect of Lagging Leading Current
![[Synchronous Machines-1727002109056.jpeg]]

#### Motor
![[Synchronous Machines-1727002149451.jpeg]]

Treating the terminal voltage as the reference, we can draw the phasor diagram. The angle between the voltage and current is the power factor.

#### Mode Switching
![[Synchronous Machines-1727002211536.jpeg]]
Load angle is also called the torque angle.

### Torque
![[Synchronous Machines-1727002422441.jpeg]]
There are 2 right angle triangles. Using trig we can find,
$$\tau_d \omega_s = \frac {3VEsin(\delta)}{X_s} = 3VI cos\phi$$

The three comes from the three-phase, cause the diagram we drew was for one phase.

The developed torque,
$$\tau_d = \frac{3VEsin(\delta)}{X_s\omega_s}$$
The maximum torque is when $\delta = 90°$.
$$\tau_{\text{max}} = \frac{3VE}{X_s}$$
The normalised torque is,
$$\frac{\tau_d}{\tau_{\text{max}}} = \frac{sin(\delta)}{sin(90°)} = sin(\delta)$$
![[Synchronous Machines-1727002724148.jpeg]]

### Excitation Control
$E_A \propto \phi_{\text{flux}} \propto V_f$

The excitation control ($E_A$) is done by controlling the field current ($I_f$). The field current is controlled by the field voltage ($V_f$).
$$E_A = K\phi \omega$$

#### Under Excited
$E_A < V_A$
The $\phi$ is negative (lagging current), this can compromise the load torque.

#### Over Excited
$E_A > V_A$
The $\phi$ is positive (leading current), this can lead to a large current, up to the thermal limit $I^2R$.

#### Power Factor Correction
Only synchronous machines can operate at leading power factor. Induction motors operate at lagging power factor.
Overexcited synchronous machines can be used to compensate the total lagging power factor of the grid.