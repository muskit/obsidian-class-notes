# Example: Wumpus world
![[Pasted image 20230919144147.png]]
Our abilities:
- We can only see adjacent tiles (4 directions, no diagonal)
- We can only move to tiles adjacent as defined above

Goal: reach the **gold**
Fatal spots, Wumpus, pits
Warning signs:
- Wumpus' adjacent tiles will have stench
- Pits' adjacent tiles will have breeze
World characterization
- Not fully observable
- Deterministic
- Static
- Discrete
- Single-agent
	- Wumpus is not an opposing agent unless it has some movement logic

Everything above is described in plain language using logic. But how about logical language?

## Propositional logic
Think back to 270A.

$\sim Q$ - "not Q"
$P \implies Q$ : "P implies Q"
$(P \land Q) \implies R$ : P and Q implies R
$(P \lor Q) \implies R$ : P or Q implies R

Knowledgebase (KB; premises)
- collection of assumptions/knowledge that we assume to be true
- "Given..."

**Entailment**
"A entails B": if A is true, then B must be true for every value of A.
Given that A is true, then B should also be true.
- don't consider states where A is not true

Example:
![[Pasted image 20230919155351.png]]
![[Pasted image 20230919155306.png]]
