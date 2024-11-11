---
aliases: 
up: "[[Properties of Production Sets]]"
created: 2024-11-09
modified: 2024-11-09
tags:
  - microeconomics
  - Type/assumption
---


>[!assumption] Additivity (free entry)
>$y, y' \in Y \implies y + y' \in Y$

## Overview

>[!danger] Satisfied by NDRTS but not DRTS technologies
### Motivation 

Helps us understand that the $Y$ formalism is more general than the $f$ formalism.

The economic interpretation of the additivity condition is that if $y$ and $y'$ are both possible, then one can set up two plants that do not interfere with each other and carry out production plans $y$ and $y'$ independently. The result is then the production vector $y + y'$. 



## Implications

### Related Notions:
- [[Free Entry]] If $y \in Y$ is being produced by a firm and another firm enters and produces $y' \in Y$, then the net result is the vector $y + y'$. Hence the _aggregate production_ set must satisfy additivity whenever unrestricted entry is possible. 



---

## Visual/Graphical Representation

![[Pasted image 20241109160853.png]]

## Remarks

 Consider the additive closure of a [[Decreasing Returns to Scale]] technology. That is find the smallest set $\hat{Y}$ such that it is additive and contains a $Y$ that has DRTS. This set contains the expansion of any feasible production, such as any point on the dashed line under the solid line to any point on the dashed line above the solid line, and thus all points along the dashed line, and therefore all those _under_ the tangent to the production function at $\hspace{0pt}0$ (the dot-and-dash line), but the tangent is not included. So there is no $f$ that generates this $\hat{Y}$ as $\hat{Y}$ open. 

![[Pasted image 20241109160742.png]]




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

