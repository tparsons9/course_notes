

> [!theorem] Cramér-Wold Device
> Let $\{ X_{n} \}$ and $X$ be random $k-$vectors. Then $X_{n}\xrightarrow{d}X$ if and only if $\lambda^{T}X_{n}\xrightarrow{d} \lambda^{T}X$ for every $\lambda \in \mathbb{R}^{k}$

`\begin{proof}`
	Let $\{ X_{n} \},\ X$ be random k-vectors. Suppose that $X_{n}\xrightarrow{d} X$ and fix $\lambda \in \mathbb{R}^{k}$. Note that $x\mapsto \lambda^{T}x$ is a continuous mapping, so by the [[Continuous Mapping Theorem]], we get $\lambda^{T}X_{n}\xrightarrow{d} \lambda^{T}X$. 
	$(\impliedby)$. Suppose that $\lambda^{T}X_{n}\xrightarrow{d}\lambda^{T}X,\ \forall \lambda \in \mathbb{R}^{k}$. By [[Levy's Continuity Theorem]], this implies that $\phi_{\lambda^{T}X_{n}}(1)\to \phi_{\lambda^{T}X}(1)$, ie., 
	$$
	\mathbf{E}[\exp(i\lambda^{T}X_{n})]\to\mathbf{E}[\exp(i\lambda^{T}X)], \quad \forall \lambda \in  \mathbb{R}^{k}
	$$
	But the LHS equals $\phi_{X_{n}}(\lambda)$, and the RHS equals $\phi_{X}(\lambda)$. So we've shown that $\phi_{X_{n}}\to\phi_{X}$ pointwise, which implies $X_{n}\xrightarrow{d}X$ by Levy's Continuity Theorem. 
`\end{proof}`


**Proved By::** [[Characteristic Functions]] of linear combinations, [[Levy's Continuity Theorem]], [[Continuous Mapping Theorem]]. 


## Specializations
1. Multivariate [[Lindeberg-Lévy CLT]]:
   - Shows convergence to multivariate normal via univariate projections
   - Proves $\frac{1}{\sqrt{n}}\sum_{i=1}^n X_i \xrightarrow{d} N(0, \Sigma)$

2. Testing Multivariate Normality:
   - Allows verification through univariate projections
   - Connection to [[Portmanteau Theorem]] for vectors

## Generalizations
1. Abstract Spaces:
   - Extensions to locally convex spaces
   - Generalizations to infinite-dimensional settings

## Remarks
The power of this device lies in reducing multivariate convergence problems to univariate ones, which are typically easier to verify. This is particularly useful in proving multivariate versions of limit theorems.

## Example
Consider proving that a bivariate random vector converges to a standard normal:
$X_n = (X_{n1}, X_{n2}) \xrightarrow{d} N(0, I_2)$. By Cramér-Wold, it suffices to show that $\lambda_1 X_{n1} + \lambda_2 X_{n2} \xrightarrow{d} N(0, \|\lambda\|^2)$ for all $\lambda \in \mathbb{R}^2$.

