# Conjunctive Normal Form
[Wikipedia](https://en.wikipedia.org/wiki/Conjunctive_normal_form)

A formula is in **conjunctive normal form (CNF, clausal normal form)** if it is a conjunction of one or more clauses, where a clause is a disjunction of literals; otherwise put, it is a **product of sums** or **an AND of ORs**.

Converting to CNF[^ai-modern]:
1. Eliminate ⇔, replacing α ⇔ β with (α ⇒ β)∧ (β ⇒ α)
2. Eliminate ⇒, replacing α ⇒ β with ¬α ∨ β
3. CNF requires ¬ to appear only in literals, so we “move ¬ inwards” by repeated application of the following equivalences:
   - ¬(¬α) ≡ α  (double-negation elimination)
   - ¬(α ∧ β) ≡ (¬α ∨ ¬β)  (De Morgan)
   - ¬(α ∨ β) ≡ (¬α ∧ ¬β)  (De Morgan)
4. Now we have a sentence containing nested ∧ and ∨ operators applied to literals. We apply the distributivity law, distributing ∨ over ∧ wherever possible.


[^ai-modern]: Russell, Stuart J. _Artificial Intelligence a Modern Approach_. Pearson Education, Inc., 2010.