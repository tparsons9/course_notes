# Motivation & Statement

In probability theory and statistics, stochastic order notation helps us describe the asymptotic behavior of random sequences. These notations are analogous to the deterministic big-O notation but account for the probabilistic nature of random variables.
## Types of Convergence
### $O_p$ (Big-O in Probability)

For sequences of random variables {$X_n$} and deterministic sequences {$a_n$}, we write:
$X_n = O_p(a_n)$ if for every $\epsilon > 0$, there exists $M_\epsilon > 0$ and $N_\epsilon$ such that:

$$P(|X_n/a_n| > M_\epsilon) < \epsilon \text{ for all } n > N_\epsilon$$

This means the sequence $X_n/a_n$ is [[Bounded in Probability]].  

### $o_p$ (Little-o in Probability)

  

We write $X_n = o_p(a_n)$ if:
$$X_n/a_n \xrightarrow{p} 0$$
This indicates that $X_n/a_n$ has [[Convergence in Probability]] to zero.



## Properties

  

1. If $X_n = O_p(a_n)$ and $Y_n = O_p(b_n)$, then:

- $X_n + Y_n = O_p(\max(a_n, b_n))$

- $X_nY_n = O_p(a_nb_n)$

  

2. If $X_n = o_p(a_n)$ and $Y_n = O_p(b_n)$, then:

- $X_nY_n = o_p(a_nb_n)$

- $X_n + Y_n = O_p(\max(a_n, b_n))$

  

### Special Cases

  

1. $O_p(1)$ notation:

- $X_n = O_p(1)$ means the sequence $\{X_n\}$ is [[Bounded in Probability]]

- This implies the sequence is "tight" or "stochastically bounded"

- Example: Sample means of i.i.d. variables with finite variance are $O_p(1/\sqrt{n})$

  

2. $o_p(1)$ notation:

- $X_n = o_p(1)$ means $X_n \xrightarrow{p} 0$

- This is equivalent to [[Convergence in Probability]] to zero

- Stronger than $O_p(1)$ as it implies the sequence converges to zero

  

3. Relationships:

- If $X_n = o_p(1)$, then $X_n = O_p(1)$, but not vice versa

- If $X_n = O_p(1)$ and $Y_n = o_p(1)$, then $X_nY_n = o_p(1)$

- If $X_n \xrightarrow{p} c$ for some constant $c$, then $X_n = O_p(1)$

  

## Links and Relationships

- **Types**: [[Convergence in Probability]], [[Bounded in Probability]]

- **Examples**: [[Central Limit Theorem]], [[Law of Large Numbers]]

- **Generalizations**: [[Modes of Convergence]]

- **Applications**: [[Asymptotic Theory]], [[Statistical Inference]]

  

## Remarks

  

The stochastic order notation is particularly useful in:

- Deriving asymptotic distributions

- Proving consistency of estimators

- Analyzing rates of convergence in probability

- Establishing limiting behavior of statistical procedures

  

## Applications

  

Common applications include:

1. Establishing consistency of estimators

2. Deriving asymptotic distributions

3. Analyzing efficiency of statistical procedures

4. Proving convergence rates in probability theory

  

### Example: Central Limit Theorem and Order Notation

  

Consider the [[Central Limit Theorem]] for i.i.d. random variables $X_1, X_2, ..., X_n$ with mean $\mu$ and variance $\sigma^2$. Let $\bar{X}_n$ be the sample mean. We can express the CLT using stochastic order notation:

  

1. First, we know that $\sqrt{n}(\bar{X}_n - \mu) \xrightarrow{d} N(0,\sigma^2)$
2. This implies:

- $\bar{X}_n - \mu = O_p(1/\sqrt{n})$

- $\bar{X}_n = \mu + O_p(1/\sqrt{n})$

3. For any consistent estimator $\hat{\sigma}^2$ of $\sigma^2$:

- $\hat{\sigma}^2 - \sigma^2 = o_p(1)$

- $\sqrt{n}(\bar{X}_n - \mu)/\hat{\sigma} \xrightarrow{d} N(0,1)$

  

This notation helps us quickly understand the rate of convergence ($1/\sqrt{n}$) and construct confidence intervals.

  

## References

- [[Asymptotic Theory]]

- [[Probability Theory]]

- [[Statistical Inference]]

`\begin{proof}`

test
 Use top [[Levy's Continuity Theorem#^a1e133]] 
`\end{proof}`

