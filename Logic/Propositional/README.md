# Propositional Logic
[Wikipedia](https://en.wikipedia.org/wiki/Propositional_calculus)

**Propositional logic (propositional calculus, statement logic, sentential calculus, sentential logic, zeroth-order logic)** deals with propositions (which can be true or false) and relations between propositions, including the construction of arguments based on them.

Grammar:
```
Sentence        → AtomicSentence | ComplexSentence
AtomicSentence  → True | False | Symbol 
Symbol          → P | Q | R | . . . 
ComplexSentence → ¬ Sentence 
                | Sentence ∧ Sentence
                | Sentence ∨ Sentence
                | Sentence ⇒ Sentence
                | Sentence ⇔ Sentence
Operator percedence: ¬, ∧, ∨, ⇒, ⇔
```

- Conjunction (and, $\land$, 合取)
- Disjunction (or, $\lor$, 析取)

  [我在思考数学中析取中析的来源_科星球_百度百科](https://baike.baidu.com/planet/issue?issueId=445624&fromModule=issue-list_issue-list)
- $P \implies Q$ is true unless $P$ is true and $Q$ is false.

  Propositional logic does not require any relation of causation or relevance between $P$ and $Q$. The sentence “5 is odd implies Tokyo is the capital of Japan” is a true sentence of propositional logic, even though it is a decidedly odd sentence of English.
  
  Another point of confusion is that any implication is true whenever its antecedent is false. For example, “5 is even implies Sam is smart” is true, regardless of whether Sam is smart.
  
  This seems bizarre, but it makes sense if you think of “$P \implies Q$” as saying, “If $P$ is true, then I am claiming that $Q$ is true; otherwise I am making no claim.” The only way for this sentence to be false is if $P$ is true but $Q$ is false.[^ai-modern]


[^ai-modern]: Russell, Stuart J. _Artificial Intelligence a Modern Approach_. Pearson Education, Inc., 2010.