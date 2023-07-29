Created: 02/05/2023 at 16:52

### In Equilibrium
$$n = n_i \exp \left(\frac{E_F - E_i}{kT}\right)$$
$$pn = n_i^2$$

### Under Non-Equilibrium Conditions
Under non-equilibrium conditions, when the density of electrons is different to the equilibrium value we define the electron **Quasi Fermi Energy $E_{Fn}$** as:
$$n = n_i \exp \left(\frac{E_{Fn} - E_i}{kT}\right)$$

Similarly, for holes
$$p = n_i \exp \left(\frac{E_i - E_{Fp}}{kT}\right)$$
![[Non-Equilibrium Currents-1683017897967.jpeg]]

For our second equation above, in non-equilibrium conditions we have,
$$pn = n_i^2 \exp \left(\frac{E_{Fn} - E_{Fp}}{kT}\right)$$

### Reverse Bias
The width of the depletion region is given by
$$W = x_n + x_p$$
where $x_n$ and $x_p$ are the widths of the depletion regions on the n and p sides respectively.
$$W = \sqrt{\frac{2 \epsilon_s}{q} \left(\frac{1}{N_a} + \frac{1}{N_d}\right) (V_{bi} - V_j)}$$
where $V_{bi}$ is the built-in potential and $V$ is the applied voltage.

The maximum electric field is given by
$$\zeta_{max} = \frac{2(\phi_{bi} - V_j)}{W}$$

### PN Junction in Forward Bias
![[Non-Equilibrium Currents-1684218962258.jpeg]]
If we assume the quasi Fermi energies are constant acroos the deploetion region, the electron population on the p side (x = - W) is given by,
$$n(-W) = n_{p0} \exp \left(\frac{eV_j}{kT}\right)$$

Where $n_{p0}$ is the equilibrium electron population on the p side.

Similarly for hole population on the n side of the depletion region (x = 0) is given by,
$$p(0) = n_i \exp \left(\frac{E_{0} - E_{Fp}^P}{kT}\right) = p_{n0} \exp \left(\frac{eV_j}{kT}\right)$$

Where $p_{n0}$ is the equilibrium hole population on the n side.

### Regions of Interest for Diode Currents
![[Non-Equilibrium Currents-1684219717835.jpeg]]
Region I is the region of equilibrium, region II is the depletion region, region III is where the diffusion occurs.

#### Region III
Considering the region of interest III, we have are concerned in the steady-state when $\frac{\partial p}{\partial t} = 0$ and $\frac{\partial n}{\partial t} = 0$. First the injection of holes in the N-side, the relevant equation is the continuity equation,
$$\frac{\partial p(x)}{\partial t} = -\mu_p p(x) \frac{\partial \zeta(x)}{\partial x} - \mu_p \zeta(x) \frac{\partial p(x)}{\partial x} + D_p \frac{\partial^2 p(x)}{\partial x^2} + [g_p(x) - r_p(x)]$$

The first two terms on the right hand side are the drift terms, the third term is the diffusion term and the last two terms are the generation and recombination terms.

Assuming low-injection, the drift current due to holes is negligeble compared to the drift current due to electrons, so we end up
$$0 = D_p \frac{\partial^2 p(x)}{\partial x^2} + (p_n - p_{n0}) \frac{1}{\tau_p}$$

Where $\tau_p$ is the hole lifetime and $p_n$ is the hole population at the edge of the depletion region and $p_{n0}$ is the equilibrium hole population at the edge of the depletion region.

This equation has solutions of the form
$$\Delta p_n(x) = A \exp \left(-\frac{x}{\sqrt{D_p \tau_p}}\right) + B \exp \left(\frac{x}{\sqrt{D_p \tau_p}}\right)$$

Where $A$ and $B$ are constants dependent on the boundary conditions.
```ad-warning
This equation is the difference of deviation away from equilibrium.
```

$\sqrt{D_p \tau_p}$ is the diffusion length denoted by $L_p$. $D_p$ is the diffusion coefficient of holes in the n-type material.

Under similar assumptions we can derive the electron population on the p side of the depletion region,
$$\Delta n_p(x) = C \exp \left(-\frac{x}{\sqrt{D_n \tau_n}}\right) + D \exp \left(\frac{x}{\sqrt{D_n \tau_n}}\right)$$

Where $C$ and $D$ are constants dependent on the boundary conditions.
$C$ is zero because the electron population on the p side x is negative.

#### Using Boundary Conditions
$$\Delta p(\inf) = 0$$
$$\Delta p(x_n) = p_{n0} \exp \left(\frac{V_D}{V_T}\right) - 1$$

The injection of holes in the neutral N-side is given by,
$$\Delta p_n(x) = p_{n0}[\exp \left(\frac{V_D}{V_T}\right) - 1] \exp \left(-\frac{x - x_n}{L_p}\right)$$

Where $V_D$ is the voltage across the depletion region and $V_T$ is the thermal voltage.

### Total Current
Assuming no generation and recombination in the depletion region, the total current is given by,
$$J_T = J_p(x_n) + J_n(-x_p)$$

Where $J_p(x_n)$ is the hole current at the edge of the depletion region and $J_n(-x_p)$ is the electron current at the edge of the depletion region.

$$J_T = J_0[\exp(\frac{V_D}{V_T}) - 1]$$

Where $J_0$ is the reverse saturation current.
