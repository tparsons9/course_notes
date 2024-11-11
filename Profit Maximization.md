---
up: "[[Production MOC]]"
created: 2024-11-10
modified: 2024-11-10
tags:
  - microeconomics
---


>[!definition] Profit Maximization Problem
>Let the price of the output be $p$. Then the vector of output-input prices denoted by $\mathbf{p} = (p,w)$. The profit function is, 
> $$
>\begin{align}
> \pi(p, w)  & = \max_{y \in  Y}\mathbf{p}\cdot y \\
>  & = \max_{q,z} pq - w\cdot z \text{ s.t. } q\leq f(z) \\ 
> & = \max_{z} pf(z) - w\cdot z \\
> & = \max_{q}pq - c(w,q)
\end{align}
>$$
>where the last three versions apply if we have a production function specification, and not only a production set. Denote the solutions by $(q(p, w), -z(p, w)) = y(\mathbf{p})$. 



#Type/definition
## Overview

### Motivation 

### Related Concepts

>[!tip]+ PMP equivalent to [[Utility Maximization]] Problem with quasilinear $u$ 
> $u(x) = v(x_{-1})+x_{1}$, since then by substituting the budget constraint, utility-maximization becomes $\max_{\hat{x}}\hat{v}(\hat{x}) - \hat{p}\cdot \hat{x}$, where $\hat{x} = x_{-1}$, $\hat{p}= p_{-1} / p_{1}, \hat{v}(\cdot) = v(\cdot) + 1 / p_{1}$. 
> This is because when utility is quasi-linear in good $j$, there are no wealth effects for other goods, ie. $x_{i}(p,w)$ does not depend on $w$ for all $i\neq j$. 


### Examples:
- Example: [[ ]] (Link to an example if available)
- Example: Insert example within the file 
- Table for items with tag example and up points to this file 



---

## Visual/Graphical Representation
![[Pasted image 20241110161718.png]]


## Properties 

> [!proposition] PMP Properties
> 1) FOC (Under suitable differentiability assumptions ...) Given a production function $f$, the FOC is that , in addition to the cost-minimization FOC, we have $p - c_{q}(w,q^{*})\leq 0$, and = if $q^{*}>0$. That is, if the firm produces, then price equals marginal cost. Given a transformation function $F$, the FOC are that $\mathbf{p} = \lambda \nabla F(y^{*})$, ie. $\mathbf{p}_{l}=\lambda F_{l}$ for all $l$. 
> 2) $\pi(\mathbf{p}) = \pi(p,w)$ is homogeneous degree $\hspace{0pt}1$; $y(\mathbf{p}) = (q(p,w), z(p,w))$ is $H$.$\hspace{0pt}0$. 
> 3) $\pi$ is **convex**
> 4) If $f$ is (strictly) concave, ie. $Y$ (strictly) convex, then $y(\mathbf{p})$ is a (singleton) convex set
> 5) If $y(\mathbf{\bar{p}})$ is a singleton then $\pi$ is differentiable at $\mathbf{\bar{p}}$ and $\nabla_{p}\pi(\mathbf{\bar{p}})=y(\mathbf{\bar{p}})$
> 6) If $y(\mathbf{\bar{p}})$ is differentiable at $\mathbf{\bar{p}}$, then $D_{p}y(\mathbf{\bar{p}})=D_{p^{2}}^{2}\pi(\mathbf{\bar{p}})$ is symmetric and **positive** semi-definite matrix with $D_{p^{2}}^{2}\pi(\mathbf{\bar{p}})\mathbf{\bar{p}} =0$

^40063c

**Property Files:** [[PMP FOC]], [[Homogeneity of Profit Maximization]], [[Convexity of Profit Function]], [[Definiteness of the PMP]], [[Hotelling's Lemma]] 
## Remarks
- The firm's _supply correspondence_ at $p$ is given by $y(\mathbf{p})$ 
	- It's the set of profit-maximizing vectors $y(\mathbf{p}) = \{ y \in Y: \mathbf{p}\cdot y = \pi(\mathbf{p}) \}$. In the figure above, $y(\mathbf{p})$ lies on the _iso-profit line_, along which all points generate equal profits. 

- In general, $y(\mathbf{p})$ may be a set rather than a single-vector. 
- Possible for no profit-maximizing production plan to exist: for example, if profits have no upper bound, $\pi(\mathbf{p})=+\infty$. 
  
### Further Reading
- See [[Comparative Statics in Production]] 


## Relationships 
- [[NRDTS implications for PMP]]
- 
## References
- Source or textbook chapter: 

```dataviewjs

const currentPage = dv.current().file.name.replace(/\.md$/, '');

// Initialize an array to hold pages that reference the current page within proofs
let referencingPages = [];

// Function to escape special regex characters in the page name
function escapeRegExp(string) {
    return string.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
}

// Create a regex pattern to match [[Current Page]] links
const linkPattern = new RegExp(`\\[\\[${escapeRegExp(currentPage)}\\]\\]`, 'g');

// Iterate over all Markdown files in the vault
for (let file of dv.pages().file) { // You can adjust the source if needed
    // Skip the current file
    if (file.path === dv.current().file.path) continue;

    // Get the raw content of the file
    let content = await dv.io.load(file.path);

    // Use a regex to find all proof environments
    const proofRegex = /\\begin\{proof\}([\s\S]*?)\\end\{proof\}/g;
    let match;

    // Search for the link within each proof environment
    while ((match = proofRegex.exec(content)) !== null) {
        let proofContent = match[1];
        if (linkPattern.test(proofContent)) {
            referencingPages.push(file.link);
            break; // Stop after finding the first reference in this file
        }
    }
}

// Display the results
if (referencingPages.length > 0) {
    dv.header(3, "Used to Prove");
    dv.list(referencingPages);
} else {
    dv.header(3, "Used to Prove");
    dv.paragraph("No references found within proofs.");
}
```

```dataviewjs
const currentPage = dv.current().file.name.replace(/\.md$/, '');

// Initialize an array to hold pages that reference the current page
let examplePages = [];

// Function to escape special regex characters in the page name
function escapeRegExp(string) {
    return string.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
}

// Create a regex pattern to match [[Current Page]] links
const linkPattern = new RegExp(`\\[\\[${escapeRegExp(currentPage)}\\]\\]`, 'g');

// Get all pages with #example tag
const exampleFiles = dv.pages('#example').file;

// Iterate over tagged files
for (let file of exampleFiles) {
    // Skip the current file
    if (file.path === dv.current().file.path) continue;

    // Get the raw content of the file
    let content = await dv.io.load(file.path);

    // Check if the current page is referenced
    if (linkPattern.test(content)) {
        examplePages.push(file.link);
    }
}

// Display the results
if (examplePages.length > 0) {
    dv.header(3, "Referenced in Examples");
    dv.list(examplePages);
} else {
    dv.header(3, "Referenced in Examples");
    dv.paragraph("No references found in example pages.");
}
```


---

**Next Steps:**
- [[ ]] (Link to the next note in your study flow.)

