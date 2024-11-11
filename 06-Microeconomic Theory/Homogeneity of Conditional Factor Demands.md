---
aliases: 
up: "[[Cost Minimization]]"
created: 2024-11-10
modified: 2024-11-10
tags:
  - microeconomics
  - Type/assumption
---


>[!assumption] $z$ is homogeneous degree $\hspace{0pt}0$ in $w$
>For all $t > 0$: $z(tw,q) = z(w,q)$
>
>This means that scaling all input prices by the same factor does not change optimal input choices.


## Overview

### Motivation 
Homogeneity of degree zero in input prices is a fundamental property of cost-minimizing behavior. It reflects the fact that only relative prices matter for input choices - if all prices double, the optimal input mix remains unchanged.

### Related Concepts
- [[Euler's Theorem]]
- [[CMP FOC]]
- [[Shephard's Lemma]]

## Mathematical Formulation

### Key Properties
1. For any scalar $t > 0$:
   $z(tw,q) = z(w,q)$

2. First derivatives:
   $\sum_{i=1}^n w_i \frac{\partial z_j}{\partial w_i} = 0$ for all $j$

### Proof Sketch
1. Consider the cost minimization problem with prices $tw$
2. Note that multiplying all prices by $t$ multiplies total cost by $t$
3. Original solution remains optimal since relative prices unchanged

## Implications

### Related Notions:
- [[Concavity of CMP]]



---


## Remarks
- Connected to [[Shephard's Lemma]] through [[Envelope Theorem]]
  



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

