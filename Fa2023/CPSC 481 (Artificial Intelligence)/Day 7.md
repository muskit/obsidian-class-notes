# Search Heuristics cont.
Recall:
*heuristic*- the "distance" a state is from the goal
- not always a literal distant in space
- ex: in a sliding tiles puzzle, heuristic can be the number of tiles in an incorrect spot

# Adversarial Search
## Modelling AI on Games
Game-playing make a good subject for AI:
- well-defined, reasonable rules: formal, trivial
- direct comparison with humans

There exists various types of games, which all for different kinds of AI situations (deterministic vs stochastic, # players, zero-sum, etc)

Zero-sum: only one winner
- has clearly-defined winners & losers
- pure competition
- single value: one maxes, other mins
**In this course, we will focus on zero-sum games.**

### Game Tree
![[Day 7 2023-09-12 15.06.25.excalidraw]]
Utility value: our "heuristic"
- Min/max: opponent tries to minimize player's utility val, player tries to maximize utility val
- Agents try to find the best path through tree to achieve desired utility val (min'ing or max'ing)

### Game Tree for Halving Game w/ n=5
