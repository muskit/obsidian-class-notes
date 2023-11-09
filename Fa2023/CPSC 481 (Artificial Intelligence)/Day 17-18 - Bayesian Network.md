### Disadvantages of Naive Bayes
- performance may take a hit when considering too many variables
- does not account for dependent variables

# Bayesian Network
*a graph-based framework for representing and analyzing models involving uncertainty*

**graphs**...
- nodes = variables
- edges = probabilistic dependence between variables

## Example: Icy roads
A road can be **icy** or not. In either driving situations, there's always a chance of an **accident**.
![[Day 17-18 2023-10-30 20.14.05.excalidraw]]
If A crashed, even though we don't know if the road is icy, **knowing that A has crashed increases the chances of B having an accident**; there's an implication now that current conditions *may* increase the chances of accidents
- Evidence (A has crashed) increased the probability of road being icy
- If we learn later that **the roads weren't icy**, then B's chances of having an accident is DECREASED upon learning that information

Marginalization: to make the joint distribution table more compact by **summing the probability of each row for some variable**.
![[Pasted image 20231030220025.png]]
## Marginalization Problems
Probability that A has an accident
- Add up the probability entries where $A_{accident}=True$
$$\begin{align}
P(A) &= 0.072 + 0.008 + 0.042 + 0.018 \\
&= .14
\end{align}$$

Probability of icy conditions and A having an accident.
$$\begin{flalign}
P(Icy,\ A_{accident}) &= .042 + .018 \\
&= .06
\end{flalign}$$

Probability of A having an accident if it is known that Icy conditions are present.
$$\begin{aligned}
P(A_{accident}|Icy) &=\frac{P(A_{accident},\ Icy)}{P(Icy)} \\
&=\frac{.042 + .018}{.098 + .042 + .042 + .018} \\
&= .3
\end{aligned}$$

Probability that A has an accident if it is known that B had an accident (icy conditions unknown).

$$\begin{align}
P(A|B) &= \frac{P(A, B)}{P(B)} \\
&= \frac{.008 + .018}{.072 + .008 + .042 + .018} \\
&= .1857
\end{align}$$

## Setting up a Bayesian Network problem
![[Pasted image 20231030223118.png]]
$$\begin{align}
P(Cloudy, !Freezing, Accident) &= 0.75 \times .667 \times 0.5 \\
&= .25
\end{align}$$