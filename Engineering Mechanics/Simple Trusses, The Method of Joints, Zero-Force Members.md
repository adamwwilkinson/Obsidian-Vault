# Simple Trusses, The Method of Joints, Zeo-Force Members
Created: 14/08/2022 at 21:20
Tags: #topic/physics 
Related: [[Equations of Equilibrium and Two Force Members]]

### Trusses
#### Applications
Commonly used to support roofs, also used in structures like cranes, aircraft frames or the space station.

#### Simple Trusses and Planar Trusses
A **truss** is a structure made of slender members joined together at their end points. If a truss, along with its load, lies on a single plane, it's called a **planar truss**. A **simple truss** is a planar truss which begins with a *triangular* element that can be expanded by adding two members and a joint. #todo/excalidraw These trusses have an equation to relate the members ($M$) to the number of joints ($J$).
$$M = 2J - 3$$

If this equation is not satisfied you either have a [[Constraints and Determinancy#Statically Indeterminate]] truss, or you have an unstable mechanism.

#### Analysis
It is necessary for the design of the *members* and *joints* for a *truss* to determine the force in each truss member. This is called **force analysis**. 
The following assumptions are made for **force analysis**:
1. All loads are applied at the joints. The weight of the truss member is neglected s the weight is small compared to the forces supported by the members.
2. Members are joined together by smooth pins. This assumption is satisfied in most practical cases where joints are formed by bolting the ends together.

With these two assumptions, the members act as [[Equations of Equilibrium and Two Force Members||two-force members]].  Either loaded in *tension* or *compression*. If they are loaded in *compression* they are made to be thicker to protect against buckling.

### The Method of Joints
For solving the forces in truss members, the equilibrium of a *joint (pin)* is considered. [[Equations of Equilibrium and Two Force Members|Equations of equilibrium]] are used to solve for the unknown forces.

#### Steps for Analysis
1. If no support reactions are given, draw a FBD of the *entire* truss and determine the support reactions.
2. Draw a FBD of a joint with one or two unknowns. **Assume all unknown member forces act on tension.**
3. Apply scalar equations of equilibrium to determine the unknowns.
4. Repeat steps 2, 3 at each joint.

### Zero-Force Members
If a joint has only two non-collinear members and there is no external load or support reaction at that joint, the two members are *zero-force members*.

If three members form a truss joint and two of the members are collinear and there is no external load or reaction at that joint, then the third non-collinear member is a zero-force member.

Zero-force members can be removed when analysing the truss, they are used to increase the stability and rigidity of the truss as well as to provide support under different loading conditions.

### Determinancy
For it to be determinante we have 3 unknown traction forves #todo read lecture sheets 2 for determinancy
sdad

#### External Determinancy
If a truss has more external supports than is necessary to ensure equilibrium, it is externally indeterminant.

#### Internal Determinancy
If a truss has more internal memebr than is necessary to ensure stability, it is internally indeterminant.