Created: 25/05/2023 at 17:14

An acronym for metal-oxide-semiconductor field-effect transistor.

### Introduction
The building block of modern electronics.
It is scalable, low power, and can be made in large quantities.
It is easy to understand the concept, but difficult to understand the physics and mathematics.

### Types
There are PMOS, NMOS, and CMOS transistors.
PMOS is when holes are the majority carrier, and NMOS is when electrons are the majority carrier.
CMOS is when both are used, and is the most common.

### MOS Capacitor
The SiO2 layer is close to 1nm thick, and is a very good insulator. A conductor usually aluminium is deposited on top.

#### The Band Diagram
![[The MOSFET-1685011088119.jpeg]]

Metal has no band gap, and is always conducting. The oxide has a large band gap and is an insulator. The semiconductor has a small band gap and is a semiconductor.

The top line is the vacuum level, and the bottom line is the Fermi level. The Fermi level is the energy level at which there is a 50% chance of finding an electron. The vacuum level is the minimum energy an electron possesses, in order to complete escape the material.

The work functon $\phi$ is the energy required to remove an electron from the material to the vacuum level. The work function is the difference between the vacuum level and the Fermi level.

The electron affinity $\chi$ is the energy required to remove an electron from the material to the vacuum level. The electron affinity is the difference between the vacuum level and the conduction band.

$$\phi = \chi + (E_{c} - E_{f})$$

#### Joining The Materials
![[The MOSFET-1685011689989.jpeg]]

Because of the insulator, it is not possible for carriers to flow between the metal and the semiconductor. The metal is in equilibrium with the semiconductor, and the Fermi level is the same in both materials.

Electrons move from higher work function to lower work function, and holes move from lower electron affinity to higher electron affinity. They cannot move through the oxide, so the move through the external circuit.

Looking at the potential energy of the oxide, this indicated the silicon side is at a higher potential than the metal. I.e. there is a voltage drop acrooss the oxide with positive voltage at the metal.

What is the difference between the two work functions? This is the built in potential $V_{bi}$.
First the difference of $E_i$ and $E_F$ need to be found in the silicon.

If the p-type doping is $1\times 10^15 cm^{-3}$, then using the equation,
$$p = n_i \exp\left(\frac{E_i - E_F}{kT}\right)$$
$$E_i - E_F = kT \ln\left(\frac{p}{n_i}\right) = 0.29 eV$$

Using the vacuum energyy as reference, $Phi_S$ in silicon is calculated as,
$$\Phi_S = \chi_s + E_i + (E_i - E_F) = -4.9eV$$

Upon the connection, the Fermi energies will align producing a potential difference across the insulator, and a gradient in the nergy bands of the silicon close to the insulator.
The voltage in the silicon is called the **surface potential** $\psi_s = [E_i(\infty) - E_i(0)]/e$.

There is $\psi_s$ volts across the depletion region with the oxide end of the depletion region being more positive than the contact away from the oxide.

This electron potential energy drop at the surface will cause the holes to move away from the silicon to oxide interface and will create a depletion region consisting of fixed negatively ionised acceptor dopants.

### Flat Band Condition
The voltage that when applied to the gate, will cause the Fermi level to be flat across the semiconductor.
![[The MOSFET-1685017112723.jpeg]]

If an external voltage is applied to the metal to balance the work function between metal and semiconductor, the potential gradient in the semiconductor and insulator can be removed.

The ideal flat band voltage is given by,
$$eV_{FB} = \Phi_M - \Phi_S \approx \Phi_M - [\chi_s + \frac {E_G}{2} - (E_i + E_F)]$$

### Accumulation Or Enhancement
When depletion layers occur there are two cases.
![[The MOSFET-1685017603498.jpeg]]
It depends on the work function of metal and semiconductor. The work function closer to vacuum level will have electrons flowing out of that and into the other material. The Fermi energy is flat within each region because no current is flowing.

Accumalation means like charges are on the same side of the insulator. Enhancement means opposite charges are on the same side of the insulator.
![[The MOSFET-1685018003428.jpeg]]![[The MOSFET-1685018157578.jpeg]]
![[The MOSFET-1685018726611.jpeg]]
$$p(x) = N_A \exp\left(-\phi(\chi_s/V_T)\right)$$
where $\phi(x) = [E_i(\infty) - E_i(x)]/e$, and $N_A = n_i \exp\left(-\phi(b)/V_T\right)$

For electrons,
$$n(x) = n_i \exp\left(\phi_b + \phi(x))/V_T\right)$$

The concentration of holes is greater at the surface than in the bulk, this condition is called accumulation or enhancement.

### Depletion
If $\phi_s > 0$ the density of holes at the surface is less than in the bulk. This condition is called depletion.
![[The MOSFET-1685018552234.jpeg]]![[The MOSFET-1685018578430.jpeg]]

### Inversion
![[The MOSFET-1685018679330.jpeg]]

### Type Conversion
By changing the gate voltage, we can change the accumalation (attracting a bunch of holes to the insulator). Changing the gate voltage towards more positive, it goes through depletion, allowing us to type convert.

If there is an n-type substrate, when it gets inverted, the channel becomes p-type.

![[The MOSFET-1685263882879.jpeg]]

Any voltage less than the green line on the left results in accumulation. This means the oxide will act as a parallel plate capacitor with width equal to the oxide width. This is accumulation.

Going towards positive reason, bands are bent and we start to get depletion, before this though we have flat band.

#### Flat Band
Applying a voltage (the metal is at a lower voltage than semiconductor) causes the bands to bend. Thinking of the voltage applied as a pump, the electrons moving into the semiconductor pipe, is pumped out again by the voltage applied to the metal. The Fermi level is flat across the semiconductor. This means the density of holes is the same everywhere.

![[The MOSFET-1685262430552.jpeg]]

#### Accumalation
Applying a voltage less than flat band, means we are encouraging pumping electrons into the metal, this starts to attract a lot of the holes in the interface with the insulator and semiconductor. Now the band is bending upwards and $(E_i)$ moves further away from Fermi energy meaning it is more p-type.
![[The MOSFET-1685262752199.jpeg]]

For voltage $V_G < V_{FB}$ we get accumalation. Again this means the transitor acts as a parallel plate capacitor.

$$C = \frac{\epsilon_{ox}}{d_{ox}}$$, this is Farads per area, and the area is the area of the gate.

#### Depletion
We start pushing electrons into the semiconductor, cause the bands to bend downwards.
$E_i$ is moving towards the Fermi energy. This means the hole are being pushed away from the interface, leaving behind fixed energy charges. Increasing the gate voltage bends the bands down further and further.

![[The MOSFET-1685262959990.jpeg]]

Then we get to the point where the intrinsic will get below the Fermi energy, we have more electrons then we have holes in the semiconductor, and it looks n-type.

If you keep going until you are below the Fermi energy equal to what it was before, i.e. below by $\phi_b$ the electron density becomes $N_A$ and the type has been converted. This is the definition of strong inversion.

Now the capacitance is made up of the oxide capacitance in series with the depletion region capacitance.

![[The MOSFET-1685263740260.jpeg]]

![[The MOSFET-1685263827176.jpeg]]

This oxide thickness doesn't change, but now we have a voltage dependant capcitance as the width of the depletion region changes.

At the onset of strong inversion, we will reach a maximum depletion width due to electron shielding.

### Things To Know For Exam
Most information will be contained in part A slides. Make sure it is understood what electron affinity, and how to calculate what voltages are required for flat band.

Note the difference between energies in eV and voltages in Volts.

Be able to work out the volt potential, understand the equation $p = n_i \exp((E_i - E_F) / kT)$

Understand the surface potential, and how to calculae the energy difference at flatband.

Understanding depletion and inversion.

## Part C
![[The MOSFET-1685432865454.jpeg]]

We've got the source gate and drain. Underneath the source and the drain are pockets of n-type material. Underneath the gate is the substrate which is p-type.

If the drain has a positive voltage, while the source is grounded, no current will flow. If a voltage exist on the gate, there will be inversion and a channel of n-type material will form between the source and drain. This is the channel.

Now a current will have a path to flow. The gate controls the current flow between the source and drain, higher the gate, the lower the resistance.

This is it acting as a switch mode, but it can also be used in a transistor like mode. A small voltage on the gate can control a large voltage on the drain.

### Device Structure
![[The MOSFET-1685433157862.jpeg]]

This channel can be modeled as a resistor, this means the drain end is higher than the source end. If there is a voltage gradient under the insulator, that means the difference between the potential at the insulator and the gate varies along the channel, and that means the degree of inversion varies along the channel.

At the source end there is a bigger voltage difference between the insulator and the gate, and at the drain end there is a smaller voltage difference between the insulator and the gate. Which means the channel thins out at the drain end.

#### Mathematically
![[The MOSFET-1685433513963.jpeg]]
![[The MOSFET-1685433624541.jpeg]]
![[The MOSFET-1685433847312.jpeg]]
$$V_{Tn} = V_{FB} + 2\phi_b + \sqrt{4e\epsilon_{Si}N_A\phi_b}\frac{t_{ox}}{C_{ox}}$$

This above one is useful to know.
![[The MOSFET-1685433957196.jpeg]]
$Z$ is the width of the gate.

### Triode and Saturation
![[The MOSFET-1685434410974.jpeg]]