---
aliases: 
up: 
created: 2024-11-09 
modified: 2024-11-09
tags: [microeconomics, Type/proposition]
---


>[!proposition] Additivity + NIRTS $\iff$ CRTS and Convex $Y$ 
>The production set $Y$ is additive and satisfies the NIRTS condition if and only if $Y$ is convex and satisfies the CRTS condition

## Overview

### Motivation 

Provides a justification for the convexity assumption in production. If feasible production plans can always be scaled down, and if the simultaneous operation of several technologies without mutual interference were always possible, then we obtain convexity. 

### Related Concepts
[[Non-increasing Returns to Scale|NIRTS]], [[Additivity (free-entry)]], [[Convexity & Concavity in Production]], [[Constant Returns to Scale|CRTS]] 

`\begin{proof}`
	The definition of a convex cone directly implies the nonincreasing returns and additivity properties. Conversely, we want to show that if nonincreasing returns and additivity hold, then for any $y, y' \in Y$ and any $\alpha> 0$, $\beta>0$, we have $\alpha y + \beta y' \in Y$. Let $k$ be any integer such that $k>\max \{ \alpha, \beta \}$. By additivity, $ky \in Y$ and $ky' \in Y$. Since $(\alpha / k)< 1$ and $\alpha y = (\alpha / k)ky$, the nonincreasing returns condition implies that $\alpha y \in Y$. Similarly, $\beta y' \in Y$. Finally, again by additivity, $\alpha y + \beta y' \in Y$
`\end{proof}`

### Related Theorems:
- [[ ]] (Link to related theorems if applicable)



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

