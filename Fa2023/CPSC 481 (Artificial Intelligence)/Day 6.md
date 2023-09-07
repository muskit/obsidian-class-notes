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
**A* is literally [[Fa2023/CPSC 481 (Artificial Intelligence)/Day 5#Dijkstra's Algorithm|UCS/Dijkstra's]], but frontier is ordered by $cost_{path}+cost_{heur}$ instead of just $cost_{path}$**

Optimality depends on costs/heuristic data being **admissible**

Search algorithm properties
- Complete
- Optimal
- Optimally efficient
	- no other optimal algorithm expands fewer nodes
 - Time complexity
	 - worst case number of states is exponential
	 - \# of states depends on error
  - Space complexity
	  - all generated nodes: exponential