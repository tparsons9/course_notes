---
aliases: 
up: "[[Cost Minimization]]"
created: 2024-11-09
modified: 2024-11-09
tags:
  - microeconomics
  - Type/definition
---
P

>[!definition] $c(w, q)$ First-Order Conditions
>Assuming differentiability, the first-order conditions for the cost minimization problem are: 
> $$
> w_{l}\geq \lambda \frac{ \partial f(z^{*}) }{ \partial z_{l} } 
>$$
>with equality if $z_{l}>0$. 

##### In Matrix Notation: 
$w\geq \lambda \nabla f(z^{*})$ and $(w - \lambda \nabla f(z^{*}))\cdot z^{*} = 0$

## Overview

### Motivation 
The FOC relates the price of an input $l$ to it's [[Marginal Productivity]], MP, $f_{l}$. Since $\lambda$ is the value of relaxing the constraint, it equals the marginal cost of producing another unit. The FOC is to equate (modulus corner solutions) the value of the of the MP to the price of the output. 

### Interpretation
- $\lambda$ represents the marginal cost of production
- The ratio of input prices equals the ratio of marginal products
- Corner solutions occur when the marginal product is too low relative to price

### Mathematical Details
1. **Lagrangian Setup:**
   $$\mathcal{L}(z,\lambda) = w\cdot z - \lambda(f(z)-q)$$

2. **First Order Conditions:**
   $$\frac{\partial \mathcal{L}}{\partial z_l} = w_l - \lambda\frac{\partial f}{\partial z_l} = 0$$
   $$\frac{\partial \mathcal{L}}{\partial \lambda} = f(z) - q = 0$$

### Properties
1. **Uniqueness:** Under strict quasi-concavity of $f$, FOCs yield unique solution
2. **Sufficiency:** FOCs are sufficient under appropriate concavity conditions
3. **Economic Meaning:** Input prices proportional to marginal products

### Examples
1. **Cobb-Douglas Production:**
   - $f(z_1,z_2) = z_1^\alpha z_2^\beta$
   - FOCs: $w_1 = \lambda\alpha\frac{y}{z_1}$, $w_2 = \lambda\beta\frac{y}{z_2}$

2. **Linear Production:**
   - $f(z_1,z_2) = az_1 + bz_2$
   - FOCs lead to corner solutions unless $\frac{w_1}{a} = \frac{w_2}{b}$

### Related Concepts
[[Lagrangian]], [[Envelope Theorem]], [[First Order Conditons]]




---

## Visual/Graphical Representation

![[Pasted image 20241109170236.png]]


## Remarks

>[!remark] 
> $w\geq \lambda \nabla f(z^{*})$ and $(w - \lambda \nabla f(z^{*}))\cdot z^{*}=0$ implies that for any pair of used inputs, the price ratio equals the [[Marginal Rate of Technological Substitution]] between the inputs, $\text{MRTS}_{lk}$, which is the slope of the [[Isoquants]], 
> $$
> \frac{f_{l}(z^{*})}{f_{k}(z^{*})} = \frac{w_{l}}{w_{k}}
>$$

The above is to be expected, since it implies that for any two inputs $l$ and $k$ with $(z_{l}, z_{k})\gg 0$ we have $\text{MRTS}_{lk} = \frac{w_{l}}{w_k}$ 
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

