---
aliases: 
up: "[[Profit Maximization]]"
created: 2024-11-10
modified: 2024-11-10
tags:
  - microeconomics
  - Type/lemma
---


>[!lemma] Hotelling's Lemma
> If $y(\mathbf{\bar{p}})$ is a singleton, then $\pi$ is differentiable at $\mathbf{\bar{p}}$ and $\nabla_{p}\pi(\mathbf{\bar{p}})=y(\mathbf{\bar{p}})$

## Overview

### Motivation 
Hotelling's Lemma relates the supply of a good to the maximum profit of the producer. It says that, _the rate of increase in maximized profits with respect to a price increase is equal to the net supply of the good_. In words, if the firm makes its choices to maximize profits, then the choices can be recovered from the knowledge of the maximum profit function. 
### Related Concepts
- Direct consequence of the [[Duality Theorem]]
- In the view of this Lemma, [[Definiteness of the PMP]] is a consequence of the convexity of $\pi(\cdot)$. Quantities respond in the same direction as price changes. 
	- if the price of an output increases, then the supply of the output increases 
	- if the price of an input increases, then the demand for the input decreases. 
	- **Note:** Add to [[Production Hints & Tricks]]. 

### Proof Steps 
1) Apply [[Envelope Theorem]]
2) Step $\hspace{0pt}2$ 
3) Step 3

`\begin{proof}`
Given that $y(\mathbf{\bar{p}})$ is a singleton and that production is specified with a production function, let $z^{*}=y(\mathbf{\bar{p}})$, the optimal input vector. We can write the profit function as, 
$$
\pi(p, w) = \mathbf{\bar{p}}\cdot f(z^{*}) - w\cdot z^{*}
$$
Due to optimality, the [[PMP FOC]] gives us, using the [[Envelope Theorem]], 
$$
\frac{ \partial \pi }{ \partial z }\rvert_{z=z^{*}} = 0
$$
By taking the derivative of $p$ at $z^{*}$, 
$$
\frac{d\pi}{dp} = \frac{ \partial \pi }{ \partial z } \rvert_{z=z^{*}}\frac{ \partial z }{ \partial p } + \frac{ \partial \pi }{ \partial p } = \frac{ \partial \pi }{ \partial p } = f(z^{*})=y^{*}(p)
$$


`\end{proof}`

### Related Theorems:
- [[ ]] (Link to related theorems if applicable)



---

## Visual/Graphical Representation
- Sketch or Graph (Use Latex or attach an image if relevant): 

## Remarks
- Any other remarks or observations:
  
### Further Reading
- [[ ]] (Link to other notes or literature on the topic)

## References
- Source or textbook chapter: 


---

**Next Steps:**
- [[ ]] (Link to the next note in your study flow.)

