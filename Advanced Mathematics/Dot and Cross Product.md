Created: 07/08/2024 at 16:36

### Cross Product
Get the hard one out the way.

#### The Magnitude

![[Dot and Cross Product-1723019971624.jpeg]]

In 2D space, is dedfined as the area of the parrallelogram created by the two vectors.

With $v \times w$, if $v$ is left of $w$ the magnitude is negative, else it is positive.

The direction it heads is perpendicular to both vectors.

Found by calculating the determinant.

#### Determinant
Measures the amount an area has been scaled.
![[Dot and Cross Product-1723020251946.jpeg]]![[Dot and Cross Product-1723020262057.jpeg]]

##### Computation
###### In 2D
$$v \times w = \begin{vmatrix} \mathbf{i} & \mathbf{j} \\ v_1 & v_2 \\ w_1 & w_2 \end{vmatrix} = v_1w_2 - v_2w_1$$

###### In 3D
$$v \times w = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ v_1 & v_2 & v_3 \\ w_1 & w_2 & w_3 \end{vmatrix} = \mathbf{i}(v_2w_3 - v_3w_2) - \mathbf{j}(v_1w_3 - v_3w_1) + \mathbf{k}(v_1w_2 - v_2w_1)$$

### Dot Product
Very easy to calculate with two vectors.

$$v \cdot w = \begin{bmatrix} v_1 \\ v_2 \\ v_3 \end{bmatrix} \cdot \begin{bmatrix} w_1 \\ w_2 \\ w_3 \end{bmatrix} = v_1w_1 + v_2w_2 + v_3w_3$$
