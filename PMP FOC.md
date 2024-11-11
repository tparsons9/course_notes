---
aliases: 
up: "[[Profit Maximization]]"
created: 2024-11-10
modified: 2024-11-10
tags:
  - microeconomics
  - Type/definition
---


>[!definition] First-Order Conditions for $\pi$
>Given a production $f$, the FOC is that, in addition to the cost-minimization FOC, we have $p-c_{q}(w, q^{*})\leq 0$ and $=$ if $q^{*}>0$. That is, if the firm produces, then price equals marginal cost. 
>Given a transformation function $F$, the FOC are that $\mathbf{p}=\lambda \nabla F(y^{*})$, $i$.$e$. $\mathbf{p}_{l}=\lambda F_{l}$ for all $l$. 



## Overview

### Motivation 
This says that the price vector $\mathbf{p}$ and the gradient $\nabla F(y^{*})$ are proportional. 
### Related Concepts
- [[Duality Theory]]: [[CMP FOC]] related to PMP FOC. 
- [[Transformation Functions]]
- [[Marginal Cost]]

### Alternative characterizations: 

When $Y$ corresponds to a single-output technology with differentiable production function $f(z)$, we can view the firm's decision as simply a choice over it's input levels $z$. In this case, we let the scalar $p>0$ denote the price of the firm's output and the vector $w\gg 0$ denote the input prices. The input vector $z^{*}$ maximizes profit given $(p,w)$ if it solves, 
$$
\max_{z\geq 0}pf(z) - w\cdot z
$$
If $z^{*}$ is optimal, then the First-order condition for this PMP is, 
$$
p\cdot \frac{ \partial f(z^{*}) }{ \partial z_{l} } \leq w_{l}
$$
Or in matrix notation: 
$$
p\nabla f(z^{*})\leq w\quad \text{ and }\quad (p\nabla f(z^{*})-w)\cdot z^{*}=0
$$
Thus, the [[Marginal Productivity]] of every input $l$ actually used (ie. with $z_{l}^{*}>0$) must equal it's price in terms out output, $w_{l} / p$. Note that for any two inputs $l$ and $k$ with $(z_{l}^{*}, z_{k}^{*})\gg 0$, this implies that $\text{MRTS}_{lk} = w_{l} / w_{k}$, or, the [[Marginal Rate of Technological Substitution]] between the two inputs is equal to their price ratio. 

If the production set $Y$ is convex, then the first-order conditions are not only necessary, but also sufficient for the determination of a solution to the PMP. 




---

## Visual/Graphical Representation

![[Pasted image 20241110161718.png]]
## Remarks

>[!tip]+ Relationship with [[Marginal Rate of Transformation]]
>The PMP FOC yields the following ratio inequality: 
> $$
> \frac{\mathbf{p}_{l}}{\mathbf{p}_{k}} = \lambda \frac{ \partial F(y^{*}) }{ \partial y_{l} } / \lambda \frac{ \partial F(y^{*}) }{ \partial y_{k} } = \frac{ \partial F(y^{*}) / \partial y_{l} }{ \partial F(y^{*}) / \partial y_{k} } = \text{MRT}_{lk}(y^{*})
>$$
>For $n=2$, this says that the slope of the transformation frontier at the profit-maximizing production plan must be equal to the negative of the price ratio. 
  
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

