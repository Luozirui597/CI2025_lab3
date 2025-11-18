# CI2025_lab3
### Handling negative edge weights

First, I tested Dijkstra and A* on a subset of parameter settings. As soon as negative edge weights appeared, both algorithms failed to compute valid shortest paths, so I switched to the Bellman–Ford algorithm for those cases.

However, on some graphs Bellman–Ford encounters negative cycles. From a mathematical point of view, this means that no finite shortest path exists: the algorithm could keep traversing the negative cycle indefinitely, driving the total cost towards negative infinity. In such cases, we treat the shortest path as undefined.


### Behavior with negative edge weights

- **Step 1 – Dijkstra & A\***  
  I first tested Dijkstra and A\* on a subset of parameter settings.  
  For graphs with non-negative edge weights, both algorithms returned valid shortest paths.

- **Step 2 – Switch to Bellman–Ford**  
  When negative edge values appeared, Dijkstra and A\* could no longer be applied, so I switched to the Bellman–Ford algorithm for those instances.

- **Step 3 – Negative cycles**  
  On some generated graphs, Bellman–Ford detects negative cycles.  
  From a mathematical perspective, this implies that no well-defined shortest path exists between source and target: the algorithm could traverse the negative cycle infinitely many times, pushing the path cost towards \(-\infty\).  
  In these cases, the instance is classified as “no shortest path (negative cycle)”.
