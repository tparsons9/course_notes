---
aliases:
  - MRTS
up: "[[Production Function]]"
created: 2024-11-09
modified: 2024-11-09
tags:
  - microeconomics
  - Type/Definition
---


>[!definition] Marginal Rate of Technological Substitution
> Given production function $f$ and production set $Y$. Holding the level of output fixed, we can define the marginal rate of technical substitution of input $l$ for input $k$ at $\bar{z}$ as, 
> $$
>\operatorname{MRTS}_{lk} = \frac{\partial f(\bar{z}) / \partial z_{l}}{\partial f(\bar{z}) / \partial z_{k}}
>$$

## Overview

### Motivation 

MRTS measures the additional amount of input $k$ that must be used to keep output at level $\bar{q} = f(\bar{z})$ when the amount of input $l$ is decreased marginally. Allows us to examine the trade-off between inputs that keeps the amount of outputs constant. 
### Related Concepts

- [[Marginal Rate of Substitution]]: MRTS is the production theory analog to the consumer's MRS
- [[Marginal Rate of Transformation]]: MRTS is MRT in the special case of a single-output, many-input technology



### Examples:
- [[Cobb-Douglas Production Function]]

---

## Visual/Graphical Representation
- Sketch or Graph (Use Latex or attach an image if relevant): 

## Remarks

>[!remark] 
>Along the [[Isoquants]], the MRTS shows the rate at which one input (ie. capital or labor) may be substituted for another. Thus the MRTS is the absolute value of the slope of an isoquant at the point in question. 

  

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

