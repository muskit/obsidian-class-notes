# Propositional Logic (cont.)
*proof*- a sequence of sentences where each sentence

### Rules
**Resolution Rule**
$A\lor B,\neg B\lor C \equiv A\lor C$
$A \lor B, \neg B \equiv A$

**Converting a statement to *Conjunctive Normal Form* (CNF)**
Eliminating the "implies" ($\rightarrow$) and having only conjunctions ($\land$) at the top level of our statement

**Removing $\rightarrow$**
$\alpha \rightarrow \beta \equiv \neg\alpha \lor \beta$

**Removing $\leftrightarrow$**
$\alpha \leftrightarrow \beta \equiv (\alpha \rightarrow \beta) \land (\beta \rightarrow \alpha)$

**Distributive Property**
$(A \land B) \lor C \equiv (A \lor C) \land (B \lor C)$

**DeMorgan's Law**
$\neg (\alpha \land \beta) \equiv \neg\alpha\lor\neg\beta$
$\neg (\alpha \lor \beta) \equiv \neg\alpha\land\neg\beta$

**Back to statements**
$A \land B$ becomes
1. A
2. B

### Proof by Resolution Refutation
Given a premise, does the conclusion hold up?

Effectively a *proof by contradiction*:
1. Convert all premises to CNF
2. Add **negated** conclusion
3. Apply rules of resolution until
	- FALSE (contradiction; ie. $R \land \neg R$): conclusion is VALID
	- Cannot contradict or apply more rules; conclusion CANNOT be proved