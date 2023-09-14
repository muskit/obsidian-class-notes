# Adversarial Search (cont)

## Optimizing
A game tree can get extremely deep (especially for games like Chess), which makes searching up to leaves/game-end results **infeasible**

To solve this, we can introduce a **depth-limit**.
### Evaluation Functions
*a **weak** estimate of the utility value of an internal node*
- determines utility value based on depth-limited search (node at limit is treated as a leaf)
- **optimiality** is no longer guaranteed
- how deep we should go depends on game 
### Minmax Pruning
An agent (ex. maxer) can determine what node the opposing agent (ex. min'er) will likely decide on in order rule out which nodes can be ignored (pruned).

### **Alpha-Beta Pruning**
- $\alpha$: value of best choice the max'er has found so far at any point in the tree 
- $\beta$: value of best choice the min'er has found so far at any point in the tree