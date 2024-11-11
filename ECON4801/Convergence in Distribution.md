  

# Motivation & Statement

  

Convergence in distribution (weak convergence) is the weakest form of convergence but is fundamental for limit theorems and asymptotic theory.

  

## Definition

  

A sequence of random variables {$X_n$} converges in distribution to $X$ if:

  

$$\lim_{n \to \infty} F_{X_n}(x) = F_X(x)$$

  

at all continuity points of $F_X$, where $F_{X_n}$ and $F_X$ are the cumulative distribution functions.

  

Notation: $X_n \xrightarrow{d} X$

  

## Properties

  

1. Equivalent formulations: See [[Portmanteau Theorem]] for complete characterization

  

2. Continuous Mapping Theorem:

- If $X_n \xrightarrow{d} X$ and $g$ is continuous, then $g(X_n) \xrightarrow{d} g(X)$

  

3. See [[Slutsky's Theorem]] for operations with converging sequences

  

4. Key Properties:

- Does not imply convergence of moments

- Convergence is preserved under continuous mappings

- Uniquely determined by characteristic functions

  

## Additional Characterizations

  

1. [[Cramér-Wold Device]]:

- For random vectors, convergence in all linear combinations implies convergence in distribution

- Essential tool for multivariate analysis

  

2. [[Characteristic Functions]]:

- $X_n \xrightarrow{d} X$ iff $\phi_{X_n}(t) \to \phi_X(t)$ for all $t$

- Where $\phi_X(t) = E[e^{itX}]$

  

3. [[Skorokhod Representation]]:

- For convergence in distribution, there exist random variables with the same distributions converging almost surely

- Important for proving limit theorems

  

## Links and Relationships

- **Types**: [[Modes of Convergence]]

- **Examples**: [[Central Limit Theorem]]

- **Implied by**: [[Convergence in Probability]]

- **Applications**: [[Statistical Inference]], [[Asymptotic Theory]]

  

## Applications

  

1. Central Limit Theorem

2. Asymptotic Distributions of Test Statistics

3. Bootstrap Theory

4. Method of Moments

  

## References

- [[Basic Probability Theory]]

- [[Statistical Inference]]