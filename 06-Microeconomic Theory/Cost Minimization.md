---
aliases: 
up: "[[Production MOC]]"
created: 2024-11-09
modified: 2024-11-09
tags: [microeconomics, Type/definition]
---


>[!definition] Cost Minimization Problem
>Let $w \in \mathbb{R}^{n}_{+}$ be the price vector of inputs, $z$. Let $f$ be the associated production function, $q$ be the output. The cost minimization problem is, 
> $$
>c(w,q) = \min_{z\geq 0} w\cdot z\text{ s.t. } f(z)\geq q
>$$

## Overview

### Motivation 

An important implication of the firm choosing a [[Profit Maximization]] production plan is that there is no way to produce the same amounts of outputs at a lower total input cost. Thus, cost minimization is a **_necessary_** condition for profit maximization. 

The cost minimization problem leads us to a number of results and constructions that are useful. When the production set exhibits [[Non-decreasing Returns to Scale|NRDTS]] the value function and optimizing vectors of the cost minimization problem, which keeps the levels of outputs fixed, are better behaved than the profit function and supply correspondence of the PMP. 

### Related Concepts
- [[Expenditure Function]]: All properties that were proved for $e$ and $h$ holds for $c$ and $z$. The equivalence to [[Compensated Demand]] follows since there are no wealth effects. 

### Examples:
- Example: [[ ]] (Link to an example if available)
- Example: Insert example within the file 
- Table for items with tag example and up points to this file 



---

## Visual/Graphical Representation
![[Pasted image 20241109170236.png]]


## Remarks

>[!remark] Conditional Factor Demands
>The solution to the CMP is called the conditional factor demands, and is represented by $z(w, q)$


## Properties 

> [!proposition] Properties of $c(w, q)$
> 1) (Assuming suitable differentiability...) FOC: $w_{l}\geq \lambda \frac{ \partial f(z^{*}) }{ \partial z_{l} }$, with equality if $z_{l}^{*}>0$; ie. $w\geq \lambda \nabla f(z^{*}),$ and $(w - \lambda \nabla f(z^{*}))\cdot z^{*} = 0$. This implies that for any pair of used inputs the price ratio equals the MRTS between the inputs, $MRTS_{lk}$, which is the slope of the isoquant; ie. $\frac{f_{l}(z^{*})}{f_{k}(z^{*})} = \frac{w_{l}}{w_{k}}$
> 2) If $f$ is (strictly) quasiconcave, so that the upper contour set $\{ z\geq 0: f(z)\geq q \}$ is (strictly) convex, then $z$ is a (singleton) convex set
> 3) $c$ is $H$.$\hspace{0pt}1$. in $w$ and increasing in $q$ 
> 4) $z$ is $H$.$\hspace{0pt}0$. in w
> 5) $c$ is concave in $w$ 
> 6) If $z(\bar{w},q)$ is a singleton then $c$ is differentiable in $w$ at $(\bar{w}, q)$ and $\nabla_{w}c(\bar{w}, q) = z(\bar{w}, q)$
> 7) If $z$ differentiable at $\bar{w}$ then $D_{w}z(\bar{w}, q) = D^{2}_{w}c(\bar{w}, q)$ is symmetric negative semidefinite with $D_{w}z(\bar{w}, q)\cdot \bar{w} = 0$
> 8) If $f$ is $H$.$\hspace{0pt}1$. (equivalently CRTS) then $c$ and $z$ are $H$.$\hspace{0pt}1$. in $q$. 
> 

### Standalone Properties 

- [[CMP FOC]]: First-order conditions 
- [[Homogeneity and Monotonicity Properties of CMP]]
- [[Homogeneity of Conditional Factor Demands]]
- [[Concavity of CMP]]

### Conjunctive Properties 
- [[Convexity of Conditional Factor Demands]]
- [[Shephard's Lemma]]
- [[Definiteness of the CMP]]
- [[CRTS & Homogeneity of CMP]]
- [[Convexity of the CMP]]

### Relation Table 


| Given                           | Relation                 | Property                                                                          |
| ------------------------------- | ------------------------ | --------------------------------------------------------------------------------- |
| FOC                             | $\implies$               | MRTS equals price ratio                                                           |
| $f$ (strictly) $q$.concave      | $\implies$               | $z$ is (singleton) convex set                                                     |
| $z(\bar{w}, q)$ singleton       | $\implies$               | $c$ is differentiable in $w$ at $(\bar{w}, q)$                                    |
| $z$ differentiable at $\bar{w}$ | $\implies$               | $D_{w}z = D^{2}_{w}c$ is symmetric NSD with $D_{w}z \cdot  \bar{w} = 0$           |
| $f$ (strictly) concave          | $\implies$<br>$\implies$ | $c$ (strictly) convex in $q$ <br>marginal costs (increasing) nondecreasing in $q$ |
|                                 |                          |                                                                                   |

### Further Reading
- [[ ]] (Link to other notes or literature on the topic)

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

