---
up: "[[Exponential Distribution]]"
aliases: 
tags:
  - econometrics
  - example
---
## $\exp(\alpha)$ ML Estimator 

The exponential distribution with parameter $\alpha>0$ is any distribution on $(\mathbb{R}, \mathcal{B})$ whose density $w$.$r$.$t$. the Lebesgue Measure is $f(x) = \alpha\exp(-\alpha x).$ The mean and variance of this distribution is $\alpha^{-1}$ and $\alpha^{-2}$ respectively. 

Suppose we have $n$ iid random variables $\{ X_{n} \}$ drawn from the $\exp(\alpha)$ distribution, and we wish to estimate $\alpha$. The obvious analogy estimator, which turns out to also be the maximum likelihood estimator, is 
$$
\hat{\alpha}_{n}:= \left( n^{-1}\sum_{i=1}^{n}X_{i} \right) ^{-1}
$$
By [[Kolmogorov's Second SLLN]], we have, 
$$
n^{-1}\sum_{i=1}^{n}X_{i}\xrightarrow{a.s.}\mathbf{E}[X_{i}] = \alpha ^{-1}
$$
so by the [[Continuous Mapping Theorem]], $\hat{\alpha}_{n}\xrightarrow{a.s.}\alpha$, ie. the estimator is strongly consistent. So $\hat{\alpha}_{n}$ will be 'close' to $\alpha$ in a large sample. 

But how close? We need to approximate the distribution of $\hat{\alpha}_{n}$ in a large sample. The [[Lindeberg-Lévy CLT]] gives us, 
$$
n^{-1/2}\sum_{i=1}^{n} \frac{X_{i}-\alpha ^{-1}}{\sqrt{ \alpha^{-2} }}\xrightarrow{d} \mathcal{N}(0,1)
$$
which we can rewrite as, 
$$
n^{1/2}\alpha(\hat{\alpha}_{n}^{-1} - \alpha ^{-1})\xrightarrow{d} \mathcal{N}(0,1)
$$
Now, using the [[Delta Method]] with $g(x) = 1 / x$ (so that $g'(x) = -1 / x^{2}$), $a_{n} = n^{1/2}\alpha$ and $b = \alpha^{-1}$ to obtain, 
$$
n^{1/2}\alpha(\hat{\alpha}_{n} - \alpha)\xrightarrow{d}(-1 / \alpha^{-2})\mathcal{N}(0,1)
$$
or equivalently, 
$$
n^{1/2}(\hat{\alpha}_{n} - \alpha)\xrightarrow{d} \mathcal{N}(0, \alpha^{2})
$$
So, for $n$ large, the distribution of $\hat{\alpha}_{n}$ is well approximated by $\mathcal{N}(\alpha, n^{-1}\alpha^{2})$. 
