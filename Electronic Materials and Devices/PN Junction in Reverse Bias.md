Created: 19/05/2023 at 17:13

### Band Diagram
![[PN Junction in Reverse Bias-1684487610752.jpeg]]

By reverse biasing, the width of the depletion region increases, and the barrier goes up.

All the equations found in equilibirum can be applied to the reverse case, but with the barrier height changed from $\phi_{bi} - V_j$.

The equlibrium equations were,
$$x_p = \sqrt{\frac{2 \epsilon_r \epsilon_0}{eN_A} \frac{N_D}{N_A + N_D} (V_{bi} - V_j)}$$
$$x_n = \sqrt{\frac{2 \epsilon_r \epsilon_0}{eN_D} \frac{N_A}{N_A + N_D} (V_{bi} - V_j)}$$
$$W = x_p + x_n = \sqrt{\frac{2 \epsilon_r \epsilon_0}{e} \frac{N_A + N_D}{N_A + N_D} (V_{bi} - V_j)}$$

### Charged Stored
The charge per unit area stored on the p-side
$$Q = -qx_pN_A$$
$$Q = -qN_A \sqrt{\frac{2 \epsilon_r \epsilon_0}{eN_A} \frac{N_D}{N_A + N_D} (V_{bi} - V_j)}$$

Small signal capacitance per unit area,
$$C = \frac {dQ} {DV_j} = \frac {\epsilon_r \epsilon_0} {W}$$

```ad-info
This only works in reverse bias and not forward as negligible current are involved.
```

The expresion for depletion capacitance per unit area is
$$\frac 1 {C^2} = \frac {2}{e \epsilon_r \epsilon_0} \frac{N_A + N_D}{N_A N_D} {V_{bi} - V_j}$$

#### One Sided PN Junctions
This equation above reduces to
$$\frac 1 {C^2} = \frac {2}{e \epsilon_r \epsilon_0} \frac{1}{N_D} {V_{bi} - V_j}; N_A >> N_D$$
$$\frac 1 {C^2} = \frac {2}{e \epsilon_r \epsilon_0} \frac{1}{N_A} {V_{bi} - V_j}; N_D >> N_A$$

### Currents in Reverse Bias
In reverse bias the majority carrier virtually disappears, so the current comes from the minority carriers.

Theres a current in the depletion region due to generation of carriers, because theres an electric field in the depletion region theres movement and thus current.
Also, at the edges theres both diffusion and generation,

![[PN Junction in Reverse Bias-1684489746385.jpeg]]

### Generation Current
The equation of the generation rate is
$$U = - \frac{n_i} {2\tau_o}$$,

$$I_{gen} = qUWA_j = - \frac{q n_i} {2\tau_o} WA_j$$

### Generation Current Outside the Depletion Region
$$U = \frac {p_n - p_{n0}} {\tau_p}$$

### Total Current
$$I_R = I_{gen} + I_{diff, p} + I_{diff, n}$$
$$I_R = - \frac{q n_i} {2\tau_o} WA_j - qD_p \frac{n_i^2}{N_D L_p}A_j - qD_n \frac{n_i^2}{N_A L_n}A_j$$
