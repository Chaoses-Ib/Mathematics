# Binary Operations
## Properties
Denote $\circ,\diamond$ binary operations on a set $S$.

- Commutative (交换律): $\forall x,y\in S,\quad x\circ y=y\circ x$
- Associative (结合律): $\forall x,y,z\in S,\quad (x\circ y)\circ z=x \circ (y\circ z)$
- Distributive (分配律)
  - Left-distributive: $\forall x,y,z\in S,\quad x\diamond (y \circ z)=(x \diamond y) \circ (x\diamond z)$
  - Right-distributive: $\forall x,y,z\in S,\quad (y \circ z)\diamond x = (y \diamond x) \circ (z\diamond x)$
  
  When $\circ$ is commutative, $\text{distributive}\iff\text{left-distributive}\iff\text{right-distributive}$.