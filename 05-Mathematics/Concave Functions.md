---
up: "[[Analysis MOC]]"
aliases: 
tags:
  - mathematics
---
> [!definition] Concave Functions
> A real-valued function on a convex set in a vector space is said to be **concave** if, for any $x$ and $y$ in the set, and for any $\alpha \in[0,1]$, 
> $$
>f(\alpha x + (1-\alpha)y) \geq \alpha f(x) + (1-\alpha)f(y)
>$$
> Strictly concave if $(>)$. 

Note that $f$ is has [[Quasiconcavity]] if the upper contour sets of the function $S(\alpha) = \{ x: f(x)\geq \alpha \}$ are convex sets. 

[![](https://upload.wikimedia.org/wikipedia/commons/7/73/ConcaveDef.png)](https://en.wikipedia.org/wiki/File:ConcaveDef.png)
## Properties 

> [!theorem] Derivative of Concave $f$ has nonincreasing slope
> A differentiable function $f$ is (strictly) concave on an interval if and only if it's derivative function $f'$ is (strictly) monotonically decreasing on that interval. That is, a concave function has non-increasing (decreasing) slope

> [!theorem] Properties of twice differentiable concave functions
> If $f$ is twice-differentiable, then $f$ is concave if and only if $f''$ is non-positive. If $f''$ is negative then $f$ is strictly concave, but the reverse is not true. 

> [!theorem] Concave $f$ lies below tangent Hyperplane
> If $f$ is concave and differentiable, then it is bounded above by it's first-order [[Taylor Expansion]]: 
> $$
> f(y)\leq f(x) + \nabla f(x)(y-x)
>$$

