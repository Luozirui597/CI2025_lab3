# CI2025_lab3



### Behavior with negative edge weights

- **Step 1 – Dijkstra & A\***  
  I first tested Dijkstra and A\* on a subset of parameter settings.  
  For graphs with non-negative edge weights, both algorithms returned valid shortest paths.

- **Step 2 – Switch to Bellman–Ford**  
  When negative edge values appeared, Dijkstra and A\* could no longer be applied, so I switched to the Bellman–Ford algorithm for those instances.

- **Step 3 – Negative cycles**  
  On some generated graphs, Bellman–Ford detects negative cycles.  
  From a mathematical perspective, this implies that no well-defined shortest path exists between source and target: the algorithm could traverse the negative cycle infinitely many times, pushing the path cost towards infinity.  
  In these cases, the instance is classified as “no shortest path (negative cycle)”.
