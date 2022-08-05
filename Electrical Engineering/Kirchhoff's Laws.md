# Kirchhoff's Laws
Created: 05/08/2022 at 17:13
Tags: #topic/physics 
Related: [[Circuit Analysis Techniques]]

### Branches and Nodes
Each 2-terminal circuit element is designated as a **branch**. Each terminal of a branch is a **node**. If a node connects to another node without any electronic components between, the two nodes can be merged.

### Parallel or Series?
If a node is shared exclusively by two electronic components, then they are in **series**.

If a common node is shared on both side of electronic components, then they are in **parallel**.

### KCL (Kirchhoff's Current Law)
A restatement of Maxwell's equation.
1. The lumped-circuit truly holds. The voltage at any location along a conductor is the same.
2. Charge is neither created nor destroyed at a node. $\sum \mathrm{incoming \; currents} = \sum \mathrm{outgoing \; currents}$

### KVL
A statement on the conservation of energy.
1. The algebraic sum of voltages around a closed path is zero.
2. The sum of all voltage rises around a closed loop is equal the sum of the voltage drops around that same loop.

```ad-info
Follow counter-clockwise and start counring around the loop.
```