---
aliases: 
up: "[[Profit Maximization]]"
created: 2024-11-10
modified: 2024-11-10
tags:
  - microeconomics
  - Type/definition
---


>[!definition] $\pi$ is convex

`\begin{proof}`
Let $\mathbf{\tilde{p}}=\alpha \mathbf{p'}+ (1-\alpha)\mathbf{p''}$. Then, 
$$
\begin{align}
\pi(\mathbf{\tilde{p}}) & = \alpha \mathbf{p'}y(\mathbf{\tilde{p}}) + (1-\alpha)\mathbf{p''}y(\mathbf{\tilde{p}}) \\
 & \leq \alpha \mathbf{p'}y(\mathbf{p'})+(1-\alpha)\mathbf{p'' }y(\mathbf{p''})
\end{align}
$$

`\end{proof}`
**Implies:** [[Law of Supply]], see [[Comparative Statics in Production]]
## Overview

### Motivation 

### Related Concepts
[[ ]] (Use this to link to related concepts like Supply, Demand, Utility, etc.)



### Examples:
- Example: [[ ]] (Link to an example if available)
- Example: Insert example within the file 
- Table for items with tag example and up points to this file 



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

