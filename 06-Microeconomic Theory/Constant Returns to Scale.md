---
aliases:
  - CRTS
up: "[[Returns to Scale]]"
created: 2024-11-09
modified: 2024-11-09
tags:
  - microeconomics
  - Type/property
---


>[!assumption] CRTS
> 1) The production function is homogeneous of degree 1: $f(\alpha x) = \alpha f(x)$
> 2) Any feasible production can be proportionally changed: $y \in Y$ implies that $\alpha y \in Y$ for all $\alpha\geq 0$. 


## Overview

### Motivation 
CRTS is essential for understanding how firms can adjust production levels in response to changes in market conditions without experiencing gains or losses in production efficiency.

### Related Concepts
- [[Efficiency in Production]]: The production process under CRTS maintains **constant efficiency** regardless of the scale of operation
- CRTS is the conjunction of [[Non-increasing Returns to Scale|NIRTS]] and [[Non-decreasing Returns to Scale]]

## Implications 
- **Proportional Scaling**: Doubling all inputs (ie. $\alpha = 2$) exactly doubles the inputs 
- **Scalability**: Firms can **scale up** or **scale down** proportionally without encountering feasibility issues 



---

## Visual/Graphical Representation

![[Pasted image 20241109143618.png]]
![[Pasted image 20241109144604.png]]
## Remarks
- Example: 
	- If a factory uses $\hspace{0pt}10$ units of labor and $\hspace{0pt}5$ units of capital to produce $\hspace{0pt}100$ inputs of output, under CRTS, using $\hspace{0pt}20$ units of labor and $\hspace{0pt}10$ units of capital will produce $2 \times 100 = 200$ units of output. 
- Under CRTS, $Y$ is a Cone. 
- Occurs when the long-run average between a firm's inputs and outputs are proportional to each other

- CRTS is equivalent to $f$ being homogeneous of degree 1
- With one input, CRTS is equivalent to linearity. 
>[!danger]- CRTS not necessarily linear for multiple inputs
>For instance, if mixing two inputs destroys the output, so that $f(z_{1}, z_{2}) = 0$ whenever $z_{1} \times z_{2}\neq 0$, while $f(z, 0) = f(0, z) = z$ we have non-increasing (constant) returns to scale with a (dichotomous and very) non-concave (and non-linear) $f$. 
- Linearity of $f$ implies CRTS, but not conversely for multiple inputs.


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

