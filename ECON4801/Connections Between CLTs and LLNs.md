
## CLTs and Weak LLNs

Whenever a [[Central Limit Theorem]]-type property holds for some scaling constants $\{ a_{n} \}$ that don't shrink too fast, a [[Weak Law of Large Numbers]] follows. 

Note however that WLLN $\centernot\implies$ CLT. Further, we cannot strengthen the result to obtain a [[Strong Law of Large Numbers]]. 

## Example 

Suppose that random variables $\{ X_{n} \}$ satisfy a CLT for some constants $\{ a_{n} \},\ \{ b_{n} \}$: 
$$
a_{n} \sum_{i=1}^{n}(X_{i} - b_{i})\xrightarrow{d}\mathcal{N}(0,1)
$$
(For concreteness, you can think of $a_{n}= n^{-1/2}, \ b_{n} = \mathbf{E}[X_{n}]$)
Then, 
$$
n^{-1}\sum_{i=1}^{n}(X_{i}-b_{i}) = O_{p}\left( \frac{1}{na_{n}} \right)
$$
The [[Stochastic Order Notation]] here holds because the statement $a_{n} S_{n}\xrightarrow{d}\mathcal{N}(0,1)$ implies that the sequence $\{ a_{n}S_{n} \}$ is **tight** in probabilistic terms. Then $a_{n}S_{n}$ is [[Bounded in Probability]], denoted as, 
$$
a_{n}S_{n} = O_{p}(1)
$$
Dividing by $a_{n}$ and multiplying both sides by $n^{-1}$, we have, 
$$
n^{-1}S_{n}\equiv n^{-1}\sum_{i=1}^{n}(X_{i}-b_{i}) = O_{p}\left( \frac{1}{na_{n}} \right)
$$
ie, $S_{n}$ is bounded in probability by $\frac{1}{na_{n}}$. In other words, for any $\epsilon>0$, there exists a constant $M$ and $n_{0}$ such that for all $n\geq n_{0}$, 
$$
P\left( \left\lvert  \frac{1}{n}\sum_{i=1}^{n}(X_{i}-b_{i})  \right\rvert > M \cdot \frac{1}{na_{n}} \right)< \epsilon 
$$
Now, if $\frac{1}{na_{n}} = o_{p}(1)$, it follows that $\{ X_{n} \}$ satisfy a weak law of large numbers, 
$$
n^{-1}\sum_{i=1}^{n}(X_{i} - b_{i}) = O_{p}(o_{p}(1)) = o_{p}(1)
$$
Then $n^{-1}\sum_{i=1}^{n}(X_{i}-b_{i})\xrightarrow{p} 0$ satisfying [[Chebychev's WLLN]] 

In particular, the implication holds if $a_{n} = n^{-1/2}$ as in the [[Lindeberg-Lévy CLT]]. 

### WLLN $\centernot \implies$ CLT 
The converse is false: a CLT does not follow from a WLLN property. 
For example, consider $\{ X_{n} \}$ and $X$ with $X = X_{n} = 0$. Then $X_{n}\xrightarrow{a.s.}X$ and we know from [[Modes of Convergence#Relationships]] that we then have $X_{n}\xrightarrow{p}X$, but $a_{n}\sum_{i=1}^{n}X_{i} = 0$ a.s. for _any_ sequence of constants $\{ a_{n} \}$. So we cannot obtain a CLT-type result no matter how we choose our scaling constants. 

### CLT $\centernot \implies$ SLLN
We cannot extend this result to strong LLN's. 