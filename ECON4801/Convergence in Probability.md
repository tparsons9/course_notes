  

# Motivation & Statement

  

Convergence in probability is weaker than almost sure convergence but stronger than convergence in distribution. It's particularly useful in statistical inference.

  

## Definition

  

A sequence of random variables {$X_n$} converges in probability to $X$ if:

  

$$\lim_{n \to \infty} P(|X_n - X| > \epsilon) = 0 \text{ for all } \epsilon > 0$$

  

Notation: $X_n \xrightarrow{p} X$

  

## Properties

  

1. Equivalent formulation:

- $X_n \xrightarrow{p} X$ iff $\forall \epsilon > 0$, $\lim_{n \to \infty} P(|X_n - X| \leq \epsilon) = 1$

  

2. Operations with converging sequences: See [[Slutsky's Theorem]]

  

3. Key Properties:

- Preserved under continuous transformations

- Implies [[Convergence in Distribution]]

- Does not generally preserve moment convergence

  

## Additional Properties

  

1. Subsequence Characterization:

- $X_n \xrightarrow{p} X$ iff every subsequence has a further subsequence converging a.s. to X

- See [[Subsequence Principle]] for details

  

2. [[Markov's Inequality]] Application:

- For non-negative $X_n$: $P(X_n \geq a) \leq E[X_n]/a$

- Useful for proving convergence in probability

  

3. Connection to [[Stochastic Order Notation]]:

- $X_n \xrightarrow{p} X$ iff $X_n - X = o_p(1)$

- Provides alternative way to express convergence

  

## Links and Relationships

- **Types**: [[Modes of Convergence]]

- **Examples**: [[Weak Law of Large Numbers]]

- **Implied by**: [[Almost Sure Convergence]], [[Mean Square Convergence]]

- **Implies**: [[Convergence in Distribution]]

  

## Applications

  

1. Weak Law of Large Numbers

2. Consistency of Estimators

3. [[Stochastic Order Notation]] ($o_p$ and $O_p$)

  

## References

- [[Probability Theory]]

- [[Statistical Inference]]