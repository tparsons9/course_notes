---
up: "[[Production MOC]]"
created: 2024-11-09
modified: 2024-11-09
tags:
  - microeconomics
  - Type/Definition
---
## 1. Overview

### Motivation 

To analyze the behavior of the firm, we need to start by identifying the production vectors that are technologically possible. Any $y \in Y$ is possible while any $y \not\in Y$ is not. 

### Related Concepts
- [[Transformation Functions]]
- [[Marginal Rate of Technological Substitution]]
- [[Isoquants]]
- [[Properties of Production Sets]]
- [[Returns to Scale]]


## 2. Definition

>[!definition] Production Function
> A production **function** $f: \mathbb{R}^{n}_{+}\to\mathbb{R}$ to be interpreted as the quantity of a single output, denoted $q$, that is created by a non-negative vector of inputs, denoted $z$. 
> 
> A production **set** is denoted by $Y\subseteq \mathbb{R}^{m}$. It is interpreted as all the _net_ bundles that can result from production. Given a vector $y \in \mathbb{R}^{m}$ if $y_{i}<0$ then a negative quantity of $i$ is produced at that vector (ie, good $i$ is an input). Conversely, if $y_{i}>0$ then good $i$ is an output. 

> [!example] 
> Suppose that $n = 5$. Then $y = (-5, 2, -6, 3, 0)$ means that $\hspace{0pt}2$ and $\hspace{0pt}3$ units of goods $\hspace{0pt}2$ and $\hspace{0pt}4$ are produced, while $\hspace{0pt}5$ and $\hspace{0pt}6$ units of goods $\hspace{0pt}1$ and $\hspace{0pt}3$ are used. Good $\hspace{0pt}5$ is neither produced nor used as an input in the production vector. 



---

## 3. Visual/Graphical Representation

![[Pasted image 20241109111537.png]]
The netput set $Y$ is the LHS of the graph. The production function $f$ is the dashed function on the RHS. The area _on and under_ the solid line (that continues down to $(0, -\infty)$) on the LHS is the set $Y$ 

## 4. Additional Notes
#### Transformation Functions 
Given a production set $Y$ we can define [[Transformation Functions]] that satisfy $F(y)\leq 0$ iff $y \in Y$ and $F(y) = 0$ iff $y$ is on the boundary of $Y$. For instance, with single-good production, for $y = (-z, q)$, it is natural to define $F(y) = q - f(z)$, which is non-positive iff $q\leq f(z)$ (ie. $q$ is feasible given $z$) and the boundary is then $F(y) = 0$ so the boundary is equivalent to the production function $q = f(z)$ in the figure above. 

See [[Transformation Functions]] for more properties and relations. 

#### Production Sets vs Production Functions

Production sets are more general than production functions. Given a production function $f$ we can define $Y = \{ (-z, q): q\leq f(z) \}$ to be the set of feasible input-output vectors. When dealing with production functions, we may refer to the set $Y$ to be understood as coming from this definition. $Y$ is more general: $Y$ may allow for two outputs, it allows for both inputs and outputs, it specifies explicitly that there is [[Free Disposal]] and more technically, it may be open so that we can produce as close as we want to some $q = f(z)$ but not reach the boundary. 
  
### Further Reading
- [[ ]] (Link to other notes or literature on the topic)

## 5. References
- Source or textbook chapter: [[MWG]] Chapter $\hspace{0pt}5$, [[Production.pdf]]

---

**Next Steps:**
- [[ ]] (Link to the next note in your study flow.)

