---
aliases: 
up: "[[Production Exercises]]"
created: 2024-11-10
modified: 2024-11-10
tags: [microeconomics, Type/exercise]
---
---



>[!exercise] Finite data about the firm
> a) You are given a finite set of input demands and input prices for a firm $\{ (x_{i}, w_{i}): i = 1,\dots, n \}$ where $x_{i},\ w_{i}\in \mathbb{R}^{n}_{+}$. Complete the following theorem: 
>> The following are equivalent: 
> 	> i) There exists a continuous, concave, monotonic production function $f$ that rationalizes the data
> 	> ii) The following relationship must hold among the $x_{i}\cdot w_{j}:\dots$
> 	> iii) There exist $q_{i},\ \lambda_{i}$ all positive that satisfy the following inequalities: $\dots$
> 	
> b) Prove that $a.i.$ implies $a.iii.$ What interpretation of $\lambda_{i}$ does this proof suggest? 
> c) You are now given, in addition, the output data, $y_{i}$. Assume that $y_{1}<y_{2}<\dots<y_{n}$. This additional data enables you to deduce that if $a.i.$ holds then additional relationships among $x_{i}\cdot w_{j}$ must hold. Describe and briefly explain these additional restrictions. _Hint:_ Remember that the firm is profit maximizing so whatever it does at each data point must be the best it can do
> d) You are now given in addition, finally, the price data for the output, $p_{i}$
>> i) Describe an inequality involving $p_{i}, y_{i}, x_{i}, w_{i}, x_{j}, y_{j}$ (for any arbitrary pair $i$ and $j$) that must hold if these $\hspace{0pt}6$ pieces of data (four from one observation, two from another) came from profit maximization. _Hint:_ Forget about the ordering, ie. whether $y_{i}$ or $y_{j}$ is larger. If you understand profit maximization then finding this inequality should be straightforward. 
> 	> ii) Rewrite the inequality in $d.i.$ with $y_{j}$ isolated on one side of the inequality and compare to the inequality in $a.iii.$ Use this to rewrite the inequalities in $a.i i i.$ suitably replacing the $q_{i}'s$ and the $\lambda_{i}$'s. What plays the role of $q_{i}$ and $\lambda_{i}$? 
> 	> iii) Prove that the rewritten $a.i i i$ as in $d.ii$ implies $a.i$. That is, construct the production function from the data and show that profit maximization with this constructed production function is consistent with the data (ie. that it generates, or rationalizes, the data). 
> 	

## Proof Steps 

a)
$(i)$ **Existence of Production function f** 
- **Continuous:** No sudden jumps; small changes in inputs lead to small changes in output 
- **Concave:** Reflects [[Diminishing Marginal Returns]], combining inputs doesn't produce disproportionately more output 
- **Monotonic**: More inputs does not produce less output; output non-decreasing in inputs - precludes corner solutions 
For $(ii),\ (iii)$ notice the connection to [[Afriat Inequalities]]. If we let $x^{*}(w,q)$ be the conditional factor demands, and let $x \in x^{*}(w,q)$. As $x$ is the cost-minimizing level of an input, we have for any other $x'\in \mathbb{R}^{n}_{+}$ that $x\succ x'$ if $w\cdot x'>w\cdot x$. This is true because if $w\cdot x'\leq w\cdot x$, then this would contradict $x$ minimizing the cost. Taking the analog from the proposition in [[Afriat Inequalities]], we have for $(aii)$ that, $\forall k,\ k' \in \{ 1,\dots,n \}$ if $x_{k}\succeq^{IR}x_{k'}$, then $\neg(x_{k'}\succ^{R}x_{k})$. 

For $a.i i i$, this is a direct consequence of [[Afriat Inequalities]], since we have continuous, monotonic, and concave $f$, and it should read, 
$$
q_{i}\leq q_{j} + \lambda_{j}w_{j}(x_{i}-x_{j})
$$
`\begin{proof}`
$(a.ii)$
Notice the connection in the problem to [[Afriat Inequalities]]. If we let $x^{*}(w,q)$ be the conditional factor demands, then if $x \in x^{*}(w,q)$, for any other $x' \in \mathbb{R}^{n}_{+}$ such that $x\succ x'$, then $w\cdot x'>w\cdot x$. If this were not the case, this would contradict $x$ being a cost-minimizer. Taking the analog of Definition $\hspace{0pt}2.17$., $a.ii$ should state, $\forall k, k' \in \{ 1,\dots,n \}$ if $x_{k}\succcurlyeq^{IR}x_{k'}$ then not $\neg(x_{k'}\succ^{R}x_{k})$. 
For $(a. i i i)$ notice that, given monotonic (in-place of LNS), concave and continuous $f$ that rationalizes the data, and from $(a.i i)$ the finite data satisfies [[Generalized Axiom of Revealed Preference]], then the Afriat inequalities follow directly. That is, 
$$
q_{i}\leq q_{j} + \lambda_{j}w_{j}(x_{i}-x_{j})
$$
where $q_{()}$ plays the role of utility levels and $w_{()}$ plays the role of consumption prices. 
`\end{proof}`

#### Part b) 

`\begin{proof}`
$(a.i)\implies(a.i i i)$. We will use the concavity of $f$. By the properties of concave functions, assuming differentiability, $f$ being concave and differentiable implies that it is bounded above by it's first order Taylor approximation: 
$$
f(x)\leq f(x') + \nabla f(x')(x - x')
$$
From the profit maximization FOC, we know that for, 
$$
\pi(p,w) = \max_{x} pf(x) - w\cdot z
$$
the first-order conditions are, 
$$
\frac{ \partial L }{ \partial x } \equiv p\nabla f(x) - w = 0 \implies \nabla f(x) = \frac{w}{p}
$$
Letting $f(x_{i}) = q_{i}$ and $\lambda_{i} = \frac{1}{p_{i}}$, we can write the original equation as, 
$$
\begin{align}
f(x_{i}) & \leq f(x_{j}) + \lambda_{j}w_{j}(x_{i}-x_{j})
\end{align}
$$
and hence $a.i i i$ holds. From Proposition $\hspace{0pt}3.3$. we know that if the firm produces, then price equals marginal costs. Therefore, $\lambda_{i}$ in the profit maximization problem is the inverse, ie. $\frac{1}{\text{MC}}. = \frac{1}{p}$. 
`\end{proof}`

#### Part c) 
`\begin{proof}`
$y_{1}<y_{2}<\dots<y_{n}$ for output data where each firm is profit maximizing, implies that $w_{1}\cdot x_{1}<w_{1}\cdot x_{2}<\dots<w_{1}\cdot x_{n}$, $w_{2}\cdot x_{2}<w_{2}\cdot x_{3}<\dots<w_{2}\cdot x_{n}$, and so on. If it were not so, then under input prices $w_{1}$, you could produce $w_{1}\cdot x_{2} = y_{1}'>y_{1} = w_{1}\cdot x_{1}$, contradicting optimality of conditional factor demand, $x_{1}$ under $w_{1}$. 
`\end{proof}`

#### Part d) 
`\begin{proof}`
$(c.i)$ At prices $(p_{i}, w_{i})$ we are given that the profit maximizing plan is $(y_{i}, x_{i})$. Then, for all pairs $(i,j)$ we know that, 
$$
\begin{align}
p_{i}y_{j} - w_{i}x_{j}  & \leq p_{i}y_{i} - w_{i}x_{i} \\
y_{j} & \leq y_{i} + \frac{1}{p_{i}} w_{i}(x_{j} - x_{i})
\end{align}
$$
Compared to $(a.i i i)$, we have $q_{i}$ represented by $y_{i}$ and $\lambda_{i}$ represented by $1 / p_{i}$. 

For $(iii)$, note that this is again similar to the proof for Proposition $\hspace{0pt}2.34$. Write, 
$$
f(x) = \min_{1\leq i\leq n} y_{i} + \frac{1}{p_{i}}w_{i}(x - x_{i})
$$
Since this is the lower envelope of linear functions and is therefore concave, we have established one of the requirements. Given the data, $y_{1}<y_{2}<\dots<y_{n}$, as long as we can show that $f$ rationalizes the data, then $f(x_{i}) = y_{i}$ and the ordering would imply that $f$ is (strictly) monotonically increasing. Continuity follows from differentiability. To show that $f$ rationalizes the data, we need to show two parts. First, note that at $x = x_{i}$, we have, 
$$
f(x_{i}) = y_{i} + \frac{1}{p_{i}}w_{i}(x_{i} - x_{i}) = y_{i}
$$
That $\arg\min_{i}\left\{  y_{i} + \frac{1}{p_{i}}w_{i}(y_{k}-y_{i})  \right\} = k$ follows from the fact that $y_{k}+ \frac{1}{p_{k}}w_{k}(y_{k}-y_{k})=y_{k}\leq y_{l}+ \frac{1}{p_{l}}w_{l}(y_{k}-y_{l})$ for all $l$ by the inequality. Now, choose any $x$ in $\mathbb{R}^{n}_{+}$ such that $f(x)p_{k} - w_{k}x\geq f(x_{k})p_{k} - w_{k}x_{k}$. Rewriting in terms of the previous argument produces, 
$$
\begin{align}
f(x)p_{k}-w_{k}x\geq f(x_{k})p_{k}-w_{k}x_{k} \\
\implies f(x) \geq y_{k} + \frac{1}{p_{k}} w_{k}(x-x_{k})
\end{align}
$$
But $f(x) = \min_{k} y_{k} + \frac{1}{p_{k}}w_{k}(x-x_{k})$ so we must have that $f(x)\leq y_{k}+ \frac{1}{p_{k}}w_{k}(x-x_{k})$ for all $k$. Combining these two inequalities implies that $f(x)p_{k} - w_{k}x  = y_{k}p_{k}-w_{k}x_{k}$. This bares the resemblance of the profit maximizing function $\pi(p,w) = pf(z) - w\cdot z$. So at prices $(p_{k},w_{k})$, $x_{k}\in\arg\max \{  p_{k}f(x) - w_{k}\cdot x\}$. Hence $f$ rationalizes the data. 
`\end{proof}`

## Overview

### Motivation 

### Related Concepts
[[ ]] (Use this to link to related concepts like Supply, Demand, Utility, etc.)



---

## Visual/Graphical Representation
- Sketch or Graph (Use Latex or attach an image if relevant): 

## Remarks
- Any other remarks or observations:
  
### Further Reading
- [[ ]] (Link to other notes or literature on the topic)

## References
- ECON410$\hspace{0pt}-1$ Problem $\hspace{0pt}3.2$ $\hspace{0pt}2009$ Final 


---

**Next Steps:**
- [[ ]] (Link to the next note in your study flow.)

