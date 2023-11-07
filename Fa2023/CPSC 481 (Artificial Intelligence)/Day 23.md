# Setting up an ML project
1. Set up the Goal
	- Business objective? Current solutions?
	- Supervised? Unsupervised?
		- Classification, regression, or recommendation?
	- Define performance: what does success look like?
2. Prepare the Dataset
	- Locate, procure, read
		- Can create dataset if appropriate dataset cannot be found for application; **takes a long time**
		- Companies/solutions exist to generate datasets
		- Consider limitations and licenses
	- Split dataset
		- Training Set: the set used to train the model
			- typ. 80% of dataset
		- Test Set: see how accurate our model is
			- typ. 20% of dataset
			- Python's `scikit-learn` has a function for splitting: `train_test_split(set, ratio of data to use)
3. Comprehend the Dataset
	- Observe the dataset (ie. visualizations)
	- Find correlations
		- *correlation coefficient*: **strength** of the relationship between two variables
			- only capable of linear correlations
			- range: [-1, 1]
			- ![[Pasted image 20231107145714.png]]
			- Python: `pandas.DataFrame.corr`
4. Clean up the Dataset
	- Remove erroneous data from training set
		- bias
		- noise
		- outlier
		- ambiguity
		- missing features
5. Train with ML Algorithm
	- Choose algorithm based on task
	- Train model
	- Test it; attempt to make predictions
6. Tune the ML model
	- Grid search (try every combination of hyperparameters)
		- brute-force: will result in optimal combinations
		- best results, but is a time-consuming process
	- Random search (try random combinations)
	- Bayesian Optimization (uses probability)
	- Automated ML frameworks
		- AutoML; cloud-based solutions
7. Deploy the ML Model
	- Install model
	- Prep for predictions
	- Methods of deployment
		- local
		- server (ie. can be queried via REST API)
		- cloud (ie. Google Cloud AI Platform)