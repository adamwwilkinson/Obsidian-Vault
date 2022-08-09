# Systematic Approaches
Created: 07/08/2022 at 12:48
Tags: #topic/physics 
Related: [[Circuit Analysis Techniques]]

### Node-to-datum Analysis
Instead of having voltage drops between two non-specific nodes, we assign one node in a circuit to be the reference node, or *datum* node or *ground* node. Any voltage in reference to the *datum* node is called **node-to-datum voltage**. A.K.A. **nodal voltage**.

#### Selecting the Datum Node
Any node can be the the datum node, but a smart datum node means less work. Picking a datum node

#### Steps
1. Choose a set of **node-to-datum** voltages
2. Write a set of KCL equations at each node
3. Solve the equation to find the **NTD** voltages
4. Determine the individual elements voltaged and currents

#### Circuit Notation
#todo/excalidraw ground node diagram

### Supernode
When a voltage source is totally enclosed within a part of a circuit. We can state that the total current flowing in to and out of the region, *supernode* is zero.

### Mesh Analysis
Analogous to [[#Node-to-datum Analysis]].
#todo/examples 

#### What is a Mesh
A closed electrical pathway that does not contain other closed physical pathways.

#### Steps
1. Choose a set of mesh currents
2. Write a set of KVL equations around each mesh
3. Solve these equations to obtain the mesh currents
4. Determine the individual elements currents