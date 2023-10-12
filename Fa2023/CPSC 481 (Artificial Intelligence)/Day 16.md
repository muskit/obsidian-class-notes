# Exam Notes
**2 pages of double-sided notes allowed**
- typed/handwritten allowed

# Probabilities (cont.)
## Naive Bayes Classifier
- uses arguments/features involved to calculate conditional proabilities
- assumes that attributes are **conditionally independent**
ie. `P(PlayTennis | sunny, temp: cool, winds: strong)`
- should we play tennis given that it's sunny and cool with strong winds?

Practical scenario: running *multiple* tests to determine if someone has cancer

To calculate, we simply multiply the **prior probabilities** given other features **independently**
- prior probabilities is our **training data**
### Play Tennis Example
*Prior probabilities table*
![[Pasted image 20231012145016.png]]
*What are the chances that we play tennis, given...*
![[Pasted image 20231012144711.png]]

**Normalizing**
Though we know which one is bigger, they're not actually probability values yet (needs to sum to 1).

We need to *normalize* the values to make them probability values (sum to 1)
- do this by dividing each number ($P(yes)$ & $P(no)$) by the sum of its values
- ie. normalized $P(yes) = \frac{P(yes)}{P(yes) + P(no)}$

## E-mail Spam-filtering Example
features of each email:
- sender's domain
- sender's username contains numbers
- subject contains exclamation points ("`!`")
