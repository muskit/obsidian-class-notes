# Search Heuristics
*heuristic*: a **function** - how close a state is to a goal

## Greedy Best-First Search
Expand only nodes that appear to be **closest to goal**
- "Pure heuristic search"
- does not consider path cost that UCS/Dijkstra's considers

Issues
- not optimal
- not complete: can get stuck in dead ends
- heuristic cost vs. true cost

## A* Search
Combines UCS/Dijkstra's and Greedy Best-First
- UCS orders by path cost (backward cost: $g(n)$)
- Greedy orders by proximity (forward cost: $h(n)$)
- $A^* = g(n) + h(n)$
- A* is literally UCS, but frontier is ordered by $cost_{path}+cost_{heur}$
- 