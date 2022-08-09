# Kirchhoff's Laws
Created: 05/08/2022 at 17:13
Tags: #topic/physics 
Related: [[Circuit Analysis Techniques]]

### Branches and Nodes
Each 2-terminal circuit element is designated as a **branch**. Each terminal of a branch is a **node**. If a node connects to another node without any electronic components between, the two nodes can be merged.

### Parallel or Series?
If a [[#Branches and Nodes|node]] is shared exclusively by two electronic components, then they are in **series**.

If a common [[#Branches and Nodes|node]] is shared on both side of electronic components, then they are in **parallel**.

```ad-important
If components are connected in series, current stays the same while the voltage is affected.

If components are connected in parallel, current changes while the voltage stays the same.
```

### KCL (Kirchhoff's Current Law)
#todo/examples
A restatement of Maxwell's equation.
1. The lumped-circuit truly holds. The voltage at any location along a conductor is the same.
2. Charge is neither created nor destroyed at a node. $\sum \mathrm{incoming \; currents} = \sum \mathrm{outgoing \; currents}$

### KVL
A statement on the conservation of energy.
1. The algebraic sum of voltages around a closed path is zero.
2. The sum of all voltage rises around a closed loop is equal the sum of the voltage drops around that same loop.
#todo/excalidraw KVL in notebook 9/8/22

### Consequences
1) Two elements in parallel have the same voltage across them
2) Two elements in series have the same current flowing through them