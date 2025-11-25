# Project Review: Issues & Fixes

Very good work, I propose only one small fix

## 1. A* Heuristic Admissibility
**Problem:**
The A* implementation uses Euclidean distance as a heuristic. For A* to guarantee an optimal path, the heuristic must be **admissible** ($h(n) \le cost(n, goal)$).
Two factors compromised admissibility:
1.  **Negative Noise:** If `negative_values` is `True`, the noise term can be negative, reducing the edge weight below the Euclidean distance.
2.  **Rounding:** The graph generation rounds weights to the nearest integer (`(problem * 1000).round()`). If a distance of `100.4` is rounded to `100`, the heuristic `100.4` exceeds the actual weight.

**Fix Applied:**
The `heuristic` function in `solve_instance_astar` has been updated:
- If `negative_values` is `True`, it returns `0.0` (falling back to Dijkstra behavior), as the Euclidean distance cannot be trusted.
- Otherwise, it subtracts `0.5` from the calculated distance to account for potential rounding down in the weight generation, ensuring $h(n) \le weight$.


## Comment

I don't find the function "benchmark_astar_once", i think it is similar to "benchmark_dijkstra_once"
