  

# Motivation & Statement

  

Mean square convergence is a special case of $L^p$ convergence when $p=2$. It's particularly useful in statistical theory due to its connection with variance and second moments.

  

## Definition

  

A sequence of random variables {$X_n$} converges in mean square to $X$ if:

  

$$\lim_{n \to \infty} E[(X_n - X)^2] = 0$$

  

Notation: $X_n \xrightarrow{L^2} X$ or $X_n \xrightarrow{m.s.} X$

  

## Properties

  

1. Relationship with moments:

- $E[(X_n - X)^2] = E[X_n^2] - 2E[X_nX] + E[X^2]$

- Implies convergence of second moments

  

2. Sufficient conditions:

- If $E[X_n^2]$ is uniformly bounded and $X_n \xrightarrow{p} X$

- Then $X_n \xrightarrow{L^2} X$

  

3. Preservation under linear operations:

- If $X_n \xrightarrow{L^2} X$ and $Y_n \xrightarrow{L^2} Y$, then:

* $aX_n + bY_n \xrightarrow{L^2} aX + bY$ for constants $a,b$

  

## Additional Properties

  

1. Cauchy Criterion:

- $X_n \xrightarrow{L^2} X$ iff $\lim_{m,n \to \infty} E[(X_n - X_m)^2] = 0$

- See [[Cauchy Sequences]] for general theory

  

2. Connection to Covariance:

- If $X_n \xrightarrow{L^2} X$, then:

* $\text{Cov}(X_n, Y) \to \text{Cov}(X, Y)$ for any $Y$ with finite variance

- See [[Covariance Properties]] for details

  

3. [[Isometry Property]]:

- $L^2$ space forms a Hilbert space

- Inner product given by $E[XY]$

  

## Links and Relationships

- **Types**: [[Modes of Convergence]], [[L^p Convergence]]

- **Examples**: [[Sample Mean Convergence]]

- **Implies**: [[Convergence in Probability]]

- **Applications**: [[Statistical Inference]], [[Estimation Theory]]

  

## Applications

  

1. Projection Theory

2. Best Linear Unbiased Estimation

3. Least Squares Estimation

4. Time Series Analysis

  

## References

- [[Probability Theory]]

- [[Statistical Inference]]