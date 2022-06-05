# Asymptomatic Complexity
### Complexity 
The complexity is related by the amount of operations an algorithm does. Usually done in asymptomatic complexity, also known as *Big O* notation. Also usually looks at worst case. Scalars are ignored, and instead we usually give complexity as the lowest polynomial which encapsulates the function.

Iterating over an array of size $n$ leads to a complexity of $O(n)$ regardless of the amount of times done, but iterate over an array of size $n$ for each element in $n$ gives a complexity of $O(n^2)$.

There also exist complexities such as $O (\log n)$ or even $O (n\log n)$.

Polynomial complexities are regarded as **feasible** while exponential complexities are regarded as **infeasible**.

### Formal Definition for Big O
$f(n)$ is $(g(n))$ if there is a constant $c > 0$ and an integer $n_0 >= 1$ : $\forall \hspace{2mm} n >= n_0$,
$$f(n) <= cg(n)$$
This means for any algorithm with $O(n)$, it can also be said that that algorithm is also $O(n^2)$ or $O(n^3)$. But not $O(\log n)$.


### Recurrence Relation
A method to express time or space recursively.

#status/todo from second last lecture