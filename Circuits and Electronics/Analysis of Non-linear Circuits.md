Created: 09/04/2023 at 11:37

### Small Signal Linear Model
The development of a linear model, for a non-linear element, is called *linearisation*. The corresponds to an approximate model which is linear and sufficiently describes the behaviour of the non-linear element.

### Non-linear Dynamic Model
#### State Space Model
$$\frac {dX(t)} {dt} = f(X(t), U(t))$$
$$Y(t) = g(X(t), U(t))$$

$X(t)$ is a vector representing the internal electrical state
$Y(t)$ represents the electrical signals of interest at the out terminals of the device
$U(t)$ represents the electrical signals of interest at the in terminals

#### Equilibrium Point
 ![[Analysis of Non-linear Circuits-1681011983582.jpeg]]
 This means $\frac {dX(t)} {dt} = 0$.

#### Taylor Series Expansion
![[Analysis of Non-linear Circuits-1681012131604.jpeg]]

#### Small Signal Model
![[Analysis of Non-linear Circuits-1681012194998.jpeg]]