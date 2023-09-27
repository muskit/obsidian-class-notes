# Propositional Logic (cont.)
### Back to [[Day 9#Example Wumpus world|Wumpus' World]]
We can use propositional logic to represent the world's state
The issue: we have to show the state for **every single tile**
- will get lengthy if we have to show multiple states
# Predicate (/First Order) Logic
Super-set of propositional logic
- variables (to represent objects in the world)
- predicates (to represent relationship between objects)
- functions
	- inputs and outputs are objects
Additional symbols compared to propsitional:
- universal quantification ($\forall$)
	- $\forall x P(x)$ - P holds for **all** values in $x$'s domain
	- $\forall x \ student(x) \implies smart(x)$ - "All students are smart"
- Existential quantification ($\exists$)
	- $\exists x P(x)$ - P holds for **some** values in $x$'s domain
	- $\exists x\ \implies smart(x)$ - "There exists a student $x$ that is smart"
		- not always right; if someone is NOT a student but is smart, then this statement holds

The order of same qualifiers doesn't change meaning.
However, reordering mixed qualifiers **will** change meaning
- $\forall x \exists f\ food(f) \land likes(x, f)$ - Everyone likes some food.
- $\exists f \forall x\ food(f) \land likes(x, f)$ - There is one specific food that everyone likes.

**De Morgan's Law**
$\forall x\ P(x) \Leftarrow \Rightarrow \neg\exists x\ \neg P(x)$
$\exists x\ P(x) \Leftarrow\Rightarrow \neg \forall x\ \neg P(x)$

