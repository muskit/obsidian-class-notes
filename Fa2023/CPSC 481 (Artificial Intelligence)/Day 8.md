# Adversarial Search (cont)

## Minimax
An essential algorithm for building a **game tree** that has a **utility value assigned for each game state**.

An agent (ex. maxer) can determine what node the opposing agent (ex. min'er) will likely decide on in order to decide what move to make.
## Optimizing
A game tree can get extremely deep (especially for games like Chess), which makes searching up to leaves/game-end results **infeasible**.

To solve this, we can introduce a **depth-limit**:
### Evaluation Functions
*a **weak** estimate of the utility value of an internal node*
- determines utility value based on depth-limited search (node at limit is treated as a leaf)
- **optimality** is no longer guaranteed
- how deep we should go depends on game 
### **Alpha-Beta Pruning**
https://www.youtube.com/watch?v=l-hh51ncgDI
process for an agent to eliminate paths in a game tree that will certainly not occur
- $\alpha$: value of best choice the max'er has found so far at any point in the tree (`alpha = max(alpha, eval(node|term))`)
	- initialized to worst case ($-\infty$)
	- only updated by the **maximizer**
- $\beta$: value of best choice the min'er has found so far at any point in the tree (`beta = min(beta, eval(node|term))`)
	- initialized to worst case ($+\infty$)
	- only updated by the **minimizer**
while exploring a node, we stop exploring that node whenever $\beta \leq \alpha$, effective pruning the remaining children
 