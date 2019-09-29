## First-Order Logic


### Comparison

![language](./pix/language.png)

### Syntax

BNF (Backus–Naur Form) grammar of sentences in first-order logic:
* **constant symbols** -> objects
* **predicate symbols** -> relations
* **function symbols** -> functions 
* predicate symbols and function symbos have **arity**, which fixes the number of arguments
* **universal quantification**: ∀x King(x) ⇒ Person(x) 
* **existential quantification**: ∃x Crown(x) ∧ OnHead(x, John)
* **equality symbol**: 
	* Father(John) = Henry -> the object referred to by Father(John) and the object referred to by Henry are the same
	* ∃x,y Brother(x, Richard) ∧ Brother(y, Richard) ∧ ¬(x=y) -> two variables are not the same by negation

![syntax](./pix/syntax.png)

### Logical equivalences

 ∀ is a conjunction over objects, and ∃ is a disjunction over objects, so they obey De Morgan’s rules:
 * ∀x Likes(x, IceCream) ≡ ¬∃x ¬Likes(x, IceCream)
 * ∀x ¬Likes(x, Parsnips) ≡ ¬∃x Likes(x, Parsnips)
 
 ![de-morgans-rule](./pix/de-morgans-rule.png)


### Knowledge Base

**assertions**: sentences that are added to a knowledge base using TELL
* TELL(KB, King(John)) 
* TELL(KB, ∀x King(x) ⇒ Person(x)) 

**queries** or **goals**: questions that are asked to a knowledge base using ASK
* ASK(KB, Person(John))
* any query that is logically entailed by the knowledge base should be answered affirmatively -> ASK(KB, Person(John)) returns true

**theorems**: theorems are entailed by **axioms**


### Reduction to propositional inference

**universal instantiation**: any sentence can be inferred by substituting the variable with a **ground term** (constant symbol or function symbol).
* ∀v α -> SUBST({v/g}, α)
* ∀x King(x) ∧ Greedy(x) ⇒ Evil(x) -> {x/John}, {x/Richard}, {x/Father(John)}
* universal instantiation can be applied many times to produce many different consequences.

**existential instantiation**: any sentence can be inferred by substituting the variable with a single new constant symbol (**skolem constant**).
* ∃v α -> SUBST({v/k}, α)
* ∃x Crown(x) ∧ OnHead(x, John) -> Crown(C1) ∧ OnHead(C1, John)
* existential instantiation can be applied once, and then the existentially quantified sentence can be discarded.

the new knowledge base is not **logically equivalent** to the old, but it can be shown to be **inferentially equivalent** in the sense that it is satisfiable exactly when the original knowledge base is satisfiable.

### First-logic inference rule

**unification**: the UNIFY algorithm takes two sentences and returns a unifier for them if one exists.
* UNIFY(p, q) = θ where SUBST(θ, p) = SUBST(θ, q)
* AskVars(Knows(John, x)) -> UNIFY(Knows(John, x), Knows(John, Jane)) = {x/Jane}

**generalized Modus Ponens**: 
* p1', p2', ..., pn', (p1 ∧ p2 ∧ ... ∧ pn ⇒ q) where SUBST(θ, pi') = SUBST(θ, pi), for all i -> SUBST(θ, q)
* it is a lifted version of Modus Ponens which uses unification to provide a natural and powerful inference rule.
* **forward chaining** and **backward chaining** algorithms apply this rule to sets of **definite clauses**.

**first-order definite clauses**:
* first-order literals can contain variables, which are assumed to be universally quantified.
* King(x) ∧ Greedy(x) ⇒ Evil(x)
* King(John)
* Greedy(y)

**resolution inference rule**
* l1 ∨ ··· ∨ lk, m1 ∨ ··· ∨ mn where UNIFY(li, ¬mj) = θ -> SUBST(θ, l1 ∨ ··· ∨ li−1 ∨ li+1 ∨ ··· ∨ lk ∨ m1 ∨ ··· ∨ mj−1 ∨ mj+1 ∨ ··· ∨ mn)
* [Animal(F(x)) ∨ Loves(G(x), x)] and [¬Loves(u, v) ∨ ¬Kills(u, v)] -> Loves(G(x), x) and ¬Loves(u, v) with unifier θ = {u/G(x), v/x} to produce the **resolvent clause**:  [Animal(F(x)) ∨ ¬Kills(G(x), x)]
* resolution inference rule is applied to first-order CNF.

**first-order CNF (Conjunctive Normal Form)**:
* first-order literals can contain variables, which are assumed to be universally quantified.
* ∀x American(x) ∧ Weapon(y) ∧ Sells(x, y, z) ∧ Hostile(z) ⇒ Criminal(x) -> ¬American(x) ∨ ¬Weapon(y) ∨ ¬Sells(x, y, z) ∨ ¬Hostile(z) ∨ Criminal(x)
* every sentence of first-order logic can be converted into an **inferentially equivalent** CNF sentence.


