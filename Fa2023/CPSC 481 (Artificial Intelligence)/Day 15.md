# Conditional Probability
Phrasing an Example in Probability
- Medical: given this medical test turns positive, what's the probability of a disease occurring?

$P(A | B)$
- probability that $A$ occurs, given that $B$ certainly occurs.

$P(A,B)$
- probability that $A$ AND $B$ occurs
$P(A,B')$
- probability that $A$ occurs given that $B$ DOESN'T occur
$P(A',B)$
- probability that $A$ doesn't occur when $B$ occurs
- false positive (medical example): probability that a patient doesn't have a disease given that a medical test turns positive

**Definition of a conditional probability**
$P(a|b) = \frac{P(a,b)}{P(b)}$

$P(x,y) = P(x|y)P(y)$
$= P(y|x)P(x)$

Given defined probabilities distributions $P(A)$ and $P(B)$ where their sum is $1$:
- $P(a,b) = P(a)\times P(b)$

## Bayes' Rule
$P(a|b) = \frac{P(b|a)P(a)}{P(b)}$
- let's us find a value by using the inverse relationship
- useful if what we're trying to calculate is too complex
- used to find **posterior conditional probabilities**

## Example
1/1000 people have **cancer**
**True positive rate** for a test is .99
**False positive rate** for a test is .02
Given a random subject tests positive for cancer, what's the probability they truly have cancer?

$A$ = has disease
$A'$ = doesn't have disease
$B$ = positive test
$P(A'|B)$ = false positive test

**Given probabilities:**
$P(A)=.001$
$P(A') = .999$
$P(B) = .99$
$P(B|A') = .2$
![[Pasted image 20231010153614.png]]
$P(B)=P(A, B) + P(A',B)$
- Probability of a positive test is the sum of \[positive test AND has disease] and \[positive test AND DOESN'T have disease]