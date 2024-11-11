# Motivation & Statement

  

The Portmanteau theorem provides equivalent conditions for [[Convergence in Distribution]], making it a fundamental tool in asymptotic theory.

  

## Definition

  

For sequences of random variables {$X_n$} and $X$, the following statements are equivalent:

  

1. $X_n \xrightarrow{d} X$

2. $\lim_{n \to \infty} E[f(X_n)] = E[f(X)]$ for all bounded, continuous $f$

3. $\limsup_{n \to \infty} P(X_n \in F) \leq P(X \in F)$ for all closed sets $F$

4. $\liminf_{n \to \infty} P(X_n \in G) \geq P(X \in G)$ for all open sets $G$

5. $\lim_{n \to \infty} P(X_n \in A) = P(X \in A)$ for all $A$ with $P(X \in \partial A) = 0$

  

## Applications

- Proving [[Central Limit Theorem]]

- Verifying [[Convergence in Distribution]]

- Bootstrap theory

  

## References

- [[Modes of Convergence]]

- [[Statistical Inference]]