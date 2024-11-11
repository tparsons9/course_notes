---
aliases: 
up: "[[Cost Minimization]]"
created: 2024-11-10
modified: 2024-11-10
tags: [microeconomics, Type/theorem]
---


>[!lemma] Shephard's Lemma
>If $z(\bar{w}, q)$ is a singleton, then $c$ is differentiable in $w$ at $(\bar{w}, q)$ and $\nabla_{w}c(\bar{w}, q) = z(\bar{w}, q)$

## Overview

### Motivation 
Shephard's Lemma establishes that the cost-minimizing input demands can be obtained by differentiating the cost function with respect to input prices. This powerful result connects the solution to the cost minimization problem with the properties of the cost function.

### Related Concepts

[[Duality Theory]]

### Proof Steps 
1) Let $z(\bar{w}, q)$ be the cost-minimizing input vector at prices $\bar{w}$
2) Consider any other price vector $w'$. By definition of cost minimization:
   $c(w', q) \leq w' \cdot z(\bar{w}, q)$
   $c(\bar{w}, q) = \bar{w} \cdot z(\bar{w}, q)$
3) Therefore:
   $\frac{c(w', q) - c(\bar{w}, q)}{||w' - \bar{w}||} \leq \frac{w' \cdot z(\bar{w}, q) - \bar{w} \cdot z(\bar{w}, q)}{||w' - \bar{w}||}$

`\begin{proof}`
Let $z(\bar{w}, q)$ be the unique cost-minimizing input vector at prices $\bar{w}$. 
For any $w'$:
1) $c(w', q) \leq w' \cdot z(\bar{w}, q)$ (by definition of cost function)
2) $c(\bar{w}, q) = \bar{w} \cdot z(\bar{w}, q)$ (cost minimization)
3) Taking limits as $w' \to \bar{w}$ yields the result
`\end{proof}`

### Related Theorems:
- [[Hotelling's Lemma]]
- [[Envelope Theorem]]



---

## Visual/Graphical Representation
- Sketch or Graph (Use Latex or attach an image if relevant): 

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

