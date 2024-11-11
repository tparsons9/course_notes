---
aliases: 
up: "[[Cost Minimization]]"
created: 2024-11-10
modified: 2024-11-10
tags:
  - microeconomics
  - Type/assumption
---


>[!assumption] If $f$ $H$.$\hspace{0pt}1$. (CRTS) then $c$ and $z$ $H$.$\hspace{0pt}1$. in $q$.


## Overview

### Motivation 
This assumption establishes the relationship between Constant Returns to Scale (CRTS) in production and homogeneity properties of the cost minimization problem's solutions.

### Related Concepts
- [[Constant Returns to Scale]]
- [[Cost Minimization]]
- [[Homogeneity of Conditional Factor Demands]]



## Implications
- When the production function exhibits CRTS, both the cost function and conditional factor demands are homogeneous of degree 1 in output
- This means that doubling output exactly doubles both minimal cost and optimal input quantities
- Connects the technological property of CRTS with cost behavior




---


## Remarks
- This is a key result linking production technology properties to cost properties
- Helps explain why long-run average costs are constant under CRTS
- Important for understanding economies of scale and firm size
  


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

