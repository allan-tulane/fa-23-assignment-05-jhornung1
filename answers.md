# CMPS 2200 Assignment 5
## Answers

**Name:** Jacob Hornung



- **1a.**  The maximum depth of a $d$-ary heap is equal to $\lfloor \log_d \left( (d - 1)n + 1 \right) \rfloor$.

- **1b.** The work for 'delete-min' is $O(log n)$ and the work for 'insert' is $O(log_d n)$.

- **1c.** The new bounds would be $O(∣V∣log d (∣V∣))$.

- **1d.** $d = |E|^{\epsilon'}$ for when $epsilon'$ is a constant greater than zero.



- **2a.**
For $k=0$:
$\mathit{APSP}(i, i, 0) = 0$ for all $i$.
No paths for $i\neq j$.

For $k=1$:
$\mathit{APSP}(1, 1, 1) = -2$.
No paths for $i\neq j$.

For $k=2$:
$\mathit{APSP}(i, i, 2) = -1$ for all $i$.
$\mathit{APSP}(0, 1, 2) = -3$.
$\mathit{APSP}(0, 2, 2) = -2$.
$\mathit{APSP}(1, 0, 2) = -2$.
$\mathit{APSP}(1, 2, 2) = 1$.
$\mathit{APSP}(2, 0, 2) = 0$.
$\mathit{APSP}(2, 1, 2) = 3$.

- **2b.** The shortest path between vertices $i$ and $j$ using vertices 0, 1, and 2 is similar to either the shortest path using only vertices 0 and 1 or the path that includes vertex 2, whichever is shorter. APSP(i,j,2) = min(APSP(i,j,1),APSP(i,2,1)+APSP(2,j,1))

- **2c.** The shortest path cost $\mathit{APSP}(i, j, k)$ is either the cost of the shortest path from $i$ to $j$ using only vertices $0, 1, \ldots, k-1$ (i.e., $\mathit{APSP}(i, j, k-1)$), or it involves vertex $k$ in the path, forming a shorter path from $i$ to $k$ followed by the shortest path from $k$ to $j$ within the vertices $0, 1, \ldots, k$. This can also be written as APSP(i,j,k) = min(APSP(i,j,k−1),APSP(i,k,k−1)+APSP(k,j,k−1)).

- **2d.**  In a top-down memoization approach, we need to compute and store the results for $n^3$ distinct subproblems, where each subproblem involves different combinations of $i$, $j$, and $k$. The memoization table helps avoid redundant computations, and the resulting work of this dynamic programming algorithm is proportional to $O(n^3)$.

- **2e.**  For small to medium-sized graphs, the dynamic programming algorithm with $O(n^3)$ complexity is preferable. Johnson's algorithm would be better for larger graphs with more copmlexity, but would not do well with cubic functions. The decision between them depends on the size and density of the graph.



- **3a.** No, a solution to the MST problem is not guaranteed to be a solution to the MMET problem. The MST may include heavy edges that minimize the sum of weights but do not necessarily minimize the mxa edge weight, which is the goal of MMET.

- **3b.** To find the next best tree after an optimal MST is unusable, sort the edges by weight and iteratively add the smallest-weight edge that doesn't create a cycle. If the resulting tree has fewer edges than the optimal MST, it is the next best tree; otherwise, stick with the optimal MST. 

- **3c.** The work is $O(E log V)$