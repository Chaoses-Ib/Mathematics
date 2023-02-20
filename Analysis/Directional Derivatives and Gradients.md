# Directional Derivatives and Gradients
## Directional Derivatives
Definition of directional derivative:

Let $f$ be a function of two variables $x$ and $y$ and let $\mathbf{u}=\cos\theta\mathbf{i}+\sin\theta\mathbf{j}$ be a unit vector. Then the **directional derivative of $f$ in the direction of $\mathbf{u}$**, denoted by $D_uf(x,y)$, is

$$D_uf(x,y)=\lim_{t\to 0} {f(x+t\cos\theta,y+t\sin\theta)-f(x,y) \over t}$$

provided this limit exists.[^larson]

### Theorem
If $f$ is a differentiable function of $x$ and $y$, then the directional derivative of $f$ in the direction of the unit vector $\mathbf{u}=\cos\theta\mathbf{i}+\sin\theta\mathbf{j}$ is[^larson]

$$D_uf(x,y)=f_x(x,y)\cos\theta+f_y(x,y)\sin\theta$$

偏导数可以看作是方向导数的特例。

## Gradients
Definition of gradient of a function of two variables:

Let $z=f(x,y)$ be a function of $x$ and $y$ such that $f_x$ and $f_y$ exist. Then the **gradient of $f$**, denoted by $\nabla f(x,y)$, is the vector

$$\nabla f(x,y)=f_x(x,y)\mathbf{i}+f_y(x,y)\mathbf{j}$$

Another notation for the gradient is given by $\text{grad } f(x,y)$.[^larson]

### Alternative form of the directional derivative
If $f$ is differentiable function of $x$ and $y$, then the direcctional derivative of $f$ in the direction of the unit vector $\mathbf{u}$ is[^larson]

$$D_uf(x,y)=\nabla f(x,y)\cdot\mathbf{u}$$

### Properties of the gradients
Let $f$ be differentiable at the point $(x,y)$.
1. If $\nabla f(x,y)=\mathbf{0}$, then $D_u f(x,y)=0$ for all $\mathbf{u}$.
2. The direction of _maximum_ increase of $f$ is given by $\nabla f(x,y)$. The maximum value of $D_u f(x,y)$ is

  $$||\nabla f(x,y)||$$

3. The direction of _minimum_ increase of $f$ is given by $-\nabla f(x,y)$. The minimum value of $D_u f(x,y)$ is

  $$-||\nabla f(x,y)||$$
  

[^larson]: Calculus. Ron Larson, Bruce Edwards.