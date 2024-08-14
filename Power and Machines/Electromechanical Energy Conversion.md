Created: 11/08/2024 at 17:56

### Key Points
- Energy flow of electro-mechanical energy conversion in electrical machines.
- Electro-mechanical energy conversion in DC machines: torque development and electro-motive-force
$$\tau = k \Phi i$$
$$e_{\text{ind}} = k \Phi \omega_{(\text{rotor speed})}$$
- Introduction of commutation and armature reaction in DC machines

### Forces on Wires:
Two current carrying wires will experiece forces from the magnetic field of the other.

$$F_1 = I_1 l B_2 \qquad B = \frac {\mu_0 i_q}{2 \pi r}$$
![[Electromechanical Energy Conversion-1723370890173.jpeg]]

Most electric machines have complex structure, also the magnetic material will contribute to magnetic fields, hence the relation of force can not be easily obtained.

### Energy Balance
$$\text{electical energy in} = \text{energy stored in magnetic field} + \text{mechanical energy out} + \text{losses}$$

#### Energy Stored in Magnetic Field
$$E_{\text{store}} = \int Q \, dt$$

This is reactive power, as it can come back.

#### Types of Losses
- copper losses (from resistance $I^2 R$)
- hysteresis loss
- eddy current loss

### Example of Electromechanical Energy Conversion
#### Linear DC Motor
$$D_m = iLB$$
![[Electromechanical Energy Conversion-1723371868673.jpeg]]

##### Case 1: The wire at rest ($v= 0$)
$$F_m = iLB \qquad F_\text{load} = mg \qquad i = \frac {mg}{LB}$$
$$P_{\text{out}} = F_m v = 0$$
$$P_{\text{in}} = V_1 i$$
$$V_1 i = i^2 R = \text{loss}$$

##### Case 2: The wire moving at constant velocity
$$i = \frac{mg}{LB} \qquad P_{out} = F_m v = iLBv$$

$$V_2 i = \text{heat} + \text{mechanical work} = i^2 R + iLBv$$

$$V_2 i - V_1 i = iLBv$$

$$V_2 - V_1 = LBv$$

$$e_{ind} = vBL$$


#### Solving Power From Load
![[Electromechanical Energy Conversion-1723376097222.jpeg]]

##### Equivalent Circuit
$$\text{Motor action } V > e_{ind}$$

$$\text{Generator action } V < e_{ind}$$


##### Dynamic Conditions
$$V = iR + e_{ind}$$

$$V = iR + BLv = R \left(\frac{F_{load}}{BL}\right) + BLv$$

$$v = \frac{V}{BL} - \frac{R}{(BL)^2} \cdot F_{load}$$

### Performance Metrics
#### Speed Regulation (the smaller the better)
$$SR = \frac{v_{no\text{-}load} - v_{full\text{-}load}}{v_{no\text{-}load}} \times 100\%$$

#### Power Efficiency
$$\eta = \frac{P_{out}}{P_{in}} \times 100\% = \frac{P_{in} - P_{loss}}{P_{in}} \times 100\%$$

$$P_{in} = Vi = i^2 R + iLBv = P_{loss} + P_{out}$$

$$\eta = \frac{Vi - i^2 R}{Vi} \times 100\% = \left[ 1 - i \frac{R}{V} \right] \times 100\% = \left[ 1 - \frac{F_{load}}{BL} \frac{R}{V} \right] \times 100\%$$

### Rotating Machine (Single Wire Loop)
Single Wire Loop means there is only one turn.
![[Electromechanical Energy Conversion-1723377097582.jpeg]]
$$F_{cd} = i(\mathbf{L} \times \mathbf{B}) = iLB$$

$$F_{ba} = i(\mathbf{L} \times \mathbf{B}) = iLB$$

$$F_{cb} = F_{ad} = 0$$

$$\tau_{cd} = F_{cd} r \qquad \tau_{ba} = F_{ba} r$$

$$\tau = 2iLBr$$

#### Commutator
Consist of slip rings(rotate with wire) and brushes (stationary).
![[Electromechanical Energy Conversion-1723377313901.jpeg]]

#### EMF
As the wire rotates an EMF is induced.
##### Circuit Model
![[Electromechanical Energy Conversion-1723377860827.jpeg]]

##### Current
![[Electromechanical Energy Conversion-1723377934621.jpeg]]
$$\tau = 2iLBr = 2B\left(\pi rL\right)\frac{i}{\pi} = \frac{2}{\pi}BA_p i = K\phi i$$

$$\tau = K \times \text{flux} \times \text{armature/rotor current}$$

$K$ is called the machine constant.

$$A_p = \frac{1}{2}\left(2\pi rL\right) \quad \text{Each pole is facing half of cylinder}$$

##### Voltage
![[Electromechanical Energy Conversion-1723378169084.jpeg]]

$$e_{ind} = e_{dc} + e_{ba} = 2vBL = 2r\omega BL = \left(2\frac{A_p}{\pi}\right)B\omega = \left(A_p B\right)\frac{2}{\pi}\omega = K\phi\omega$$

$$\text{generated voltage} = K \times \text{flux} \times \text{angular speed}$$

### Armature Reaction
![[Electromechanical Energy Conversion-1723378386467.jpeg]]

As the rotor rotates, some places strength the magnetic field while others weaken it.

![[Electromechanical Energy Conversion-1723378589822.jpeg]]

This causes a lagging sensation which can cause extremely high current surges.
![[Electromechanical Energy Conversion-1723378626654.jpeg]]

Can overcome this using compensation windings.
![[Electromechanical Energy Conversion-1723378672127.jpeg]]