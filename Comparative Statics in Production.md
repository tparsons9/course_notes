---
up: "[[Production MOC]]"
aliases: 
tags:
  - microeconomics
  - production_theory
---
## Overview 

> [!theorem] Comparative Statics in Production
> Assume that $f$ is twice differentiable, strictly concave production function of $L$ inputs and that $D_{z}f(z)\geq 0$ and $D_{z}f(z)\neq 0$ for all $z$, ie. that each input has non-negative marginal product and, at each $z$, at least one input has positive marginal product. Then, 
> 1) $q$ is increasing in $p$ 
> 2) Demand for some input increases due to an increase in output price 
> 3) An increase in $w_{i}$ leads to an increase in demand for $z_{i}$. 


## Collection of Proofs 

### Proofs for $q$ is increasing in $p$ 

#### Proof $\hspace{0pt}1$. 
`\begin{proof}`
By strict concavity and using the fact that in [[Profit Maximization#^40063c]] if $f$ is strictly concave then $Y$ is strictly convex and $y(\mathbf{p})$ is a singleton, this implies that the solution is unique. Let $\mathbf{p'}= \mathbf{p}+(\epsilon,0,\dots, 0)$. The [[Law of Supply]] says that $(\mathbf{p'}-\mathbf{p})\cdot(y(\mathbf{p'})-y(\mathbf{p}))\geq 0$, so $\epsilon \times (q(p', w) - q(p,w))\geq 0$. Then $\Delta q\equiv q(p', w) - q(p,w)$ is non-negative. We need to show that it is strictly positive. 

Let $z$ maximize profit at $p,w$. Suppose that price increases to $p+\epsilon$. Consider using inputs $z' = \alpha z$ and let $\pi(\alpha, p+\epsilon)$ be the profit from using inputs at $\alpha z$ at price $p+\epsilon$. 
$$
\pi(\alpha, p+\epsilon)=(p+\epsilon)f(\alpha z)-\alpha wz
$$
Now, at $\alpha=1$, the derivative equals, 
$$
\begin{align}
\pi'_{\alpha}(1, p+\epsilon ) & = (p+\epsilon)(D_{z}f(z))\cdot z - w\cdot z \\
 & = \epsilon(D_{z}f(z))z + z[p(D_{z}f(z))-w]
\end{align}
$$
From [[PMP FOC]] we know that $z[p(D_{z}f(z)) - w] = 0$. Further, $D_{z}f(z)\cdot z>0$ since when $z_{i}>0$, then $f_{i}= \frac{w}{p}>0$ and $z_{i}>0$ exists. So there exists an $\alpha>1$ such that $q' = f(\alpha z)>f(z)=q$ delivers higher profit, and together with the law of supply shows that output is increasing in price. 
`\end{proof}`

#### Proof $\hspace{0pt}2$, using FOC. 
`\begin{proof}`
First assume one input to see how the case works. The [[PMP FOC]] for one input states that $pf'(z(p))=w$. Taking the derivative wrt $p$ and assuming that $f$ is differentiable, then if we knew that $z$ is differentiable we would have $f'(z(p))+pf''(z(p))z'(p) = 0$, so $z'=-f' / (pf'')>0$ by strict concavity of $f$. 
`\end{proof}`
## Other Results 


> [!definition] Convexity of $\pi$ implies differential law of supply
> The convexity of $\pi$ implies the differential version of the law of supply; the discrete form is $(\mathbf{p'}-\mathbf{p''})\cdot(y(\mathbf{p'})-y(\mathbf{p''}))\geq 0$

`\begin{proof}`
Convexity of $\pi$ implies that the gradient lies above the tangent, that is, 
$$
\pi(\mathbf{p'})\geq \pi(\mathbf{p''})+ \nabla \pi(\mathbf{p''})(\mathbf{p'}-\mathbf{p''})
$$
Since $y(\mathbf{p'})$ and $y(\mathbf{p''})$ optimal at prices $\mathbf{p'},\ \mathbf{p''}$ respectively, we can write $\pi(\mathbf{p''})= \mathbf{p}''\cdot y(\mathbf{p''})$, and note that the gradient with respect to $p''$ becomes, $\nabla \pi(\mathbf{p''})= y(\mathbf{p''})$. Now, 
$$
\pi(\mathbf{p'})\geq \pi(\mathbf{p''}) + y(\mathbf{p''})(\mathbf{p'}-\mathbf{p''})
$$
Similarly, 
$$
\pi(\mathbf{p''})\geq \pi(\mathbf{p'})+ y(\mathbf{p'})(\mathbf{p''}-\mathbf{p'})
$$
Adding these two inequalities gives, 
$$
\begin{align}
\pi(\mathbf{p''})+ \pi(\mathbf{p'}) & \geq \pi(\mathbf{p'}) + y(\mathbf{p'})(\mathbf{p''}-\mathbf{p'}) + \pi(\mathbf{p''})+y(\mathbf{p''})(\mathbf{p'}-\mathbf{p''}) \\
\pi(\mathbf{p''})+\pi(\mathbf{p'}) -\pi(\mathbf{p''})-\pi(\mathbf{p'}) & \geq \mathbf{p''}y(\mathbf{p'})-\mathbf{p' }y(\mathbf{p'}) + \mathbf{p'}y(\mathbf{p'})-\mathbf{p''}y(\mathbf{p''}) \\
0 & \geq \mathbf{p''}y(\mathbf{p'})-\mathbf{p' }y(\mathbf{p'}) + \mathbf{p'}y(\mathbf{p'})-\mathbf{p''}y(\mathbf{p''}) \ \\
\mathbf{p'}y(\mathbf{p'}) + \mathbf{p''}y(\mathbf{p''})-\mathbf{p'}y(\mathbf{p''})-\mathbf{p''}y(\mathbf{p'}) & \geq 0 \\
\implies (\mathbf{p'}-\mathbf{p''})\cdot(y(\mathbf{p'})-y(\mathbf{p''})) & \geq 0
\end{align}
$$
Hence, concavity of $\pi$ implies the differential law of supply. 

`\end{proof}`

>[!remark] Law of supply holds even when $y(\mathbf{p})$ is not single valued. 


