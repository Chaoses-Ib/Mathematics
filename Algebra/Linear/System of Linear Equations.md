# System of Linear Equations
## Solving a linear system
### Elimination of variables

### Row reduction (Gaussian elimination)

### Cramer's rule
$$\mathbf{A} \mathbf{x}=\mathbf{b}$$

对于二阶线性方程组， $\mathbf{x}$ 与一个基向量 $i$ 构成的平行四边形的面积为 $\mathbf{x}$ 在另一基向量 $j$ 上的投影，记为 $y$。经过 $\mathbf{A}$ 的线性变换后，这一平行四边形的面积变为 $\det(\mathbf{A})\cdot y$。如果我们能够用 $\mathbf{A}$ 和 $\mathbf{b}$ 表示出变换后的平行四边形的面积，将它除以 $\det(\mathbf{A})$ 即可得到 $y$。实际上，变换后的平行四边形是由 $\mathbf{b}$ 与变换后的 $i$ 构成的，它的面积可以表示为 $\det(\mathbf{A} \xrightarrow{j} \mathbf{b})$，其中 $\mathbf{A} \xrightarrow{j} \mathbf{b}$ 表示将 $\mathbf{A}$ 中的 $j$ 列替换为 $\mathbf{b}$。于是我们可以得到

$$y={\det(\mathbf{A} \xrightarrow{j} \mathbf{b}) \over \det(\mathbf{A})} \quad (\det(\mathbf{A})\ne 0)$$

这一结论可以推广到所有维度。[^cramer-3blue1brown]

### Matrix solution
$$\mathbf{A} \mathbf{x}=\mathbf{b}$$

将 $\mathbf{A}$ 看作对 $\mathbf{x}$ 的线性变换，求出线性变换的逆 $\mathbf{A}^{-1}$，并对 $\mathbf{b}$ 施加该变换，即

$$\mathbf{x}=\mathbf{A}^{-1}\mathbf{b}$$


[^cramer-3blue1brown]: [Cramer's rule, explained geometrically | Chapter 12, Essence of linear algebra - YouTube](https://www.youtube.com/watch?v=jBsC34PxzoM&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=12)