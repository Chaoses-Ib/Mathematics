# Propositional Logic
[Wikipedia](https://en.wikipedia.org/wiki/Propositional_calculus)

**Propositional logic (propositional calculus, statement logic, sentential calculus, sentential logic, zeroth-order logic)** deals with propositions (which can be true or false) and relations between propositions, including the construction of arguments based on them.

Grammar:
```
Sentence        → AtomicSentence | ComplexSentence
AtomicSentence  → True | False | Symbol 
Symbol          → P | Q | R | . . . 
ComplexSentence → ¬ Sentence 
                | ( Sentence ∧ Sentence ) 
                | ( Sentence ∨ Sentence ) 
                | ( Sentence ⇒ Sentence ) 
                | ( Sentence ⇔ Sentence )
```