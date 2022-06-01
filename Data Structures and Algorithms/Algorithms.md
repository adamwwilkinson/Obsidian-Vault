# Algorithms
Well-defined *set of rules* that specify a sequential series of operations to be applied to an input, which then produces an output.

### Design and Analysis
Few questions to keep in mind:
	1. *What* is the *problem* to solve?
	2. Does a solution *exist*?
	3. Can we find a solution (algorithm), and is there *more* *than* *one* solution?
	4. Is the algorithm *correct*?
	5. How *efficient* is the algorithm?

### Evaluating Algorithms
This includes how correct they are, and how efficient they are.

#### Correctness
There are two main ways to prove correctness, by induction, and by contradiction.

#### Efficiency
An efficient algorithm minimises time, and space (memory). In most situations there is a time-space trade off which exist

### Complexity 
The complexity is related by the amount of operations an algorithm does. Usually done in asymptomatic complexity, also known as *Big O* notation. Scalars are ignored, and instead we usually give complexity as the lowest polynomial which encapsulates the function.

Iterating over an array of size $n$ leads to a complexity of $O(n)$ regardless of the amount of times done, but iterate over an array of size $n$ for each element in $n$ gives a complexity of $O(n^2)$.

There also exist complexities such as $O (\log n)$ or even $O (n\log n)$.

#concept/abstract 