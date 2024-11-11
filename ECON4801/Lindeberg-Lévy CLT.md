---
up: "[[Central Limit Theorem]]"
---

# Motivation 

The Lindeberg-Lévy Central Limit Theorem is a foundational result in probability theory that establishes conditions under which the sum of independent and identically distributed random variables converges to a normal distribution. It serves as the most basic form of the [[Central Limit Theorem]] and provides the theoretical basis for many statistical procedures.

> [!theorem] Lindeberg-Lévy
> Let $\{ X_{n} \}$ be a sequence of iid random variables with $\mathbf{E}[X_{1}] = 0$ and $\text{Var}(X_{1}) = 1$. Then $n^{-1/2}\sum_{i=1}^{n}X_{i}\overset{d}{\to}\mathcal{N}(0,1)$

`\begin{proof}`
	We'll show that the characteristic function of $n^{-1/2}\sum_{i=1}^{n}X_{i}$ converges pointwise to $\varphi_{\mathcal{N}(0,1)}(t) = \exp\left( -\frac{1}{2}t^{2} \right)$ and then appeal to [[Levy's Continuity Theorem]]. First, write, 
	$$
	Z_{n} = n^{-1/2}\sum_{i=1}^{n}X_{i}
	$$
	Fix an arbitrary $t \in \mathbb{R}$. Then, 
	$$
	\begin{align}
	\varphi_{Z_{n}}(t) & = \mathbf{E}\left[ \exp \left( itn^{-1/2}\sum_{j=1}^{n}X_{j} \right)  \right]  \\
	 & = \mathbf{E}\left[ \prod_{j=1}^{n}\exp(itn^{-1/2}X_{j}) 
	 \right]  \\
	 & = \prod_{j=1}^{n}\mathbf{E}[\exp(itn^{-1/2}X_{j} )] \\
	 & = E[\exp(itn^{-1/2}X_{1})]^{n} \\
	 & = \varphi_{X_{1}}(t / n^{1/2})^{n}
	\end{align}
	$$
	Where we used independence in the third equality and identical distribution in the fourth. Since $t / n^{1/2}\to 0$, only the behavior of $\varphi_{X}$ in a shrinking neighborhood of $\hspace{0pt}0$ will matter. Formally, we use the [[Taylor Expansion]] around $\hspace{0pt}0$ to approximate $\varphi_{X_{1}}(t / n^{1/2})$ as $n$ grows large: 
	$$
	\varphi_{X_{1}}(t / n^{1/2}) = \varphi_{X_{1}}(0) + \varphi'_{X_{1}}(0) \frac{t}{n^{1/2}} + \frac{1}{2}\varphi_{X_{1}}'' (0) \frac{t^{2}}{n} + o(1 / n)
	$$
	where the derivatives exist since $\mathbf{E}[X_{1}]$ and $\mathbf{E}[X_{1}^{2}]$ exist and are finite (see [[Characteristic Functions#Properties]]). Then, $\varphi_{X_{1}}(0) = 1,\ \varphi_{X_{1}}'(0) = i^{-1}\mathbf{E}[X_{1}]=0$ and $\mathbf{E}[X_{1}^{2}] = i^{-2}\text{Var}(X_{1}) = i^{-2} = -1$. We can write the Taylor Expansion as, 
	$$
	\varphi_{X_{1}}(t / n^{1/2}) = 1 - \frac{1}{2}t^{2} / n + o(1 / n)
	$$
	So using the fact that $\lim_{ n \to \infty }(1+x / n)^{n} = \exp(x)$, we get: 
	$$
	\begin{align}
	\varphi_{Z_{n}}(t)  & = \varphi_{X_{1}}(t / n^{1/2})^{n}  \\
	 & = \left( 1 - \frac{1}{2}t^{2} / n + o(1 / n) \right)^{n} \\
	 & \to \exp\left( -\frac{1}{2}t^{2} \right) \\
	 & = \varphi_{\mathcal{N}(0,1)}(t)
	\end{align}
	$$
	Hence, $Z_{n}\xrightarrow{d}\mathcal{N}(0,1)$ by [[Levy's Continuity Theorem]]. 
`\end{proof}`
## Properties

1. Scaling Property:
   - For general iid $\{X_n\}$ with mean $\mu$ and variance $\sigma^2$:
   - $\frac{\sum_{i=1}^n (X_i - \mu)}{\sigma\sqrt{n}} \overset{d}{\to} \mathcal{N}(0,1)$

2. Proof Approach:
   - Uses [[Characteristic Functions]]
   - Relies on the fact that $\phi_{X_n}(t) \to e^{-t^2/2}$
   - Applies [[Lévy's Continuity Theorem]]

3. Relationship to [[Stochastic Order Notation]]:
   - $\bar{X}_n - \mu = O_p(n^{-1/2})$
   - Connects to [[Connections Between CLTs and LLNs]]

## Applications

1. Statistical Inference:
   - Construction of confidence intervals
   - Hypothesis testing
   - Maximum likelihood theory

2. Sample Mean Properties:
   - Asymptotic normality
   - Efficiency considerations
   - [[Convergence in Distribution]] properties

## Remarks 

Setting $\mathbf{E}[X_{1}] = 0$ and $\text{Var}(X_{1}) = 1$ is wlog, since for $\mathbf{E}[X_{n}] = \mu$ and $\text{Var}(X_{n}) = \sigma^{2}$, we can apply the theorem to $Y_{n}:= \frac{X_{n} - \mu}{\sigma}$. The importance of these restrictions is that the mean exists and is finite and that the variance is finite and nonzero. 


## Example
Let $\{ X_{n} \}$ be iid with $X_{n}\sim \mathcal{N}(0,1)$, and define $S_{n}:= \sum_{i=1}^{n}X_{i}^{2}$. In this case, we don't really need to approximate the distribution of $S_{n}$ because we know that it is a $\chi^{2}(n)$. But the Lindeberg-Lévy CLT still applies. 

Compute $\mathbf{E}(Z_{n}^{2}) = 1,\ \text{Var}(Z_{n}^{2}) = \mathbf{E}[Z_{n}^{4}] - \mathbf{E}[Z_{n}^{2}]^{2} = 3 - 1 = 2$, where we use the fact that the fourth moment of the Standard [[Normal Distribution]] is equal to $\hspace{0pt}3$. Hence, by the Lindeberg-Lévy CLT, 
$$
(2n)^{-1/2}(S_{n} - n) = n^{-1/2}\sum_{i=1}^{n} \frac{X_{i}^{2} - 1}{\sqrt{ 2 }}\xrightarrow{d} \mathcal{N}(0,1)
$$
and $S_{n} \overset{a}{\sim}\mathcal{N}(n, 2n).$ 
## Links and Relationships
- **Theory**: [[Characteristic Functions]], [[Convergence in Distribution]]
- **Related**: [[Slutsky Theorem]], [[Portmanteau Theorem]]
- **Applications**: [[Statistical Inference]], [[Asymptotic Theory]]

## References
- [[Modes of Convergence]]
- [[Probability Theory]]
- [[Statistical Inference]]

