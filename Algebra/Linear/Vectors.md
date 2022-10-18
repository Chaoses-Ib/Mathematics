# Vectors
An array $x$ of $n$ real numbers $x_1,x_2,...,x_n$ is called a **vector**, and is written as[^applied-multi-stat]

$$\mathbf{x}=\begin{bmatrix}x_1 \\ x_2 \\ ... \\ x_n\end{bmatrix}
\quad\text{or}\quad
\mathbf{x}'=\begin{bmatrix}x_1,x_2,...,x_n\end{bmatrix}
$$

## Norm
A **norm** is a function from a real or complex vector space to the non-negative real numbers that behaves in certain ways like the distance from the origin: it commutes with scaling, obeys a form of the triangle inequality, and is zero only at the origin.[^norm-wiki]

## Linear dependence
A set of vectors $\mathbf{x_1},\mathbf{x_2},\cdots,\mathbf{x_k}$ of the same dimension is said to be **linearly dependent**
if there exist constants $c_1,c_2,\cdots,c_k$, not all zero, such that
$$c_1\mathbf{x_2}+c_2\mathbf{x_2}+\cdots+c_k\mathbf{x_k}=0$$

Linear dependence implies that at least one vector in the set can be written as a linear combination of the other vectors.[^applied-multi-stat]

[^norm-wiki]: [Norm (mathematics) - Wikipedia](https://en.wikipedia.org/wiki/Norm_(mathematics))
[^applied-multi-stat]: *Applied Multivariate Statistical Analysis*