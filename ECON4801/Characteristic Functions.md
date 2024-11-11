  

# Motivation & Statement

  

Characteristic functions provide a powerful tool for studying distributions and their convergence. They are particularly useful because they always exist (unlike moments) and uniquely determine distributions.

  

## Definition

  

For a random variable $X$, its characteristic function $\phi_X(t)$ is defined as:

  

$$\phi_X(t) = E[e^{itX}] = \int_{-\infty}^{\infty} e^{itx} dF_X(x)$$

  

where $t \in \mathbb{R}$ and $i$ is the imaginary unit.

  

## Properties

  

1. Basic Properties:

- $|\phi_X(t)| \leq 1$ for all $t$

- $\phi_X(0) = 1$

- $\phi_X(-t) = \overline{\phi_X(t)}$ (complex conjugate)

- Continuous for all $t$

  

2. Linear Transformations:

- For $Y = aX + b$: $\phi_Y(t) = e^{itb}\phi_X(at)$

- For independent $X,Y$: $\phi_{X+Y}(t) = \phi_X(t)\phi_Y(t)$

  

3. [[Connection to Moments]]:

- If $E[|X|^n] < \infty$, then $\phi_X^{(n)}(0) = i^n E[X^n]$

- All moments can be recovered from derivatives at $t=0$

  

## Convergence Properties

  

1. [[Lévy's Continuity Theorem]]:

- $X_n \xrightarrow{d} X$ iff $\phi_{X_n}(t) \to \phi_X(t)$ for all $t$

- Fundamental tool for proving convergence in distribution

  

2. [[Uniqueness Theorem]]:

- If $\phi_X(t) = \phi_Y(t)$ for all $t$, then $X$ and $Y$ have the same distribution

- Essential for proving distributional equality

  

## Common Examples

  

1. Normal Distribution:

- If $X \sim N(\mu, \sigma^2)$: $\phi_X(t) = e^{i\mu t - \sigma^2t^2/2}$

  

2. Poisson Distribution:

- If $X \sim Poisson(\lambda)$: $\phi_X(t) = e^{\lambda(e^{it}-1)}$

  

3. Uniform Distribution:

- If $X \sim U[a,b]$: $\phi_X(t) = \frac{e^{itb}-e^{ita}}{it(b-a)}$

  

## Applications

  

1. [[Central Limit Theorem]] Proof:

- Uses characteristic functions to show convergence

- Leverages their multiplicative property for sums

  

2. [[Stable Distributions]]:

- Characterized through their characteristic functions

- Important in limit theory and financial modeling

  

3. [[Mixture Distributions]]:

- Easily handled through weighted sums of characteristic functions

  

## Links and Relationships

- **Theory**: [[Fourier Analysis]], [[Probability Theory]]

- **Applications**: [[Convergence in Distribution]], [[Moment Generation]]

- **Examples**: [[Normal Distribution]], [[Stable Distributions]]

  

## References

- [[Probability Theory]]

- [[Statistical Inference]]

- [[Asymptotic Theory]]