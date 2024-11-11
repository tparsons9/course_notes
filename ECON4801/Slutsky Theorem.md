  > [!theorem] Slutsky's Theorem
> Let $\{ X_{n} \}$ and $X$ be $m \times k$ random matrices. Let $\{ Y_{n} \}$ be $k \times k$ matrices. Let $A$ be a $k \times k$ (constant) matrix. Suppose that $X_{n} \xrightarrow{d} X$ and $Y_{n}\xrightarrow{p} A$. Then, 
> 1) $X_{n} + Y_{n}\xrightarrow{d} X + A$
> 2) $X_{n}Y_{n}\xrightarrow{d}XA$
> 3) $X_{n}Y_{n}^{-1}\xrightarrow{d} XA^{-1}$ provided that $A$ is invertible

`\begin{proof}`
	$(X, A)$ and each $(X_{n},Y_{n})$ are random elements of the metric space $\mathbb{R}^{m \times k}\times \mathbb{R}^{k \times k}$. $Y_{n}\xrightarrow{p} A$ implies that $Y_{n}\xrightarrow{d} A$ by [[Modes of Convergence#Relationships]]. The mappings $(x,y)\mapsto x+y$ and $(x,y)\mapsto xy$ are continuous and $(x,y)\mapsto xy^{-1}$ is continuous whenever $y$ is invertible. The result then follows from part $\hspace{0pt}3$ of [[Continuous Mapping Theorem]]. 
`\end{proof}`
# Motivation & Statement

Slutsky's theorem describes how different modes of convergence interact under basic operations, making it crucial for statistical inference.

## Properties

1. For [[Convergence in Distribution]]:

- If $X_n \xrightarrow{d} X$ and $Y_n \xrightarrow{p} c$ (constant), then:

* $X_n + Y_n \xrightarrow{d} X + c$

* $X_nY_n \xrightarrow{d} cX$

2. For [[Convergence in Probability]]:

- If $X_n \xrightarrow{p} X$ and $Y_n \xrightarrow{p} Y$, then:

* $X_n + Y_n \xrightarrow{p} X + Y$

* $X_nY_n \xrightarrow{p} XY$

3. For [[Almost Sure Convergence]]:

- Similar properties hold with stronger conclusions

## Remarks 
It is important that $Y$ converges to a constant rather than to a random matrix. When $X_{n}$ and $Y_{n}$ both converge to random elements $X$ and $Y$ it need not be that the result holds. For an example of violation of the theorem, see [[Weak Convergence of Marginals vs Joint]]. 
## Applications

- Constructing confidence intervals

- Analyzing transformed statistics

- Proving asymptotic properties of estimators

## References

- [[Modes of Convergence]]

- [[Statistical Inference]]