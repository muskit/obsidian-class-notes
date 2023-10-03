# Ethics (cont.)
## Privacy
*de-identification*- elimination of personally-identifying info
- ie. name, address, SSN
	- just partial of any of these elements can be enough to reconnect individuals maliciously (ie. cross-referencing different datasets)
- data needs to be publicised for other researchers, so we make sure privacy is preserved
- what should be omitted depends on context/study

Solution to the partial-reconnection problem: *k-anonymity*
- intentionally hide **part of the elements**
	- ie. zipcode = 130**, age groups instead of exact
	- *k*: given any row, there are $k-1$ **other rows** which have the same identifying values
	- each "anonymized" column is a *quasi-identifier*

### Anonymization techniques
1. Data swapping: interchange values between records
	- ie. swap/reorganizing data points as to not affect data operations (like averaging)
 2. Randomization: add random noise to data
	 - ie. alter subjects' age slightly within range of error
3. Generalization: be less specific about subjects' properties
	- (ie. zipcode = 130**, 24 years old --> age 20-30)
4. Suppression: don't release detail at all
	- ie. don't release location of subject at all

