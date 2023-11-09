# Decision Tree
*allows for decision-making based on the dataset's subsets **(classification)***
- constructed during **model training**

Consists of...
- root node
	- divides the whole dataset into 2+ sets
- decision node
	- splits input dataset based on criteria (decides)
- leaf (terminal) node
	- class; result of classification

## Decision Tree Process
1. **Model Training:** tree construction using training dataset
2. **New Data Point**: user *inputs* certain observation(s)
3. **Prediction**: use features of data point(s) (user input) to navigate tree and reach a leaf
4. **Output**: prediction for given data point

Example: patient's risk for a disease given the patient's certain features and criteria based on those features
![[Pasted image 20231109144910.png]]

## D.Tree generation algorithms
- Classification And Regression Tree (CART)
	- generates binary tree
- Iterative Dichotomiser 3 (ID3)
	- generates n-ary trees
	- uses entropy
- C5.0
	- improved ID3: faster, less memory usage
	- can handle both continuous and discrete features

## Considerations for D.Tree generation
- greedy strategies
- splitting process details
	- specifying test conditions
	- determining the best split
- when to stop splitting

## Specifying test conditions
**There are two considerations as follows**

Attribute type
- Nominal: independent (unordered) discrete values
	- ie. countries, colors, ZIP codes
- Ordinal: discrete values with relationships (order)
	- ie. grade, cancer stage
- Continuous
	- ie. age, height, distance

Splitting
- 2-way split: binary tree
- multi-way split: n-ary tree