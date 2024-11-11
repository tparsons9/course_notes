---
aliases: 
up: "[[Profit Maximization]]"
created: 2024-11-10
modified: 2024-11-10
tags:
  - microeconomics
  - Type/exercise
---


>[!exercise] $Y$ NDRTS $\implies$ $\pi(\mathbf{p})\leq 0$ or $\pi(\mathbf{p})=+\infty$
>Prove that, in general, if the production set $Y$ exhibits nondecreasing returns to scale, then either $\pi(\mathbf{p}) \leq 0$ or $\pi(\mathbf{p})=+\infty$. 

`\begin{proof}`
We will consider two exhaustive cases. 

Case 1) All production plans yield non-positive profit
Suppose that, $\forall y \in Y$, the profit it nonpositive: $p\cdot y\leq 0$. Then clearly, $\pi(\mathbf{p}) = max_{y\in Y}\mathbf{p}\cdot y\leq 0$. 

Case 2) There exists a production plan yielding positive profit
Let $y_{0}\in Y$ such that $\mathbf{p}\cdot y_{0}>0$. We will show that under [[Non-decreasing Returns to Scale]] this leads to infinite profit. Since $Y$ exhibits non-decreasing returns to scale, for any $\alpha\geq 1$, the scaled production plan, $\alpha y_{0} \in Y$. The profit from producing $\alpha y_{0}$ is $\mathbf{p}\cdot(\alpha y_{0})=\alpha(\mathbf{p}\cdot y_{0})$. Since $\mathbf{p}\cdot y_{0}>0$, scaling by $\alpha\geq 1$ (which can be arbitrarily large) scales the profit proportionally. 
Taking the limit as $\alpha\to \infty$ gives us, 
$$
\lim_{ \alpha \to \infty } \alpha(\mathbf{p}\cdot y_{0})=+\infty
$$
Therefore the profit function is unbounded above and hence, $\pi(\mathbf{p})=+\infty$. 
`\end{proof}`


---
## Implications 
- [[Non-decreasing Returns to Scale|NDRTS]]: 
	- Producing more does not diminish efficiency
	- Scaling up production is not met with proportionally higher costs or diminishing outputs 
- [[Profit Maximization]]
	- If any production plan yields positive profit, the firm can exploit non-decreasing returns to scale to increase profit without bound 
	- If no production plan yields positive profit, the firm cannot improve it's position by scaling production 


## References
- MWG Exercise 5.$C$.$\hspace{0pt}1$. 


---

**Next Steps:**
- [[ ]] (Link to the next note in your study flow.)

