Created: 27/07/2024 at 13:38

### Motivations
- electrical machines have no emissions
- high in efficiency
-
### Electric Motors
- higher efficiency
- power level $10^{-6}$ W - $10^9$ W (watch - power station)
- torque levels $10^{-9}$ Nm - $10^7$ Nm
- speed range 0 rpm - 300,000 rpm (wind turbine - spindle)
- positioning accuracy to below 1nm

### Review of Circuit Theory
#### Kirchoff's Laws
![[Kirchhoff's Laws]]

#### v-i Characterisation of Devices
![[Introduction-1722060748763.jpeg]]

Current leads voltage by 90 degrees in a capacitor and lags by 90 degrees in an inductor.

#### Frequency Domain
![[The Frequency Domain]]

#### RMS Value
$$V_{rms} = \sqrt{\frac{1}{T} \int_0^T [V \cos(\omega t)]^2 \, dt} = \frac{V}{\sqrt{2}}$$

#### AC Power
![[Introduction-1722063079073.jpeg]]

But what does negative power mean? It means that the power is being absorbed by the source.

##### Instantaneous Power
![[Introduction-1722064526139.jpeg]]

The difference between the terms $A$ and $B$ is that $B$ has a frequency. $A$ is a constant.
![[Introduction-1722064638487.jpeg]]
![[Introduction-1722064737797.jpeg]]

$A'$ is made up of two parts, a constant and a cosine function. While $B'$ is made up of a constant and a sine function.
$A'$ is the active power and is equal to the average power. $B'$ is the reactive power and average is always zero.

#### Phasors for Different Loads
![[Introduction-1722065617075.jpeg]]

### Three Phase Wye Connection
![[Introduction-1722066368570.jpeg]]
![[Introduction-1722066768372.jpeg]]
![[Introduction-1722066854879.jpeg]]

#### Wye Connection
$$p_{3\phi}(t) = 3 V_{\phi} I_{\phi} \cos(\theta)$$

$$V_{\phi} = \frac{V_{\text{line}}}{\sqrt{3}}$$
$$I_{\phi} = I_{\text{line}}$$

Thus:
$$p_{3\phi}(t) = \sqrt{3} V_{\text{line}} I_{\text{line}} \cos(\theta)$$


#### Delta Connection
$$p_{3\phi}(t) = 3 V_{\text{line}} I_{\text{line}} \cos(\theta)$$

$$I_{\phi} = \frac{I_{\text{line}}}{\sqrt{3}}$$
$$V_{\phi} = V_{\text{line}}$$

Thus:
$$p_{3\phi}(t) = \sqrt{3} V_{\phi} I_{\phi} \cos(\theta)$$
