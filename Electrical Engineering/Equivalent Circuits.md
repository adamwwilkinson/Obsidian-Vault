# Equivalent Circuits
Created: 12/08/2022 at 11:55
Tags: #topic/physics 
Related: [[Source Transformation]]

### Thevenin's Theorem
Any *linear electrical network containing only independent and dependent voltage and current sources and resistances* can be **replaced** at terminal X-Y by an *equivalent combination of a voltage source $V_{th}$ is series with a resistor $R_{th}$* .

#### Conditions
Network A:
- Consist of [[Superposition and Equivelent Circuits#Linearity|Linear]] elements
- Initial conditions allowed on passive elements
- No coupling to Network B
Network B:
- Any elements
- Any source
- Initial conditions allowed on passive elements
- No coupling to Network A

### Norton's Theorem
Any *linear electrical network containing only independent and dependent voltage and current sources and resistances* can be **replaced** at terminal X-Y by an *equivalent combination of a current source $I_{N}$ is parallel with a resistor $R_{N}$* .

In fact, $R_{N}$ = $R_{th}$

To find $I_N$ short the terminals X-Y and find the current flowing through the shorted path.

![[Norton's Theorem Drawing]]
