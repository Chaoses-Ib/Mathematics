# Entailment
[Wikipedia](https://en.wikipedia.org/wiki/Logical_consequence)

The formal deﬁnition of entailment is: $\alpha\models\beta$ if and only if, in every model in which $\alpha$ is true, $\beta$ is also true, i.e.
$$\alpha \models \beta \text{ if and only if } M(\alpha)\subseteq M(\beta)$$
where $M(\alpha)$ is the set of all models of $\alpha$.

If an inference algorithm $i$ can derive $\alpha$ from KB, we write
$$KB \vdash_i \alpha$$
which is pronounced “$\alpha$ is derived from KB by $i$” or “$i$ derives $\alpha$ from KB.”[^ai-modern]

- An inference algorithm that derives only entailed sentences is called **sound (truth-preserving)**.
- An inference algorithm is **complete** if it can derive any sentence that is entailed.

## Model checking
```
function TT-ENTAILS?(KB, α) returns true or false
  inputs: KB, the knowledge base, a sentence in propositional logic
          α, the query, a sentence in propositional logic
  
  symbols ← a list of the proposition symbols in KB and α
  return TT-CHECK-ALL(KB, α, symbols, {})

function TT-CHECK-ALL(KB, α, symbols, model) returns true or false
  if EMPTY?(symbols) then
    if PL-TRUE?(KB, model) then return PL-TRUE?(α, model)
    else return true  // when KB is false, always return true
  else
    P ← FIRST(symbols)
    rest ← REST(symbols)
    return (TT-CHECK-ALL(KB, α, rest, model ∪ {P = true})
            and
            TT-CHECK-ALL(KB, α, rest, model ∪ {P = false}))
```
where TT stands for truth table. PL-TRUE? returns true if a sentence holds within a model. The variable model represents a partial model—an assignment to some of the symbols.

TT-ENTAILS? performs a recursive enumeration of a ﬁnite space of assignments to symbols. The algorithm is sound because it implements directly the deﬁnition of entailment, and complete because it works for any KB and $\alpha$ and always terminates—there are only ﬁnitely many models to examine. The time complexity of the algorithm is $O(2^n)$. (The space complexity is only $O(n)$ because the enumeration is depth-ﬁrst.)

Propositional entailment is co-NP-complete (i.e., probably no easier than NP-complete) so every known inference algorithm for propositional logic has a worst-case complexity that is exponential in the size of the input.[^ai-modern]

## Theorem proving
**Theorem proving** applys rules of inference directly to the sentences in our knowledge base to construct a proof of the desired sentence without consulting models. If the number of models is large but the length of the proof is short, then theorem proving can be more efﬁcient than model checking.

**Logical equivalence**: two sentences $\alpha$ and $\beta$ are logically equivalent if they are true in the same set of models. We write this as $\alpha\equiv\beta$. An alternative deﬁnition of equivalence is as follows: any two sentences $\alpha$ and $\beta$ are equivalent if and only if each of them entails the other:
$$\alpha\equiv\beta\text{ if and only if }\alpha\models\beta\text{ and }\beta\models\alpha$$
A sentence is **valid** if it is true in all models. Valid sentences are also known as tautologies—they are necessarily true.Because the sentence True is true in all models, every valid sentence is logically equivalent to True.

From our deﬁnition of entailment, we can derive the **deduction theorem**:

$$\text{For any sentences }\alpha\text{ and }\beta,\alpha\models\beta\text{ if and only if the sentence }(\alpha\implies\beta)\text{ is valid}$$

Hence, we can decide if $\alpha\models\beta$ by checking that $(\alpha\implies\beta)$ is true in every model—which is essentially what the model checking algorithm does.

A sentence is **satisﬁable** if it is true in, or satisﬁed by, some model. The problem of determining the satisﬁability of sentences in propositional logic—the **SAT** problem—was the ﬁrst problem proved to be NP-complete. Many problems in computer science are really satisﬁability problems. For example, all the constraint satisfaction problems ask whether the constraints are satisﬁable by some assignment.

Validity and satisﬁability are of course connected: $\alpha$ is valid iff $\lnot\alpha$ is unsatisﬁable; contrapositively, $\alpha$ is satisﬁable iff $\lnot\alpha$ is not valid. We also have the following useful result: 

$$\alpha\models\beta\text{ if and only if the setence }(\alpha\land\lnot\beta)\text{ is unsatisfiable}$$

Proving $\beta$ from $\alpha$ by checking the unsatisﬁability of $(\alpha\land\lnot\beta)$ corresponds exactly to the standard mathematical proof technique of **reductio ad absurdum** (literally, “reduction to an absurd thing”). It is also called **proof by refutation** or **proof by contradiction**. One assumes a sentence $\beta$ to be false and shows that this leads to a contradiction with known axioms $\beta$. This contradiction is exactly what is meant by saying that the sentence $(\alpha\land\lnot\beta)$ is unsatisﬁable.

One ﬁnal property of logical systems is **monotonicity**, which says that the set of entailed sentences can only increase as information is added to the knowledge base. For any sentences $\alpha$ and $\beta$:[^ai-modern]

$$\text{if }KB\models\alpha\text{ then }KB\land\beta\models\alpha$$

### Proof by resolution
A simple resolution algorithm for propositional logic[^ai-modern]:
```
function PL-RESOLUTION(KB, α) returns true or false
  inputs: KB, the knowledge base, a sentence in propositional logic
          α, the query, a sentence in propositional logic
  clauses ← the set of clauses in the CNF representation of KB ∧ ¬α
  new ← {}
  while true do
    for each pair of clauses Ci, Cj in clauses do
      resolvents ← PL-RESOLVE(Ci,Cj)
      if resolvents contains the empty clause then return true
      new ← new∪resolvents
    if new ⊆ clauses then return false
    clauses ← clauses∪new
```

### Forward chaining
The forward-chaining algorithm PL-FC-ENTAILS?(KB, q) determines if a single proposition
symbol q—the query—is entailed by a knowledge base of deﬁnite clauses. It begins from
known facts (positive literals) in the knowledge base. If all the premises of an implication are known, then its conclusion is added to the set of known facts. This process continues until the query q is added or until no further inferences can be made. The main point to remember is that it runs in linear time.

```
function PL-FC-ENTAILS?(KB, q) returns true or false
  inputs: KB, the knowledge base, a set of propositional deﬁnite clauses
          q, the query, a proposition symbol
  count ← a table, where count[c] is initially the number of symbols in clause c’s premise
  inferred ← a table, where inferred[s] is initially false for all symbols
  queue←a queue of symbols, initially symbols known to be true in KB
  
  while queue is not empty do
    p←POP(queue)
    if p = q then return true
    if inferred[p] = false then
      inferred[p] ← true
      for each clause c in KB where p is in c.PREMISE do
        decrement count[c]
        if count[c] = 0 then add c.CONCLUSION to queue
  return false
```

Forward chaining is an example of the general concept of **data-driven reasoning**—that is, reasoning in which the focus of attention starts with the known data. It can be used within an agent to derive conclusions from incoming percepts, often without a speciﬁc query in mind.[^ai-modern]

### Backword chaining
The backward-chaining algorithm, as its name suggests, works backward from the query. If the query q is known to be true, then no work is needed. Otherwise, the algorithm ﬁnds those implications in the knowledge base whose conclusion is q. If all the premises of one of those implications can be proved true (by backward chaining), then q is true. As with forward chaining, an efﬁcient implementation runs in linear time.

Backward chaining is a form of **goal-directed reasoning**. Often, the cost of backward chaining is much less than linear in the size of the knowledge base, because the process touches only relevant facts.[^ai-modern]


[^ai-modern]: Russell, Stuart J. _Artificial Intelligence a Modern Approach_. Pearson Education, Inc., 2010.