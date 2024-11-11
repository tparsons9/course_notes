# Motivation & Statement

  

In probability theory, there are several ways to characterize the convergence of random variables. Each mode of convergence has different strengths and relationships with other modes.

  

## Types of Convergence

  

### Almost Sure Convergence ($\xrightarrow{a.s.}$)

- Strongest form of convergence

- $X_n \xrightarrow{a.s.} X$ if $P(\{\omega: \lim_{n \to \infty} X_n(\omega) = X(\omega)\}) = 1$

- Also known as convergence with probability 1

  

### Convergence in Probability ($\xrightarrow{p}$)

- $X_n \xrightarrow{p} X$ if $\lim_{n \to \infty} P(|X_n - X| > \epsilon) = 0$ for all $\epsilon > 0$

- Connected to [[Stochastic Order Notation]] through $o_p(1)$

  

### Convergence in Distribution ($\xrightarrow{d}$)

- Weakest form of convergence

- $X_n \xrightarrow{d} X$ if $\lim_{n \to \infty} F_n(x) = F(x)$ at all continuity points of $F$

- Foundation for [[Central Limit Theorem]]

  

### $L^p$ Convergence

- $X_n \xrightarrow{L^p} X$ if $\lim_{n \to \infty} E[|X_n - X|^p] = 0$

- Special case: Mean Square Convergence ($p=2$)

  

## Relationships

  

1. Hierarchy of Convergence:

```

Almost Sure Convergence

↓

L^p Convergence (p ≥ 1)

↓

Convergence in Probability

↓

Convergence in Distribution

```

  

2. Implications:

- Almost Sure → Probability

- $L^p$ → Probability

- Probability → Distribution

- If $p > q$, then $L^p$ → $L^q$

  

3. Non-implications:

- Distribution ↛ Probability

- Probability ↛ Almost Sure

- Probability ↛ $L^p$

- $L^p$ ↛ Almost Sure

  

4. Special Cases:

- For bounded random variables: Probability ↔ $L^1$

- For discrete distributions: Distribution ↔ Probability

- For sequences of constants: All modes equivalent

  

## Comparison Table

  

| Property | Almost Sure | $L^p$ | Probability | Distribution |

|----------|-------------|-------|-------------|--------------|

| Pointwise | Yes | No | No | No |

| Preserves Moments | Yes | Yes | No | No |

| Continuous Maps | Yes | Yes | Yes | Yes |

| Products | Yes | Yes* | Yes | No |

| Subsequences | Yes | Yes | No | No |

  

*Under appropriate moment conditions

  

## Links and Relationships

- **Types**: [[Almost Sure Convergence]], [[Convergence in Probability]]

- **Examples**: [[Law of Large Numbers]], [[Central Limit Theorem]]

- **Specializations**: [[Stochastic Order Notation]]

- **Applications**: [[Statistical Inference]], [[Asymptotic Theory]]

  

## Applications

  

1. Consistency of Estimators

2. Asymptotic Normality

3. Law of Large Numbers

4. Empirical Processes

  

## Key Theorems

  

1. Completeness Theorem:

- Almost sure convergence implies convergence in probability

- Convergence in $L^p$ implies convergence in $L^q$ for $p > q$

- All modes of convergence are complete

  

2. Limiting Operations:

- All modes preserve limits under continuous transformations

- Only almost sure convergence preserves countable operations

  

## Extended Relationships

  

1. [[Uniform Integrability]]:

- Links convergence in $L^1$ and convergence in probability

- If {$X_n$} is uniformly integrable and $X_n \xrightarrow{p} X$, then $X_n \xrightarrow{L^1} X$

  

2. [[Dominated Convergence Theorem]]:

- If $X_n \xrightarrow{a.s.} X$ and $|X_n| \leq Y$ with $E[Y] < \infty$

- Then $X_n \xrightarrow{L^1} X$

  

3. [[Uniform Convergence]] vs. Almost Sure:

- Uniform convergence is stronger than pointwise

- Useful for function spaces and stochastic processes

  

## Examples

  

1. Sample Means:

- $\bar{X}_n \xrightarrow{a.s.} \mu$ (Strong LLN)

- $\bar{X}_n \xrightarrow{p} \mu$ (Weak LLN)

- $\sqrt{n}(\bar{X}_n - \mu) \xrightarrow{d} N(0,\sigma^2)$ (CLT)

  

2. Sample Variance:

- $s_n^2 \xrightarrow{p} \sigma^2$

- $s_n^2 \xrightarrow{a.s.} \sigma^2$ under fourth moment condition

  

## References

- [[Basic Probability Theory]]

- [[Asymptotic Theory]]

- [[Statistical Inference]]