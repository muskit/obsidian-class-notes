# Supervision Learning
- learning from training set with expected inputs/outputs **labeled** by a human

*regression*: give an input, get an output (typically a number)
	- linear regression
 
*classification*: give an input, get a classifier (categorize data)
	- ex: e-mail spam filtering

# Unsupervised Learning
- **inferring** from data with no particular labels
- Cluster Analysis
	- *k-means* algorithm
	- Visualization of similar things
- Dimensionality Reduction
	- simplify data w/o losing too much info (ie. merging several correlated features)
- Association Rule Learning
	- discover relations in large data between attributes

# Semi-supervised Learning
Training with a combination of both labeled and unlabeled data.

# Reinforcement Learning
**There is no initial training phase.**

Agents observe environment, take action, and **receive rewards or penalties based on action**.
- action is decided via a **policy**, which updates based on situation (the "learning" while doing)

Reinforcement: learn incrementally
Traditional ML: learn from Big Data

Best in situations requiring adaptability

used in autonomy, games, self-driving cars, personalized recommendations

## Elements in RL
- Agent
	- the object which is trying to maximize rewards via actions
	- Interacts with environment
- Goal: the milestone that agent wishes to accomplish
- Environment
	- representation of domain in terms of states
	- ie. location of vehicle on streets, representation of a chessboard
- Action
- Reward
- Policy
	- a **knowledgebase** which captures rules and patterns

# Batch Learning
Training with all available data
- requires massive computing resource and time
- not as adaptable

# Online Learning
Incrementally train by feeding data instances sequentially
- processes smaller sets of data at a time; less memory usage
- best used when resources are limited

# Instance-based Learning
Compare new data to known data and generalize new cases by similarity

# Model-based Learning
Build model from training data and make predictions from that model

Training process:
1. Study training data
2. Select a model
3. Training model on data
4. Apply model to make predictions