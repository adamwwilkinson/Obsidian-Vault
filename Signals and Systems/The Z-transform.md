Created: 19/08/2023 at 09:32

For a general discrete-time signal $x[n]$, the Z-transform is defined as:
$$X(z) = \sum_{n=-\infty}^{\infty} x[n]z^{-n}$$
![[The Z-transform-1692409060986.jpeg]]

### ROC
The region of convergence is the set of values of $z$ for which the Z-transform converges. The ROC is a ring in the complex plane.
![[The Z-transform-1692409542943.jpeg]]![[The Z-transform-1692409555785.jpeg]]

As digital signals aren't real world, they can be a mix of anti causal and causal signals. The ROC is the region of convergence of the causal part of the signal.
![[The Z-transform-1692409360398.jpeg]]