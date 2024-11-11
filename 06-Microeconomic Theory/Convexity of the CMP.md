---
aliases: 
up: "[[Cost Minimization]]"
created: 2024-11-10
modified: 2024-11-10
tags:
  - microeconomics
  - Type/proposition
---


>[!proposition] Marginal costs are nondecreasing in $q$
>If $f$ is (strictly) concave then $c$ is a (strictly) convex function of $q$ (ie. marginal costs are (increasing) nondecreasing in q)

^0c1668

## Overview

### Motivation 
The convexity of cost functions in output reflects diminishing returns to scale in production. As output increases, the cost of producing additional units typically rises at an increasing rate due to capacity constraints and efficiency limitations.


### Proof Steps 
1) Let $q_1, q_2$ be any two output levels and $\alpha \in [0,1]$
2) Let $z_1, z_2$ be the cost-minimizing input vectors for $q_1, q_2$ respectively
3) Consider $z_\alpha = \alpha z_1 + (1-\alpha)z_2$
4) By concavity of $f$:
   $f(z_\alpha) \geq \alpha f(z_1) + (1-\alpha)f(z_2) = \alpha q_1 + (1-\alpha)q_2$
5) Therefore:
   $c(\alpha q_1 + (1-\alpha)q_2) \leq w \cdot z_\alpha = \alpha c(q_1) + (1-\alpha)c(q_2)$


`\begin{proof}`
	Let $q_1, q_2 \in \mathbb{R}_+$ and $\alpha \in [0,1]$. Let $z_1, z_2$ be the cost-minimizing input vectors for producing $q_1, q_2$ respectively. Consider the convex combination $z_\alpha = \alpha z_1 + (1-\alpha)z_2$. By the concavity of $f$, we have $f(z_\alpha) \geq \alpha f(z_1) + (1-\alpha)f(z_2) = \alpha q_1 + (1-\alpha)q_2$. This implies $z_\alpha$ is feasible for producing $\alpha q_1 + (1-\alpha)q_2$. Therefore, $c(\alpha q_1 + (1-\alpha)q_2) \leq w \cdot z_\alpha = \alpha c(q_1) + (1-\alpha)c(q_2)$.

`\end{proof}`

### Related Theorems:
- [[Shephard's Lemma]]
- [[Envelope Theorem]]

### Implications
- Marginal costs are increasing in output. As production increases, the cost of producing each additional unit either stays the same or increases
- Average costs are U-Shaped 


---

## Visual/Graphical Representation
![[Pasted image 20241110101201.png]]

## Remarks
- Any other remarks or observations:
  
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

