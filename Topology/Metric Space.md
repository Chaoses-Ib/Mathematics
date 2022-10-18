# Metric Space
A **metric space** is a set together with a notion of *distance* between its elements, usually called points. The distance is measured by a function called a **metric** or **distance function**. Metric spaces are the most general setting for studying many of the concepts of mathematical analysis and geometry.

## Minkowski distance
The Minkowski distance of order $p\in Z$ between two points $\mathbf X=(x_1,x_2,\cdots,x_n)$ and $\mathbf Y=(y_1,y_2,\cdots,y_n)$ is defined as:

$$D(\mathbf X, \mathbf Y) = (\sum_{n=1}^n |x_i-y_i|^p )^{1\over p}$$

- $p=1$: Taxicab metric ( $L_1$ distance, rectilinear distance, city block distance, Manhattan distance)

  $$D(\mathbf X, \mathbf Y) = \sum_{n=1}^n |x_i-y_i|$$
- $p=2$: Euclidean distance ( $L_2$ distance )

  $$D(\mathbf X, \mathbf Y) = (\sum_{n=1}^n (x_i-y_i)^2 )^{1\over 2}$$
- $p=\infty$: Chebyshev distance ( $L_\infty$ distance, maximum metric, Supremum distance)

  $$\lim_{p\to \infty} D(\mathbf X, \mathbf Y)
  = \lim_{p\to \infty} (\sum_{n=1}^n (x_i-y_i)^p )^{1\over p}
  = \max_{i=1}^n |x_i-y_i|$$